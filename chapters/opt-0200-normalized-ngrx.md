# OPT-2. Classical NgRx & Normalized State

## Introduction

Real-world codebases you will join often still use **classical NgRx**: a global `Store`, actions, reducers, selectors, and effects. This chapter teaches that Redux-style approach — the *legacy* form of state management, analogous to the decorator-era conventions in [Chapter 13](1300-legacy-angular-conventions.md) — and then shows how to **normalize** the state with `@ngrx/entity` for efficient lookups and updates.

It assumes you've already built the Online Shop state with Signal Store in [Chapter 12](1200-ngrx.md). Only pick this up if you specifically want exposure to classical NgRx.

> **Note:** Redux-style state is usually used in medium-to-large projects; we use it here to understand its fundamentals. Talk to your mentor if you get stuck.

The chapter has two parts:

1. **Classical NgRx basics** — actions, reducers, selectors, effects.
2. **Normalized state with `@ngrx/entity`** — the same building blocks, applied with an `ids` + `entities` state shape.

## Goal

### Theory

By the end of this chapter you should be able to explain:

- The Redux data flow: **action → reducer → store → selector → component**, with **effects** handling side effects such as HTTP.
- What each classical NgRx building block does (`createAction`, `createReducer`, `createSelector`, `createEffect`) and how it maps to Signal Store primitives (`withState`, `withComputed`, `withMethods`, `rxMethod`).
- What a normalized state shape is (`ids` + `entities` dictionary) and why it beats arrays-of-objects for lookups and updates.
- How `@ngrx/entity` provides the primitives (`createEntityAdapter`, `EntityState`, pre-built CRUD reducer helpers, denormalizing selectors).
- Where effects fit in to hydrate the entity state from HTTP.

### Practice

