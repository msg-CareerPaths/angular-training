# 6. Modules and Standalone Components [4h]

**Goal:** Be able to understand how to better split your code functionality.

## Mandatory Materials

**Videos**

1. [Modules in Angular](https://youtu.be/UMvjzcPGyTg)
2. [Standalone Components](https://youtu.be/x5PZwb4XurU)

**Reading**

- [Introduction to Modules](https://angular.dev/guide/ngmodules/overview) (Modules are becoming deprecated slowly, the link is kept to the old documentation)
- [Complete Guide to Modules](https://blog.angular-university.io/angular2-ngmodule/)
- [Standalone Components](https://angular.io/guide/standalone-components)
- [Input Decorator](https://angular.dev/guide/components/inputs#declaring-inputs-with-the-input-decorator)
- [Output Decorator](https://angular.dev/guide/components/outputs#declaring-outputs-with-the-output-decorator)

## Notes

- By default, starting with Angular v19, all components are standalone unless the attribute `standalone: false` is set
- If you have created your app with a cli version of v19 or higher, the cli will by default create for you a standalone config app. (that means no `app.module.ts` is present, and you only have an `app.config.ts`)
- Continue using the `@Input` and `@Output` decorator for now.

## Online Shop

>
> Create a new Angular Module for the shopping cart functionality called `ShoppingCartModule`
>
> Create a new Angular Component for displaying a shopping cart (separate it into container and presentational). Mark the components with a "standalone: false" flag in the @Component decorator.
>
> Add the new components to the declaration of the `ShoppingCartModule`
>
> Import `ShoppingCartModule` inside of your `AppModule` imports array
> 
> To test it, add the selector of your shopping cart in the app.component.html just to view it and import the module in your app.component.ts imports array.
>
> Test the previous implementation that it worked.
> 
> Convert the previous component back to a standalone and import it properly in your app.component.ts, get rid of the module.
> 

### Folder Structure
```text
├── src/app
│   ├── features
│   │   ├── shared
│   │   │   ├── types
│   │   │       ├── product.types
│   │   ├── shopping-cart
│   │   │   ├── shopping-cart.module.ts (remove this after you are done)
│   │   │   ├── shopping-cart.routes.ts (add this when you switch to standalone)
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
- [Feature Modules](https://angular.dev/guide/ngmodules/overview#the-forroot-and-forchild-pattern)
- [Shared Modules](https://angular.dev/guide/ngmodules/overview)
- [Modules vs Standalone](https://www.lynkz.com.au/blog/2024-angular-standalone-vs-modules)