# 4. Angular Intro [4h]

## Introduction

This chapter gets Angular 22 onto your machine and your first project running. From here on, every chapter adds something to the Online Shop.

A habit to start now: **format your file on every save**. Both [VSCode](https://code.visualstudio.com/docs/editor/codebasics#_formatting) and [WebStorm](https://www.jetbrains.com/help/webstorm/reformat-and-rearrange-code.html) can do this. It avoids merge conflicts that are nothing but whitespace.

## Goal

### Theory

By the end of this chapter you should be able to explain:

- The difference between a Single Page Application and a Multi Page Application.
- What the Angular CLI is and what `ng new` scaffolds.
- Where to find the main building blocks in a freshly generated project (`main.ts`, `app.ts`, `app.config.ts`, `app.routes.ts`). You only need to know they exist; later chapters explain how each works.

### Practice

> Install the Angular CLI (uses Node.js npm): `npm install -g @angular/cli`.
>
> Create a new project in the root of your git repository: `ng new online-shop --style=scss`.
>
> `ng new` will prompt you for a few choices. **Pick these for this training:**
>
> - **Which stylesheet format?** → **SCSS** *(already set via `--style=scss`)*.
> - **Do you want to enable Server-Side Rendering (SSR) and Static Site Generation (SSG/Prerendering)?** → **No** — the Online Shop is a plain SPA; SSR adds complexity you don't need here.
> - **Which AI tools do you want to configure?** → **None** (skip for learning purposes).
>
> Navigate into the project folder, start the dev server, and open the home page in your browser: `ng serve --open`.
>
> Common `ng` commands you'll use throughout the training:
>
> - `ng generate component <name>` (or `ng g c <name>`) — scaffold a component.
> - `ng generate service <name>` (or `ng g s <name>`) — scaffold a service.
> - `ng serve` — run the dev server with hot reload.
> - `ng build` — produce a production bundle in `dist/`.
> - `ng test` — run the unit tests.

## Mandatory Materials

**Videos**

1. [Angular in 100 Seconds](https://www.youtube.com/watch?v=Ata9cSC2WpM)

**Reading**

- [Single vs Multiple Page Applications](https://medium.com/@NeotericEU/single-page-application-vs-multiple-page-application-2591588efe58)
- [Angular Installation](https://angular.dev/installation)
- [Angular Essentials](https://angular.dev/essentials)
- [Angular First App](https://angular.dev/tutorials/first-app) — **stop at tutorial 02 (Hello World)**. We'll cover components, control flow, services, and forms in dedicated chapters rather than following the full "first app" walkthrough.
- [Angular Style Guide](https://angular.dev/style-guide)
- [Angular Architecture Overview](https://angular.dev/overview)
- [Angular Testing Overview](https://angular.dev/guide/testing)

## Testing

> Nothing to test yet. Run `ng test` once to confirm Vitest runs — you'll write actual tests from Chapter 5 on.

## Optional Resources

- [Difference between AngularJS and Angular 2 / 4](https://www.simplilearn.com/angularjs-vs-angular-2-vs-angular-4-differences-article) — context for what "AngularJS" means vs modern Angular.
- [The evolution of Angular — key features v12 → v21](https://dev.to/mina_golzari_dalir/the-evolution-of-angular-key-features-and-benefits-from-version-12-to-21-12a) — how Angular got to the modern shape this training teaches.
