# 9. Forms and Validation [3h]

**Goal:** dive into Angular Forms and add them to your project.

## Mandatory Materials

**Videos**

1. [Reactive Forms - The Basics](https://www.youtube.com/watch?v=JeeUY6WaXiA)
2. [Typed Forms in Angular](https://youtu.be/L-odCf4MfJc)

**Reading**

- [Angular Forms](https://angular.dev/guide/forms)
- [Reactive Forms](https://angular.dev/guide/forms/reactive-forms) (focus on this)
- [First App: Forms](https://angular.dev/tutorials/first-app/12-forms)
- [Input Validation](https://v17.angular.io/guide/form-validation#validating-input-in-reactive-forms)
- [Forms tutorial](https://www.tutorialspoint.com/angular6/angular6_forms.htm)

## Online Shop:

> Add a new "Edit" button on the detail page. Pressing it should open a new view that uses reactive forms to update the product’s properties. The view should have two buttons: "Cancel" (which undoes all changes) and "Save" (which calls the backend to persist the changes).
>
> Add validation to your form (e.g., check that the fields are not empty, ensure that the price and weight inputs contain only numbers, etc.).
>
> Create a new "Add" button on the product list. Pressing this button should open a view for creating a new product, with the same structure and buttons as the edit view.

### Folder Structure

```text
├── src/app
│   ├── components
│   │   ├── products-form
│   │   │   ├── products-form.component.ts
│   │   │   ├── products-form.component.scss
│   │   │   ├── products-form.component.html
│.......<the previous files>................................
```

## Further Resources (Optional):

- [Custom form controls](https://blog.thoughtram.io/angular/2016/07/27/custom-form-controls-in-angular-2.html)
- [ControlValueAccessor](https://angular.io/api/forms/ControlValueAccessor)
