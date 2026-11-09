# OPT-2. Normalized NgRx

## Introduction

This chapter is a deeper dive into **classical NgRx** (see [Chapter 13](1300-ngrx.md)'s optional section for the primer). It assumes you've already built the main Online Shop state with Signal Store and now want to see what the Redux-style approach looks like, with the state **normalized** for efficient updates.

Only pick this up if you specifically want exposure to classical NgRx.

## Goal

### Theory

By the end of this chapter you should be able to explain:

- What a normalized state shape is (`ids` + `entities` dictionary) and why it beats arrays-of-objects for lookups and updates.
- How `@ngrx/entity` provides the primitives (`createEntityAdapter`, `EntityState`, pre-built CRUD reducer helpers, denormalizing selectors).
- Where effects fit in to hydrate the entity state from HTTP.

### Practice

> Build a parallel NgRx classical implementation of Products, Users, and Shopping Cart state:
>
> - Split reducers / effects / selectors per entity (Product, User, Shopping Cart).
> - Place the Shopping Cart reducer inside the `shopping-cart` feature folder.
> - Split state into:
>   - `ids`: array of primary keys,
>   - `entities`: dictionary keyed by id.
> - Use [Entity Adapter](https://ngrx.io/guide/entity) to generate selectors and reducer helpers.
> - Add selectors to denormalize data back for the UI.
>
> Keep this in a branch — don't delete your Signal Store code.

## Mandatory Materials

**Reading**

- [Normalizing state shape (Redux)](https://redux.js.org/recipes/structuring-reducers/normalizing-state-shape)
- [Benefits of state normalization in Angular](https://medium.com/angular-in-depth/the-benefits-of-application-state-normalization-in-angular-f93392ca9f44)
- [NgRx Entity](https://ngrx.io/guide/entity)
- [NgRx Store testing](https://ngrx.io/guide/store/testing)
- [NgRx Effects testing](https://ngrx.io/guide/effects/testing)

## Testing

> Add a test for the normalized reducer handling `addProduct` / `removeProduct` / `updateProduct`. Assert `ids` and `entities` evolve correctly.
>
> Add a test for one effect using `provideMockActions`.
