# OPT-2. Normalized NgRx

**Goal:** Normalize the NGRX state.

## Mandatory Materials
- [Normalizing State Shape](https://redux.js.org/recipes/structuring-reducers/normalizing-state-shape)
- [The benefits of application state normalization in Angular](https://medium.com/angular-in-depth/the-benefits-of-application-state-normalization-in-angular-f93392ca9f44)
- [NgRx Entity State](https://ngrx.io/guide/entity) (use this to help with your normalization)

## Online Shop:

> Split your main reducers, effects, selectors into `reducers per entity` (e.g.: Product, User, Shopping Cart)
> 
> Have the Shopping Cart reducer inside the `shopping-cart` module folder
> 
> Split your reducer state into two parts: (use Entity Adapter from NgRx)
>  - `ids`: An array of all the primary ids in the collection,
>  - `entities`: A dictionary of entities in the collection indexed by the primary id.
>
> You should define selectors to denormalize the data back to what you need in your pages.
> 
> Refactor your application to use the new structure and test it.
