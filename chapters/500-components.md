# 5. Components [3h - 4h]

**Goal:** get a grip on the basics of Angular Components and create your own.

## Mandatory Materials

**Videos**

1. [Angular Components Beginner's Guide](https://www.youtube.com/watch?v=23o0evRtrFI)

**Reading**

- [Introduction to components](https://angular.io/guide/architecture-components)
- [Creating a Component](https://angular-training-guide.rangle.io/components/creating_components)
- Angular First App
  - [Angular First App 02](https://angular.io/tutorial/first-app/first-app-lesson-02)
  - [Angular First App 03](https://angular.io/tutorial/first-app/first-app-lesson-03)
- [Presentational and Container Components Style](https://medium.com/@dan_abramov/smart-and-dumb-components-7ca2f9a7c7d0)
  - [Structuring Application Components](https://angular-training-guide.rangle.io/components/structuring_applications_with_components)
- [Debugging in Angular](https://medium.com/@vamsivempati/a-guide-to-debugging-angular-applications-5a36bd88b4cf)
- [Using Angular DevTools](https://angular.io/guide/devtools)
- [Container and Presentational Components](https://medium.com/@dan_abramov/smart-and-dumb-components-7ca2f9a7c7d0)


## Online Shop

For the moment, we will use mock data across all components. The data will be defined locally in the Typescript file associated to a component.

> Create a new Angular Component for displaying a single product's details. You can use the CLI command `ng generate component <component-name>` to achieve this.
>
> Create an Angular component for displaying a list of products. Hint: use the `*ngFor` directive.
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
│   │   ├── products.types.ts -- interface/classes for the Product
│   ├── mocks
│       ├── products.mocks.ts -- mock data for the Product (will be deleted later on when we will retrieve the data from the API)
```

## Further Resources (Optional):

- [The `*ngFor` directive](https://angular.io/guide/displaying-data#showing-an-array-property-with-ngfor)
- [The `*ngIf` directive](https://angular.io/api/common/NgIf)
- [Types of Bindings](https://angular.io/guide/binding-overview)
    - [Attribute Binding](https://angular.io/guide/attribute-binding)
    - [Property Binding](https://angular.io/guide/property-binding)
    - [Event Binding](https://angular.io/guide/event-binding)
    - [Class and Style Binding](https://angular.io/guide/class-binding)
    - [Two-Way Binding](https://angular.io/guide/two-way-binding)
