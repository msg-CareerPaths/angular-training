# 5. Components [3h - 4h]

**Goal:** get a grip on the basics of Angular Components and create your own.

## Mandatory Materials

**Videos**

1. [Angular Components Beginner's Guide](https://www.youtube.com/watch?v=23o0evRtrFI)

**Reading**

- [Introduction to components](https://angular.dev/guide/components)
- Angular First App
  - [Angular First App 02](https://angular.dev/tutorials/first-app/02-Home)
  - [Angular First App 08](https://angular.dev/tutorials/first-app/08-ngFor) (stop here)
- [Presentational and Container Components Style](https://medium.com/@dan_abramov/smart-and-dumb-components-7ca2f9a7c7d0)
- [Debugging in Angular](https://medium.com/@vamsivempati/a-guide-to-debugging-angular-applications-5a36bd88b4cf)
- [Using Angular DevTools](https://angular.dev/tools/devtools)
- [Input Decorator](https://angular.dev/guide/components/inputs#declaring-inputs-with-the-input-decorator)
- [Output Decorator](https://angular.dev/guide/components/outputs#declaring-outputs-with-the-output-decorator)

## Online Shop

For the moment, we will use mock data across all components. The data will be defined locally in the Typescript file associated to a component.
> Use for the moment use the @Input and @Output decorator to bind the components. Do not signal inputs or outputs.
> 
> Create a new Angular Component for displaying a single product's details. You can use the CLI command `ng generate component <component-name>` to achieve this.
>
> Create an Angular component for displaying a list of products. Hint: use the `@for` directive.
>
> Add some CSS to each of the components to make them look nicer (following the mockup structure).
> 
> To test them, add their selector to the app.component.html just to view them

### Folder Structure
```text
├── src/app
│   ├── components
│   │   ├── containers -- just import the mock data here and pass it to the presentational as input
│   │   │   ├── products-list
│   │   │   │   ├── products-list.component.ts
│   │   │   │   ├── products-list.component.scss
│   │   │   │   ├── products-list.component.html
│   │   │   ├── products-details
│   │   │   │   ├── products-details.component.ts
│   │   │   │   ├── products-details.component.scss
│   │   │   │   ├── products-details.component.html
│   │   ├── presentational -- the presentational aspect of the components
│   │       ├── products-list-view
│   │       │   ├── products-list-view.component.ts
│   │       │   ├── products-list-view.component.scss
│   │       │   ├── products-list-view.component.html
│   │       ├── products-details-view
│   │           ├── products-details-view.component.ts
│   │           ├── products-details-view.component.scss
│   │           ├── products-details-view.component.html
│   ├── types
│   │   ├── products.types.ts -- interface for the Product
│   ├── mocks
│       ├── products.mocks.ts -- mock data for the Product (will be deleted later on when we will retrieve the data from the API)
```

## Further Resources (Optional):

- [The `@for` directive](https://angular.dev/guide/templates/control-flow#repeat-content-with-the-for-block)
- [The `@if` directive](https://angular.dev/guide/templates/control-flow#conditionally-display-content-with-if-else-if-and-else)
- [Types of Bindings](https://angular.dev/guide/templates/binding)
    - [Attribute Binding](https://angular.dev/guide/templates/binding#attributes)
    - [Property Binding](https://angular.dev/guide/templates/binding#binding-dynamic-properties-and-attributes)
    - [Event Binding](https://angular.dev/guide/templates/event-listeners)
    - [Class and Style Binding](https://angular.dev/guide/templates/binding#css-class-and-style-property-bindings)
    - [Two-Way Binding](https://angular.dev/guide/templates/two-way-binding)
