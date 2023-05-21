# 6. Modules and Standalone Components [4h]

**Goal:** Be able to understand how to better split your code functionality.

## Mandatory Materials

**Videos**

1. [Modules in Angular](https://youtu.be/UMvjzcPGyTg)
2. [Standalone Components](https://youtu.be/x5PZwb4XurU)

**Reading**

- [Introduction to Modules](https://angular.io/guide/architecture-modules)
- [Complete Guide to Modules](https://blog.angular-university.io/angular2-ngmodule/)
- [Quick Module Explanation](https://angular-training-guide.rangle.io/modules/introduction)
- [Standalone Components](https://angular.io/guide/standalone-components)


## Online Shop

> Create a new Angular Module for the shopping cart functionality called `ShoppingCartModule`
>
> Create a new Angular Component for displaying a shopping cart (separate it into container and presentational).
>
> Add the new Component to the declaration of the `ShoppingCartModule`
>
> Import `ShoppingCartModule` inside of your `AppModule` imports array
> 
> To test it, add the selector of your shopping cart in the app.component.html just to view it
>
> 
> Now, let's create a standalone component for a Button which will be used to display icons inside it (think the remove button, the shopping cart button from the mockup)
> 
> Create a new folder called `shared` (as per structure) and inside it create a component which receives a string specifying an `icon type` as an `@Input` and has an `@Output` to emit an event `onClick`
> 
> Call this new component `IconButton`
> 
> Mark the component as `standalone` and use it in your shopping cart module for the remove button (you need just import in the `ShoppingCartModule`)
>
> Test your application displays the components correctly
> 
> As a final step, to be correct let move the `product.types` from the root types folder to the `shared` module
> 
> Correct the imports in your application and test that it works without any errors in the browser console

### Folder Structure
```text
├── src/app
│   ├── modules
│   │   ├── shared
│   │   │   ├── types
│   │   │       ├── product.types
│   │   │   ├── components
│   │   │   │   ├── presentational
│   │   │   │       ├── icon-button
│   │   │   │           ├── icon-button.component.ts
│   │   │   │           ├── icon-button.component.html
│   │   │   │           ├── icon-button.component.scss
│   │   ├── shopping-cart
│   │   │   ├── shopping-cart.module.ts
│   │   │   ├── components
│   │   │       ├── containers
│   │   │       │   ├── shopping-cart-details
│   │   │       │   │   ├── shopping-cart-details.component.ts
│   │   │       │   │   ├── shopping-cart-details.component.html
│   │   │       │   │   ├── shopping-cart-details.component.scss
│   │   │       ├── presentational
│   │   │           ├── shopping-cart-details-view
│   │   │               ├── shopping-cart-details-view.ts
│   │   │               ├── shopping-cart-details-view.html
│   │   │               ├── shopping-cart-details-view.scss
│   ....<the previous files>................................
```

## Further Resources (Optional):
- [Feature Modules](https://angular.io/guide/feature-modules)
- [Shared Modules](https://angular.io/guide/sharing-ngmodules)