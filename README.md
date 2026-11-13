# Angular Training (Angular 22)

Chapters here target **Angular 22** throughout — standalone components, signals, native control flow (`@if`, `@for`, `@switch`), `inject()`, functional interceptors and guards, and `@ngrx/signals` Signal Store.

Legacy conventions (`@Input`/`@Output` decorators, constructor DI, `*ngIf`/`*ngFor`, `NgModule`, class-based interceptors/guards, classical NgRx) are covered in a dedicated chapter so you can read older codebases without surprise — not written into every chapter.

## Chapter Template

Every chapter follows the same shape:

1. **Introduction** — short context for the chapter.
2. **Goal**
   - **Theory** — concepts you should be able to explain.
   - **Practice** — what to build in the *Online Shop* application.
     - Rules (optional)
     - Folder structure (optional)
3. **Mandatory Materials** — videos and reading.
4. **Testing** — what to test from this chapter (replaces the old standalone "Unit Testing" chapter).
5. **Optional Resources** — further reading, cheat sheets (RxJS / Signals where relevant).

## Mandatory Content

- [0. Introduction](chapters/0000-introduction.md)
- [1. Git Introduction](chapters/0100-git-introduction.md)
- [2. Web Basics](chapters/0200-the-web-basics.md)
- [3. HTML, CSS, JS Basics](chapters/0300-html-css-js-basics.md)
- [4. Angular Intro](chapters/0400-angular-intro.md)
- [5. Components](chapters/0500-components.md)
- [6. Signals](chapters/0600-signals.md)
- [7. RxJS](chapters/0700-rxjs.md)
- [8. Routing](chapters/0800-routing.md)
- [9. Services and HTTP Client](chapters/0900-services-and-http-client.md)
- [10. Forms and Validation](chapters/1000-forms-and-validations.md)
- [11. Authentication](chapters/1100-authentication.md)
- [12. State Management with NgRx Signal Store](chapters/1200-ngrx.md)
- [13. Legacy Angular Conventions](chapters/1300-legacy-angular-conventions.md)
- [14. Material Components](chapters/1400-material-components-library.md)

## Optional Content

No particular order is required.

- [Opt 1. Internationalization](chapters/opt-0100-internationalization.md)
- [Opt 2. Classical NgRx & Normalized State](chapters/opt-0200-normalized-ngrx.md)
- [Opt 3. E2E Testing](chapters/opt-0300-e2e-testing.md)
- [Opt 4. Component Library](chapters/opt-0400-component-library-development.md) *(deprecated)*
- [Opt 5. Nx Mono-repository](chapters/opt-0500-monorepository-nx.md) *(deprecated)*

## Other Content

- [Further Frontend Resources](chapters/others-0100-frontend-development-learn-more.md)

## What's New Compared to v1

- **Angular 22 default throughout** — no mixing of decorator inputs/outputs with signal inputs/outputs chapter by chapter.
- **RxJS is its own chapter**, placed right after Signals so students see them as a pair ([Chapter 7](chapters/0700-rxjs.md)). Routing can then prefer signal inputs and mention the Observable form as recognition-only.
- **Chapter 12 (NgRx)** leads with **`@ngrx/signals` Signal Store**; classical NgRx is optional material in [Opt 2](chapters/opt-0200-normalized-ngrx.md).
- **New [Chapter 13 — Legacy Angular Conventions](chapters/1300-legacy-angular-conventions.md)** — a guided tour of `@Input`/`@Output`, constructor DI, `*ngIf`/`*ngFor`, `NgModule`, class-based interceptors & guards. Throwaway-branch exercises only — nothing to merge.
- **Standalone vs Modules absorbed** — v1 had a dedicated Modules & Standalone chapter that overlapped with the Legacy chapter. In v2, standalone is the default from Chapter 5 and the NgModule contrast is a single exercise in Chapter 13.
- **Unit testing is no longer a standalone chapter.** Every chapter from 5 onward has a **Testing** subsection with what to test for that chapter's work. The former `opt-400` E2E chapter is now [Opt 3](chapters/opt-0300-e2e-testing.md).
- **Signals and RxJS cheat sheets** are embedded in Chapter 6 and Chapter 7 respectively.
