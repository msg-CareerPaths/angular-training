# 9. Forms and Validation [3h]

**Goal:** dive into Angular Forms and add them to your project.

## Mandatory Materials

**Videos**

1. [Reactive Forms - The Basics](https://www.youtube.com/watch?v=JeeUY6WaXiA)
2. [Typed Forms in Angular](https://youtu.be/L-odCf4MfJc)

**Reading**

- [Forms overview](https://angular.io/guide/forms-overview)
- [Reactive Forms](https://angular.io/guide/reactive-forms) (focus on this)
- [Angular First App 12: Forms](https://angular.io/tutorial/first-app/first-app-lesson-12)
- [Validating Form Input](https://angular.io/guide/form-validation)
- [Form Validation: Reactive Forms](https://angular.io/guide/form-validation#validating-input-in-reactive-forms)
- [Forms tutorial](https://www.tutorialspoint.com/angular6/angular6_forms.htm)


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
- [ControlValueAccessor](https://angular.io/api/forms/ControlValueAccessor)