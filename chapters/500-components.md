# 5. Components [3h - 4h]

**Goal:** get a grip on the basics of Angular Components and create your own.

## Mandatory Materials

**Videos**

1. [Angular Components Beginner's Guide](https://www.youtube.com/watch?v=23o0evRtrFI)

**Reading**

- [Angular Component Essentials](https://angular.dev/essentials/components)
- [Official Component Documentation](https://angular.dev/guide/components) (first 6 chapters + Lifecycle chapter)
- Angular First App
  - [Angular First App 02](https://angular.dev/tutorials/first-app/02-HomeComponent)
  - [Angular First App 03](https://angular.dev/tutorials/first-app/03-HousingLocation)
- [Debugging in Angular](https://medium.com/@vamsivempati/a-guide-to-debugging-angular-applications-5a36bd88b4cf)
- [Using Angular DevTools](https://angular.dev/tools/devtools)

## Online Shop

For the moment, we will use mock data across all components. The data will be defined locally in the Typescript file associated to a component.

> Create a new Angular Component for displaying a single product's details. Use the CLI command `ng generate component <component-name>` to achieve this. `ng g c <component-name>` will also do the trick!.
>
> Create an Angular component for displaying a list of products. Hint: use the `*ngFor` directive.
>
> Add some CSS to each component to improve their appearance and align them with the mockup structure.
>
> Add the selectors for both components to app.component.html to test them.
>
> Note: The buttons shown in the mockups (e.g., shopping cart, edit, delete) can be added either now with basic styling and no functionality, or implemented later with full functionality and design.

### Folder Structure

```text
├── src/app
│   ├── components
│   │   ├── products-list
│   │   │   ├── products-list.component.ts
│   │   │   ├── products-list.component.scss
│   │   │   ├── products-list.component.html
│   │   ├── products-details
│   │   │   ├── products-details.component.ts
│   │   │   ├── products-details.component.scss
│   │   │   ├── products-details.component.html
│   ├── types
│   │   ├── products.types.ts -- interface for the Product
│   ├── mocks
│       ├── products.mocks.ts -- mock data for the Product (will be deleted later on when we will retrieve the data from the API)
```

## Further Resources (Optional):

- [The `*ngFor` directive](https://angular.dev/api/common/NgFor?tab=description)
- [The `*ngIf` directive](https://angular.dev/api/common/NgIf?tab=description)
- [Bindings](https://angular.dev/guide/templates/binding)
- [Event Listeners](https://angular.dev/guide/templates/event-listeners)
- [Two-Way Binding](https://angular.dev/guide/templates/two-way-binding)