> **Rewrite just one store — the `ProductsStore` — in classical NgRx**, as an alternative to your Signal Store version. Keep the Signal Store implementation; you should be able to switch the container component between the two.
>
> `npm install @ngrx/store @ngrx/effects @ngrx/entity @ngrx/store-devtools`
>
> - **Actions:** `loadAll`, `loadAllSuccess`, `loadAllFailure`, `select`, `remove`.
> - **Reducer:** state is `EntityState<Product>` (`ids` + `entities`) plus `loading` and `selectedId`. Use an [Entity Adapter](https://ngrx.io/guide/entity) for the reducer helpers (`setAll`, `removeOne`, …).
> - **Selectors:** use `adapter.getSelectors()` and add a `selectSelectedProduct` selector that denormalizes `selectedId` + `entities` back into a `Product`.
> - **Effect:** `loadAll` → call `ProductsService` → `loadAllSuccess` / `loadAllFailure`.
> - Dispatch actions and select state **only** in the container ("smart") component.
>
> Hints:
>
> - Keep the `loading` flag in state and bind spinners to it.
> - Use the `async` pipe (or `store.selectSignal`) in the smart component so presentational components never receive `Observable`s.
> - Install the [Redux DevTools](https://chrome.google.com/webstore/detail/redux-devtools/lmhkpmbekcpmknklioeibfkpmmfibljd?hl=en) browser extension and add [Store DevTools](https://ngrx.io/guide/store-devtools/install) (`provideStoreDevtools()`) to your app.
>
> **Stretch (optional):** repeat the exercise for the Shopping Cart (reducer inside the `shopping-cart` feature folder) and User state.

#### Folder Structure

**Note:** For brevity the Products state is shown; in a larger app, keep a `state` folder per feature.

```text
├── src/app
│   ├── features
│       ├── products
│       │   ├── state
│       │   │   ├── products.actions.ts
│       │   │   ├── products.reducer.ts   -- adapter, initialState, reducer
│       │   │   ├── products.selectors.ts
│       │   │   ├── products.effects.ts
│       │   ├── store
│       │   │   ├── products.store.ts     -- the Signal Store version (kept)
│.......<the previous files>................................
```

## Part 1: Classical NgRx Basics

Use the modern creator functions:

```ts
// Action
export const increment = createAction('[Counter Component] Increment');

// Reducer
export const counterReducer = createReducer(
  initialState,
  on(increment, (state) => state + 1),
  on(decrement, (state) => state - 1),
  on(reset, () => 0),
);

// Selectors
export const selectFeature = (state: AppState) => state.feature;

export const selectFeatureCount = createSelector(
  selectFeature,
  (state: FeatureState) => state.counter,
);
```

Many older tutorials use deprecated APIs (class-based actions, `ofType` with strings, `@Effect()` decorators). Always follow the current documentation.

Before moving on, make sure you can answer: where does an HTTP call live in this flow? (In an **effect**, which listens for an action, calls the service, and dispatches a success/failure action that the reducer handles.)

## Part 2: Normalized State with `@ngrx/entity`

Storing collections as arrays (`Product[]`) makes lookups O(n) and updates awkward. A **normalized** state keeps `ids` and a dictionary of `entities`:

```ts
{
  ids: ['p1', 'p2'],
  entities: {
    p1: { id: 'p1', name: 'Keyboard' },
    p2: { id: 'p2', name: 'Mouse' },
  },
}
```

`@ngrx/entity` generates the reducer helpers and selectors for this shape, so you only need to describe the entity:

```ts
export const adapter = createEntityAdapter<Product>();
export const initialState = adapter.getInitialState({ loading: false });

export const productsReducer = createReducer(
  initialState,
  on(ProductsActions.loadAllSuccess, (state, { products }) => adapter.setAll(products, state)),
  on(ProductsActions.remove, (state, { id }) => adapter.removeOne(id, state)),
);

export const { selectAll, selectEntities, selectIds } = adapter.getSelectors();
```

Use effects to hydrate the entity state from HTTP (`loadAll` → service call → `loadAllSuccess`), and compose selectors (`createSelector`) to denormalize data back into the shapes the UI needs (e.g. the cart's items joined with product details).

## Mandatory Materials

**Videos**

- [NgRx Crash Course](https://www.youtube.com/watch?v=kx0VTgTtSBg)
- [Original JS Redux](https://youtu.be/_shA5Xwe8_4) — the library NgRx is modeled on.
- [NgRx Quickstart](https://youtu.be/f97ICOaekNU) — *uses the deprecated NgRx API; watch for the concepts only.*

**Reading**

- [Angular: NgRx a clean and clear introduction](https://medium.com/frontend-fun/angular-ngrx-a-clean-and-clear-introduction-4ed61c89c1fc) — use the modern creators shown above, not the ones in the article.
- [NgRx Store — reducers & actions](https://ngrx.io/guide/store)
- [NgRx Effects](https://ngrx.io/guide/effects)
- [Normalizing state shape (Redux)](https://redux.js.org/recipes/structuring-reducers/normalizing-state-shape)
- [Benefits of state normalization in Angular](https://medium.com/angular-in-depth/the-benefits-of-application-state-normalization-in-angular-f93392ca9f44)
- [NgRx Entity](https://ngrx.io/guide/entity)
- [NgRx Store testing](https://ngrx.io/guide/store/testing)
- [NgRx Effects testing](https://ngrx.io/guide/effects/testing)

## Testing

> For the Products state:
>
> - Test the reducer: `loadAllSuccess` populates `ids` and `entities`; `remove` drops the id from both.
> - Test the `loadAll` effect using `provideMockActions` and a stub `ProductsService`.

## Further Reading

- [NgRx docs](https://ngrx.io/docs)
- [NgRx tips and tricks (effects)](https://medium.com/@praveenpuglia/practical-ngrx-effects-tips-tricks-1935509c9fb6)
- [NgRx best practices](https://indepth.dev/posts/1451/ngrx-best-practices-new)
- [NgRx example app](https://github.com/ngrx/platform/tree/master/projects/example-app/)
- [Redux from scratch](https://youtu.be/hG7v7quMMwM)
- [NgRx Signal Store](https://ngrx.io/guide/signals/signal-store)
