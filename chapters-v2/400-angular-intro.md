# 4. Angular Intro [4h]

## Introduction

This chapter gets Angular 22 onto your machine and your first project running. From here on, every chapter adds something to the Online Shop.

A habit to start now: **format your file on every save**. Both [VSCode](https://code.visualstudio.com/docs/editor/codebasics#_formatting) and [WebStorm](https://www.jetbrains.com/help/webstorm/reformat-and-rearrange-code.html) can do this. It avoids merge conflicts that are nothing but whitespace.

## Goal

### Theory

By the end of this chapter you should be able to explain:

- The difference between a Single Page Application and a Multi Page Application.
- What the Angular CLI is and what `ng new` scaffolds.
- The top-level architecture of an Angular app (standalone bootstrap, components, services, routes).
- Why Angular 22 defaults to standalone components and OnPush change detection.

### Practice

> Install the Angular CLI (uses Node.js npm): `npm install -g @angular/cli`.
>
> Create a new project in the root of your git repository: `ng new online-shop --style=scss`.
>
> Navigate into the project folder, start the dev server, and open the home page in your browser: `ng serve --open`.

## Mandatory Materials

**Videos**

1. [Angular in 100 Seconds](https://www.youtube.com/watch?v=Ata9cSC2WpM)

**Reading**

- [Single vs Multiple Page Applications](https://medium.com/@NeotericEU/single-page-application-vs-multiple-page-application-2591588efe58)
- [Angular Installation](https://angular.dev/installation)
- [Angular Essentials](https://angular.dev/essentials)
- [Angular First App 01](https://angular.dev/tutorials/first-app)
- [Angular Style Guide](https://angular.dev/style-guide)
- [Angular Architecture Overview](https://angular.dev/overview)

## Testing

> Nothing to test yet. Run `ng test` once to confirm Karma/Jasmine boots — you'll write actual tests from Chapter 5 on.

## Optional Resources

- [Difference between AngularJS and Angular 2 / 4](https://www.simplilearn.com/angularjs-vs-angular-2-vs-angular-4-differences-article) — context for what "AngularJS" means vs modern Angular.
