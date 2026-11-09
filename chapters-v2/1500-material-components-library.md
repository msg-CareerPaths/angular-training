# 15. Material Components [2h – 3h]

## Introduction

Writing every button, table, and dialog from scratch gets old quickly. **Angular Material** is a battle-tested component library with Google's Material Design built in. This chapter swaps some of the Online Shop's plain HTML for Material components.

## Goal

### Theory

By the end of this chapter you should be able to explain:

- What a component library is and why you'd use one.
- The Material Design principles at a high level.
- How Angular Material's components are imported (standalone — one import per component).
- How theming works (predefined palettes, dark mode, custom tokens).

### Practice

> [Install Angular Material](https://material.angular.dev/guide/getting-started) in the Online Shop: `ng add @angular/material`.
>
> Replace some plain HTML with Material components:
> - The product list → [`mat-table`](https://material.angular.dev/components/table/overview).
> - Buttons → [`mat-button`](https://material.angular.dev/components/button/overview).
> - The edit/add forms → [`mat-form-field`](https://material.angular.dev/components/form-field/overview) + [`mat-input`](https://material.angular.dev/components/input/overview).
> - Navigation → [`mat-toolbar`](https://material.angular.dev/components/toolbar/overview).

## Mandatory Materials

**Reading**

- [Material — introduction](https://m2.material.io/design/introduction)
- [Angular Material — getting started](https://material.angular.dev/guide/getting-started)
- [Angular Material — component catalog](https://material.angular.dev/components/categories)

## Testing

> Replace one plain button with a `mat-button` and update the DOM assertions in its test. Add a test covering the swapped-out `mat-table` renders the expected number of rows.
>
> Reference: [Material — component harnesses](https://material.angular.dev/guide/using-component-harnesses).

## Optional Resources

- [Theming Angular Material](https://material.angular.dev/guide/theming)
- [Component tokens](https://material.angular.dev/guide/theming#component-tokens)

### Alternative Styling Libraries (reference only)

- [Tailwind CSS](https://tailwindcss.com)
- [Angular + Tailwind](https://angular.dev/guide/tailwind)
- [Angular Bootstrap (`ng-bootstrap`)](https://ng-bootstrap.github.io/#/home)
- [PrimeNG](https://primeng.org/installation)
- [DaisyUI](https://daisyui.com/docs/install/)
