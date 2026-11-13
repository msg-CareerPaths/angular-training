# 5. Components [3h – 4h]

## Introduction

Components are the unit of UI in Angular. Starting with Angular 22, the modern way is: **standalone** components, **signal** inputs/outputs, **native control flow** (`@if`, `@for`, `@switch`), and `inject()` for dependencies. That is the only style used in this chapter.

The legacy decorator style (`@Input()`, `@Output()`, `*ngIf`, `*ngFor`) and `NgModule` are covered in [Chapter 13](1300-legacy-angular-conventions.md).

## Goal

### Theory

By the end of this chapter you should be able to explain:

- What a component is in Angular (TS class + template + styles + selector).
- How to declare a **signal input** (`input()` / `input.required()`) and a **signal output** (`output()`).
- The native control-flow blocks `@if`, `@for`, `@switch`, `@let`.
- Template binding types: property, attribute, event, class/style, two-way.
- The lifecycle hooks `ngOnInit`, `ngOnChanges`, `ngOnDestroy` and when each fires.
- The Presentational / Container (smart / dumb) split and why it matters.
- How to use Angular DevTools.

### Practice

Use mock data defined locally in each component's TypeScript file. Real data will come later via HTTP.

> Create a new Angular component for displaying a single product's detail. Use `ng generate component <component-name>`.
>
> Create a component for displaying a list of products. Use the `@for` block.
>
> Create a shopping-cart component (one container + one presentational) that renders a list of mock cart items and a total.
>
> Use `input()` and `output()` (signal-based) to wire data between parent and child components.
>
> Add CSS to each component so it roughly matches the mockups.
>
> To test them, place their selectors in `app.html` and import the containers into `app.ts`'s `imports` array.

#### Rules

- Every component is **standalone** (the default in Angular 22) and uses **signal inputs/outputs**.
- Use native control flow (`@if`, `@for`, `@switch`) — avoid the legacy structural directives.
- Note that Angular 22's CLI scaffolds standalone components by default: `app.config.ts` + `bootstrapApplication()` replace the old `app.module.ts`. For the legacy `NgModule` path, see [Chapter 13](1300-legacy-angular-conventions.md).

#### Folder Structure

We organize the app **by feature**. Inside each feature, `pages/` holds the smart, routed components (the containers) and `views/` holds the presentational, view-only components. A feature also owns its types, and later its service and store. Two more top-level folders appear in later chapters — `core/` for app-wide singletons (guards, interceptors, auth) and `shared/` for things used across features.

`ng generate` scaffolds a `.spec.ts` test file next to every component and service — those are shown below and in later chapters.

```text
├── src/app
│   ├── features
│   │   ├── products
│   │   │   ├── pages
│   │   │   │   ├── products-list
│   │   │   │   │   ├── products-list.ts
│   │   │   │   │   ├── products-list.scss
│   │   │   │   │   ├── products-list.html
│   │   │   │   │   ├── products-list.spec.ts
│   │   │   │   ├── products-details
│   │   │   │       ├── products-details.ts
│   │   │   │       ├── products-details.scss
│   │   │   │       ├── products-details.html
│   │   │   │       ├── products-details.spec.ts
│   │   │   ├── views
│   │   │   │   ├── products-list-view
│   │   │   │   │   ├── products-list-view.ts
│   │   │   │   │   ├── products-list-view.scss
│   │   │   │   │   ├── products-list-view.html
│   │   │   │   │   ├── products-list-view.spec.ts
│   │   │   │   ├── products-details-view
│   │   │   │       ├── products-details-view.ts
│   │   │   │       ├── products-details-view.scss
│   │   │   │       ├── products-details-view.html
│   │   │   │       ├── products-details-view.spec.ts
│   │   │   ├── products.types.ts       -- interface for Product
│   │   │   ├── products.mocks.ts       -- mock data (deleted in Chapter 9, once HTTP replaces it)
│   │   ├── shopping-cart
│   │       ├── pages
│   │       │   ├── shopping-cart-details
│   │       │       ├── shopping-cart-details.ts
│   │       │       ├── shopping-cart-details.scss
│   │       │       ├── shopping-cart-details.html
│   │       │       ├── shopping-cart-details.spec.ts
│   │       ├── views
│   │           ├── shopping-cart-details-view
│   │               ├── shopping-cart-details-view.ts
│   │               ├── shopping-cart-details-view.scss
│   │               ├── shopping-cart-details-view.html
│   │               ├── shopping-cart-details-view.spec.ts
```

## Mandatory Materials

**Videos**

1. [Angular Components Beginner's Guide](https://www.youtube.com/watch?v=23o0evRtrFI)

**Reading**

- [Introduction to components](https://angular.dev/guide/components)
- Angular First App — [02: Home](https://angular.dev/tutorials/first-app/02-Home) → [08: @for](https://angular.dev/tutorials/first-app/08-ngFor) *(stop here)*
- [Presentational vs Container Components](https://medium.com/@dan_abramov/smart-and-dumb-components-7ca2f9a7c7d0)
- [Component lifecycle](https://angular.dev/guide/components/lifecycle)
  - [`ngOnInit`](https://angular.dev/guide/components/lifecycle#ngoninit)
  - [`ngOnChanges`](https://angular.dev/guide/components/lifecycle#ngonchanges)
  - [`ngOnDestroy`](https://angular.dev/guide/components/lifecycle#ngondestroy)
- [Signal inputs](https://angular.dev/guide/components/inputs) — modern input API.
- [Signal outputs](https://angular.dev/guide/components/outputs) — modern output API.
- [Native control flow](https://angular.dev/guide/templates/control-flow)
- [Debugging Angular apps](https://medium.com/@vamsivempati/a-guide-to-debugging-angular-applications-5a36bd88b4cf)
- [Angular DevTools](https://angular.dev/tools/devtools)

## Testing

> Write a basic test for the presentational `products-list-view` component:
>
> - Render the component with a mock list of products and assert the DOM shows one row per product.
> - Emit an output (e.g. "view details") from a child element and assert the parent's spy was called.
>
> Add a test for the `shopping-cart-details` container:
>
> - Render it with a mock cart of a few items and assert the total line-item count and the rendered total price.
>
> Reference: [Angular testing — components basics](https://angular.dev/guide/testing/components-basics).

## Optional Resources

### Native Control Flow

- [`@for`](https://angular.dev/guide/templates/control-flow#repeat-content-with-the-for-block)
- [`@if`](https://angular.dev/guide/templates/control-flow#conditionally-display-content-with-if-else-if-and-else)
- [`@switch`](https://angular.dev/api/core/@switch)
- [`@let`](https://angular.dev/api/core/@let)

### Template Bindings

- [Types of bindings](https://angular.dev/guide/templates/binding)
  - [Attribute binding](https://angular.dev/guide/templates/binding#attributes)
  - [Property binding](https://angular.dev/guide/templates/binding#binding-dynamic-properties-and-attributes)
  - [Event binding](https://angular.dev/guide/templates/event-listeners)
  - [Class & style binding](https://angular.dev/guide/templates/binding#css-class-and-style-property-bindings)
  - [Two-way binding](https://angular.dev/guide/templates/two-way-binding)
