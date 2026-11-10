# 10. Forms and Validation [3h]

## Introduction

This chapter uses **Reactive Forms** for the Online Shop. Reactive Forms are what nearly every existing Angular codebase uses and what a mentor reviewing your code will expect. Angular 22 also ships **Signal Forms** — you'll explore them at the end of the chapter as an optional dive.

## Goal

### Theory

By the end of this chapter you should be able to explain:

- The difference between Template-driven and Reactive Forms (and why we use Reactive here).
- `FormGroup`, `FormControl`, and `FormArray`, and how typed forms work.
- Built-in validators (`required`, `min`, `max`, `pattern`) and how to write a custom one.
- How to subscribe to `valueChanges` safely (recall Chapter 7 — use `takeUntilDestroyed()` or `| async`).
- How to display validation errors and how to submit a form.

### Practice

The logic lives in **container** components; the view lives in the **presentational** sibling.

> **Extend `ProductsService` first.** In [Chapter 9](900-services-and-http-client.md) you added `getAll()`, `getOne()`, and `delete()`. Add the two methods this chapter's forms need: `create()` and `update()`.
>
> Add an "Edit" button on the product detail page. Clicking it opens a view using a reactive form to update the product. The view has:
> - **Cancel** — discards all changes.
> - **Save** — calls new services to persist, then navigates back.
>
> Validate: fields are non-empty, price and weight contain only numbers, price > 0, etc.
>
> Add an "Add" button on the product list. Clicking it opens a view with the same shape and buttons for creating a new product.

#### Folder Structure

```text
├── src/app
│   ├── components
│   │   ├── containers
│   │   │   ├── products-form
│   │   │   │   ├── products-form.ts
│   │   │   │   ├── products-form.scss
│   │   │   │   ├── products-form.html
│   │   ├── presentational
│   │       ├── products-form-view
│   │       │   ├── products-form-view.ts
│   │       │   ├── products-form-view.scss
│   │       │   ├── products-form-view.html
│.......<the previous files>................................
```

## Mandatory Materials

**Videos**

1. [Reactive Forms — The Basics](https://www.youtube.com/watch?v=JeeUY6WaXiA)
2. [Typed Forms in Angular](https://www.youtube.com/watch?v=L-odCf4MfJc)

**Reading**

- [Forms overview](https://angular.dev/guide/forms)
- [Reactive Forms](https://angular.dev/guide/forms/reactive-forms) *(focus here)*
- [Angular First App 12: Forms](https://angular.dev/tutorials/first-app/12-forms)
- [Form validation](https://angular.dev/guide/forms/form-validation)
- [FormGroup / FormControl in Angular](https://blog.logrocket.com/formgroup-formcontrol-angular/)

## Testing

> Add a test for the products-form container:
>
> - Build the form with an initial value and assert all controls hold the right data.
> - Clear a required field, assert the form is invalid and the control's `errors` reflect it.
> - Submit a valid form, assert the service call was made with the right payload.

## Optional Resources

- [Custom form controls](https://blog.thoughtram.io/angular/2016/07/27/custom-form-controls-in-angular-2.html)
- [ControlValueAccessor](https://angular.dev/api/forms/ControlValueAccessor)

### Optional: Explore Signal Forms (Angular 22)

Angular 22 ships **Signal Forms**, a newer forms API built on signals. Once your Reactive Forms implementation is working, use this as a side exploration — **do not replace** your Reactive Forms with it.

**Recommended Reading**

- [Signal Forms — overview](https://angular.dev/guide/forms/signals/overview)
- [Signal Forms — form models](https://angular.dev/guide/forms/signals/models)
- [Signal Forms — validation](https://angular.dev/guide/forms/signals/validation)
- [Signal Forms — comparison with other form systems](https://angular.dev/guide/forms/signals/comparison)
- [Signal Forms playground](https://angular.dev/playground?templateId=4-signal-forms) — live runnable Signal Forms example on angular.dev.

**Optional Exercise**

Build a small version of the product form using Signal Forms. Focus on:

- How form models are created.
- How form fields are connected to the template.
- How validation rules are defined.
- How validation errors are displayed.
- How the form is submitted.

Compare the two implementations.
