# 13. Legacy Angular Conventions [2h – 3h]

## Introduction

By now you've built the Online Shop entirely in the modern Angular 22 style: standalone components, signal inputs/outputs, native control flow, `inject()`, Signal Store. Great. But most real codebases you will join have years of history — you will open files that look nothing like what you've written here. This chapter is a guided tour of the legacy conventions so you can **read, debug, and touch** older code without surprise.

You are not expected to use these patterns in new code. You *are* expected to recognize them.

## Goal

### Theory

By the end of this chapter you should be able to explain:

- The `@Input()` / `@Output()` **decorator** form of component I/O, and how it differs from `input()` / `output()` signals.
- **Constructor dependency injection** (`constructor(private svc: Svc) {}`) vs `inject()`.
- The old **structural directives**: `*ngIf`, `*ngFor`, `*ngSwitch`, and their `else` / `let` tricks.
- Legacy pipes you still see everywhere: `| async`, `| json`, `| date`, `| uppercase`.
- `NgModule` basics — `declarations`, `imports`, `providers`, `exports` — and how a feature module hangs together.
- **Class-based** `HttpInterceptor` and **class-based** route guards (`CanActivate`), and why they were replaced by the functional forms.
- The old change-detection story: `ChangeDetectionStrategy.OnPush` was opt-in; `ChangeDetectorRef.markForCheck()` was common.
- Classical NgRx briefly (actions / reducers / effects / selectors) — see [Opt 2 — Classical NgRx & Normalized State](opt-200-normalized-ngrx.md).

### Practice

This is a reading-and-recognizing chapter. Do each exercise in a **throwaway branch** — do not merge it.

> **Exercise 1 — Decorator I/O.** Pick one leaf component and rewrite it using `@Input()` / `@Output() EventEmitter`. Note what you lose (type-inference-friendly `input.required()`, no required-input guarantee, `@Input() set x(v) { ... }` getter/setter dance for derived values).
>
> **Exercise 2 — Constructor injection.** In the same component (or a service), replace `inject(Svc)` with `constructor(private svc: Svc) {}`. Note the difference and the gotchas (injection context restrictions you *don't* have with constructor DI — but you lose the flexibility of injecting outside class-field context).
>
> **Exercise 3 — Structural directives.** Rewrite one template to use `*ngIf`, `*ngFor`, and `*ngSwitchCase` instead of `@if` / `@for` / `@switch`. Import `CommonModule` (or `NgIf`, `NgFor` individually) to make the directives available.
>
> **Exercise 4 — Legacy module.** Convert the shopping-cart feature back to an `NgModule` with `declarations`, `imports`, `exports` — mark its components `standalone: false`. See how many lines you added.
>
> **Exercise 5 — Class-based interceptor & guard.** Rewrite the auth interceptor as a class implementing `HttpInterceptor` and register it with `HTTP_INTERCEPTORS`. Rewrite the auth guard as a class implementing `CanActivate` and register it in `providers`.
>
> **Reset.** Delete the branch. Your main codebase stays modern.

#### Rules

- **Do not merge** these exercises. They exist to build pattern recognition.
- When you see these patterns in a real project, resist the urge to rewrite — follow the project's conventions.

## Mandatory Materials

**Reading**

- [`@Input` decorator — declaring inputs with the decorator](https://angular.dev/guide/components/inputs#declaring-inputs-with-the-input-decorator)
- [`@Output` decorator — declaring outputs with the decorator](https://angular.dev/guide/components/outputs#declaring-outputs-with-the-output-decorator)
- [Constructor vs `inject()` — Angular DI](https://angular.dev/guide/di/dependency-injection) — read the "class providers" & "injection context" sections.
- [Structural directives — the `*` syntax explained](https://angular.dev/guide/directives/structural-directives)
  - [`NgIf`](https://angular.dev/api/common/NgIf), [`NgFor`](https://angular.dev/api/common/NgFor), [`NgSwitch`](https://angular.dev/api/common/NgSwitch)
- [Common pipes](https://angular.dev/api/common) — `AsyncPipe`, `DatePipe`, `JsonPipe`, `UpperCasePipe`, etc.
- [NgModules overview](https://angular.dev/guide/ngmodules/overview)
- [Class-based `HttpInterceptor`](https://angular.dev/api/common/http/HttpInterceptor)
- [Class-based `CanActivate` guard](https://angular.dev/api/router/CanActivate)
- [`ChangeDetectorRef`](https://angular.dev/api/core/ChangeDetectorRef) — the hook you rarely need with signals.

**Videos**

- [Angular decorators explained](https://www.youtube.com/watch?v=O6P86uwfdR0) *(older but conceptually accurate)*
- [Standalone Components (why Angular moved away from NgModules)](https://youtu.be/x5PZwb4XurU)

## Testing

> Pick one of your exercises above (e.g. the decorator-input component) and write a test for it. Notice what changes between testing a signal input vs a decorator input (`fixture.componentRef.setInput('x', ...)` vs `component.x = ...`).

## Optional Resources

### Side-by-side cheat sheet

| Modern (Angular 22)              | Legacy equivalent                                   |
| -------------------------------- | --------------------------------------------------- |
| `name = input.required<string>()`| `@Input({ required: true }) name!: string`          |
| `clicked = output<Event>()`      | `@Output() clicked = new EventEmitter<Event>()`     |
| `svc = inject(Svc)`              | `constructor(private svc: Svc) {}`                  |
| `@if (open) { ... }`             | `<div *ngIf="open"> ... </div>`                     |
| `@for (p of items; track p.id)`  | `<div *ngFor="let p of items; trackBy: trackById">` |
| `@switch (x) { @case (1) {} }`   | `<div [ngSwitch]="x"><div *ngSwitchCase="1">`       |
| Standalone component + `imports:`| `NgModule.declarations` + `NgModule.imports`        |
| `provideHttpClient(withInterceptors([authFn]))` | `providers: [{ provide: HTTP_INTERCEPTORS, useClass: AuthInterceptor, multi: true }]` |
| `CanActivateFn` (function)       | `class AuthGuard implements CanActivate`            |
| Signal Store (`@ngrx/signals`)   | `Store` + actions + reducers + effects + selectors  |

### Further Reading

- [Angular changelog highlights](https://github.com/angular/angular/blob/main/CHANGELOG.md) — skim to see when each modern API landed.
- [`ngFor` with `trackBy`](https://angular.dev/api/common/NgForOf#trackBy) — `trackBy` is why `@for` requires `track`.
