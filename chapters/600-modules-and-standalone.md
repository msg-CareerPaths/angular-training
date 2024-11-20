# 6. Modules and Standalone Components [4h]

**Goal:** Gain a better understanding of how to organize and split your code functionality effectively.

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
> Create a new Angular Component to display the shopping cart.
>
> Add the new Component to the declarations array of the `ShoppingCartModule`
>
> Import the `ShoppingCartModule` into the imports array of your `AppModule`.
>
> Add the selector of your shopping cart component to the app.component.html file to display it for testing.
>
> Create a new `shared` folder (following the specified structure). Inside this folder, create a new standalone component named `IconButton`, that will be used to display icons (e.g., the remove and shopping cart buttons from the mockup).
>
> This component should accept a string as an `@Input` to specify the `icon type`, and it should emit a `click` event using `@Output`.
>
> Mark the component as `standalone` and use it as the remove button in your shopping cart module (you only need to import it into the `ShoppingCartModule`).
>
> Test that your application displays the components correctly.
>
> As a final step, for better organization, move the `product.types` file from the root types folder to the `shared` module.
>
> Correct the imports in your application and test that if everything works without errors in the browser console.

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
