# 8. Routing [2h – 3h]

## Introduction

Routing turns URL paths into views. In this chapter you add navigation to the Online Shop: a product list at one URL, a product detail at another.

You already know from [Chapter 7](700-rxjs.md) that `ActivatedRoute` exposes params as Observables (`paramMap`, `queryParamMap`). You could subscribe to those — and plenty of older codebases do. **In this training we prefer signal inputs via `withComponentInputBinding()`** for route params: no subscription to manage, no `takeUntilDestroyed`, the value just arrives as a signal. We'll mention the Observable form for recognition only.

## Goal

### Theory

By the end of this chapter you should be able to explain:

- What a route is and how `path`, `component`, `loadComponent`, and `children` compose.
- What `<router-outlet>` does.
- How to navigate declaratively (`routerLink`) and programmatically (`Router.navigate`).
- How to read a route parameter via **signal inputs with `withComponentInputBinding()`** (preferred in Angular 22).
- How to read a route parameter via `ActivatedRoute.snapshot` (one-shot read).
- Lazy loading routes via `loadComponent` / `loadChildren`.

### Practice

> Add a button next to each product in the product list that navigates to the product's detail page.
>
> From the detail page, add an "Add to Cart" button (hooks up properly in later chapters).
>
> Wire routing: register `app.routes.ts` in `app.config.ts`, add `<router-outlet>` to `app.component.html`.
>
> Redirect the default path `/` to `/products`.
>
> Pass the product's ID as a route param. **Read it as a signal input** on the detail component via `withComponentInputBinding()`. Example:
>
> ```ts
> // app.config.ts
> provideRouter(routes, withComponentInputBinding())
>
> // products-details.ts
> id = input.required<string>();        // comes straight from the :id route param
> ```
>
> If a given use case only needs a one-shot read, use `ActivatedRoute.snapshot.paramMap.get('id')` instead.

#### Folder Structure

```text
├── src/app
│   ├── app.routes.ts
│   ├── app.config.ts            -- provideRouter(routes, withComponentInputBinding())
│   ....<the previous files>................................
```

## Mandatory Materials

**Videos**

1. [Angular Router — The Basics](https://www.youtube.com/watch?v=Np3ULAMqwNo)

**Reading**

- [Angular Routing](https://angular.dev/guide/routing)
- [Common router tasks](https://angular.dev/guide/routing/common-router-tasks)
- [`withComponentInputBinding` — route params as signal inputs](https://angular.dev/api/router/withComponentInputBinding)
- [Reading route state](https://angular.dev/guide/routing/read-route-state) — the **snapshot** section is what you'll use here; the Observable-based `paramMap` section is the RxJS-flavored alternative from [Chapter 7](700-rxjs.md).
- [Lazy loading](https://angular.dev/guide/routing/common-router-tasks#lazy-loading)

## Testing

> Add a routing test for the detail component:
>
> - Use `RouterTestingHarness` (or a stub `ActivatedRoute`) to render the detail component with `id` set to a known product.
> - Assert the DOM shows that product's title.
>
> Reference: [Angular testing — routing](https://angular.dev/guide/testing/components-scenarios#routing-component).

## Optional Resources

- [`Router.navigate` deep dive](https://angular.dev/api/router/Router#navigate)
- [Route data (static)](https://angular.dev/api/router/Route#data)
- [Resolvers](https://angular.dev/api/router/Resolve) — prefer them cautiously; signal-based data loading is usually simpler.
