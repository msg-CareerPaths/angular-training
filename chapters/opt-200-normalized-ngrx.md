## OPT-2. Normalized NgRx


**Goal:** Normalize the NGRX state.

#### Required Reading:
- [Normalizing State Shape](https://redux.js.org/recipes/structuring-reducers/normalizing-state-shape)
- [The benefits of application state normalization in Angular](https://medium.com/angular-in-depth/the-benefits-of-application-state-normalization-in-angular-f93392ca9f44)
- [NgRx Entity State](https://ngrx.io/guide/entity) (use this to help with your normalization)

#### Online Shop:

> Split your application state into two parts:
>  - `data`: The portion which will hold the normalized data collections,
>  - `ui`: The portion which will hold the sub-states used in the app pages.
>
> Inside the `data` sub-tree, you should have a `products` map (between ID and the entity itself).
> For each product, you should also store an indicator if the product is fully loaded or just the header is loaded.
> You should only make a call to the backend if it is really necessary (if the entity / entity set is not loaded).
>
> Inside the `ui` sub-tree, you should never copy product data, just have the IDs to reference the corresponding
> entry from the `data` sub-tree.
>
> You should define selectors to denormalize the data back to what you need in your pages.
