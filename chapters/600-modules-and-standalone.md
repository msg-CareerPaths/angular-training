# 6. Modules and Standalone Components [4h]

**Goal:** Be able to understand how to better split your code functionality.

## Mandatory Materials

**Videos**

1. [Modules in Angular](https://youtu.be/UMvjzcPGyTg)
2. [Standalone Components](https://youtu.be/x5PZwb4XurU)

**Reading**

- [Introduction to Modules](https://angular.dev/guide/ngmodules)
- [Complete Guide to Modules](https://blog.angular-university.io/angular2-ngmodule/)
- [Quick Module Explanation](https://angular-training-guide.rangle.io/modules/introduction)
- [Standalone Components](https://blog.angular-university.io/angular-standalone-components/)

## Online Shop

> Create a new Angular Module for the shopping cart functionality called `ShoppingCartModule`.
>
> Create a new Angular Component for displaying a shopping cart.
>
> Add the new Component to the declaration of the `ShoppingCartModule`
>
> Import the `ShoppingCartModule` into the imports array of your `AppModule`.
>
> To test it, add the selector for your shopping cart to the app.component.html file to display it.
>
> Now, let's create a standalone Button component that will be used to display icons inside it (such as the remove and shopping cart buttons from the mockup).
>
> Create a new folder named `shared` (following the specified structure). Within this folder, add a component that takes a string as an `@Input` to specify an `icon type` and uses an `@Output` to emit a `click` event.
>
> Name this new component `IconButton`
>
> Mark the component as `standalone` and use it as the remove button in your shopping cart module (you only need to import it into the `ShoppingCartModule`).
>
> Test that your application displays the components correctly.
>
> As a final step, for better organization, move the `product.types` file from the root types folder to the `shared` module.
>
> Correct the imports in your application and test that it works without any errors in the browser console.

### Folder Structure

```text
├── src/app
│   ├── modules
│   │   ├── shared
│   │   │   ├── types
│   │   │       ├── product.types
│   │   │   ├── components
│   │   │       ├── icon-button
│   │   │           ├── icon-button.component.ts
│   │   │           ├── icon-button.component.html
│   │   │           ├── icon-button.component.scss
│   │   ├── shopping-cart
│   │   │   ├── shopping-cart.module.ts
│   │   │   ├── components
│   │   │       ├── shopping-cart-details
│   │   │       │   ├── shopping-cart-details.component.ts
│   │   │       │   ├── shopping-cart-details.component.html
│   │   │       │   ├── shopping-cart-details.component.scss
│   ....<the previous files>................................
```

## Further Resources (Optional):

- [Feature Modules](https://angular.dev/guide/ngmodules/feature-modules)
- [Shared Modules](https://angular.dev/guide/ngmodules/sharing)
