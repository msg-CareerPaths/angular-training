# 10. Forms and Validation [3h]

**Goal:** dive into Angular Forms and add them to your project.

## Mandatory Materials

**Videos**

1. [Reactive Forms—The Basics](https://www.youtube.com/watch?v=JeeUY6WaXiA)
2. [Typed Forms in Angular](https://www.youtube.com/watch?v=L-odCf4MfJc)

**Reading**

- [Forms overview](https://angular.dev/guide/forms)
- [Reactive Forms](https://angular.dev/guide/forms/reactive-forms) (focus on this)
- [Angular First App 12: Forms](https://angular.dev/tutorials/first-app/12-forms)
- [Validating Form Input](https://angular.dev/guide/forms/form-validation)
- [Form Group and Form Controls in Angular](https://blog.logrocket.com/formgroup-formcontrol-angular/)


## Online Shop:

Recall that the logic should be added to the `container` components and the presentational part in his named counterpart.

> Add a new "Edit" button on the detail page. Pressing it should open a new view, which uses reactive forms to update the properties of the product. The view should have two buttons: "Cancel" (which undo's all the changes) and "Save" (which calls the backend to persist the changes).
>
> Add some validation to your form (ex: check that the fields are not empty, that the price and weight inputs contain only numbers, etc.)
>
> Also create a new "Add" button on the product list. Pressing this button should open a view for creating a new product (which the same structure and buttons as the edit view).

### Folder Structure
```text
├── src/app
│   ├── components
│   │   ├── containers
│   │   │   ├── products-form
│   │   │   │   ├── products-form.component.ts
│   │   │   │   ├── products-form.component.scss
│   │   │   │   ├── products-form.component.html
│   │   ├── presentational
│   │       ├── products-form-view
│   │       │   ├── products-form-view.component.ts
│   │       │   ├── products-form-view.component.scss
│   │       │   ├── products-form-view.component.html
│.......<the previous files>................................
```

## Further Resources (Optional):

- [Custom form controls](https://blog.thoughtram.io/angular/2016/07/27/custom-form-controls-in-angular-2.html)
- [ControlValueAccessor](https://angular.dev/api/forms/ControlValueAccessor)