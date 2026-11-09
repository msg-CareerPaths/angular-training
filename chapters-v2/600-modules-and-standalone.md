# 6. Modules and Standalone Components [4h]

## Introduction

Angular 22 defaults to **standalone** components — no `NgModule` needed. This chapter teaches that modern approach first, then explains what `NgModule` was so you can navigate older codebases. For a wider tour of legacy Angular patterns, see [Chapter 14](1400-legacy-angular-conventions.md).

## Goal

### Theory

By the end of this chapter you should be able to explain:

- What "standalone" means on a component and how `imports: [...]` on the component replaces module declarations.
- How `app.config.ts` and `bootstrapApplication()` replace `AppModule`.
- What an `NgModule` was (declarations, imports, providers, exports) and why it still shows up in older projects.
- When (in modern code) you would still reach for `NgModule` — rarely, for backwards compatibility.

### Practice

> Create an Angular component for the shopping cart (one container + one presentational), standalone from the start.
>
> Place its selector in `app.component.html` and import the container into `app.component.ts` `imports` array. Confirm it renders.
>
> For **learning only**, briefly explore the legacy path: scaffold a `ShoppingCartModule`, add `standalone: false` on your components, register them in the module's `declarations`, import the module into `AppModule`. Re-verify it still works.
>
> Then revert to standalone — this is the shape we use going forward.

#### Rules

- Default to **standalone** components in every chapter from here on.
- Keep using signal inputs/outputs (`input()`, `output()`) from Chapter 5.

#### Folder Structure

```text
├── src/app
│   ├── features
│   │   ├── shared
│   │   │   ├── types
│   │   │       ├── product.types.ts
│   │   ├── shopping-cart
│   │   │   ├── shopping-cart.routes.ts        -- lazy-loaded routes added in Chapter 8
│   │   │   ├── components
│   │   │       ├── containers
│   │   │       │   ├── shopping-cart-details
│   │   │       │   │   ├── shopping-cart-details.ts
│   │   │       │   │   ├── shopping-cart-details.html
│   │   │       │   │   ├── shopping-cart-details.scss
│   │   │       ├── presentational
│   │   │           ├── shopping-cart-details-view
│   │   │               ├── shopping-cart-details-view.ts
│   │   │               ├── shopping-cart-details-view.html
│   │   │               ├── shopping-cart-details-view.scss
│   ....<the previous files>................................
```

## Mandatory Materials

**Videos**

1. [Standalone Components](https://youtu.be/x5PZwb4XurU)
2. [Modules in Angular](https://youtu.be/UMvjzcPGyTg) *(context for legacy code)*

**Reading**

- [Standalone Components](https://angular.dev/guide/components/importing) — the modern default.
- [`bootstrapApplication` and `app.config.ts`](https://angular.dev/api/platform-browser/bootstrapApplication)
- [NgModules Overview](https://angular.dev/guide/ngmodules/overview) — background for older projects.
- [Modules vs Standalone](https://www.angular.courses/modern-angular-path/modules/standalone-vs-ngmodules)

### Notes

- Since Angular v19, components are standalone unless you set `standalone: false`.
- Projects created with Angular v19+ CLI don't have an `app.module.ts` — only `app.config.ts`.

## Testing

> Add one test for the shopping-cart container component:
>
> - Render it with a mock cart of a few items and assert the total line item count and the rendered total price.
> - Toggle an input's value, trigger change detection, and assert the DOM updates.

## Optional Resources

- [Feature Modules (legacy)](https://angular.dev/guide/ngmodules/overview)
- [Shared Modules (legacy)](https://angular.dev/guide/ngmodules/overview)
- [Lazy loading with standalone routes](https://angular.dev/guide/routing/common-router-tasks#lazy-loading) — useful preview for Chapter 8.
