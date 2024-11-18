# OPT-2. Normalized NgRx

**Goal:** Normalize the NGRX state.

## Mandatory Materials

- [Normalizing State Shape](https://redux.js.org/recipes/structuring-reducers/normalizing-state-shape)
- [The benefits of application state normalization in Angular](https://medium.com/angular-in-depth/the-benefits-of-application-state-normalization-in-angular-f93392ca9f44)
- [NgRx Entity State](https://ngrx.io/guide/entity) (use this to help with your normalization)

## Online Shop:

> Split your main reducers, effects, and selectors into separate reducers for each entity (e.g., Product, User, Shopping Cart).
>
> Place the Shopping Cart reducer inside the `shopping-cart` module folder.
>
> Divide your reducer state into two parts using NgRx's Entity Adapter:
>
> - `ids`: An array of all the primary IDs in the collection
> - `entities`: A dictionary of entities in the collection, indexed by their primary ID.
>
> Define selectors to denormalize the data as needed for your pages.
>
> Refactor your application to follow the new structure and test it.
