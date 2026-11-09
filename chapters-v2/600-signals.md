# 6. Signals [1 day]

## Introduction

Signals are Angular's native reactive primitive. They replace much of what you used to do with `@Input` getters, change-detection tricks, and hand-rolled Subjects. You've already been using `input()` and `output()` — those are signals. This chapter zooms out and makes them the center of the component model.

## Goal

### Theory

By the end of this chapter you should be able to explain:

- What a signal is (a value with a known reader) and why it changes rendering.
- The three flavors: **writable** (`signal`), **computed** (`computed`), **linked** (`linkedSignal`).
- Input signals (`input()`, `input.required()`), output signals (`output()`), and model signals (`model()`).
- What an **effect** is, and why effects are a last resort.
- `toSignal` / `toObservable` — the RxJS interop bridges.
- Why Angular 22 defaults to **OnPush** change detection and what that implies.
- What an **injection context** is (why `inject()` and `effect()` must be called inside one).

### Practice

> Convert all your components to use signals wherever possible. From here on, this is the default.
>
> - Component state → `signal()`.
> - Derived state → `computed()`.
> - Child → parent → `output()`.
> - Parent → child → `input()` / `input.required()`.

#### Rules

- All your components should be on **OnPush** change detection. In Angular 22 this is the default — keep it that way.
- Signals wherever possible.
- Use [RxJS interop](https://angular.dev/ecosystem/rxjs-interop) (`toSignal`, `toObservable`) where you need to cross the RxJS boundary.
- Avoid `effect()` unless the use case warrants it. From the Angular team:

  ```text
  Good use cases for effects:
    - Logging a value for analytics or debugging.
    - Keeping data in sync with window.localStorage.
    - Custom DOM behavior that can't be expressed in the template.
    - Rendering to a canvas or third-party UI library.

  Edge-case but sometimes valid:
    - Fetching data from an API when a signal changes (wrap sensitive reads in `untracked`).
    - Bridging reactive and non-reactive contexts (e.g. syncing a form control).
  ```

- [Resources](https://angular.dev/guide/signals/resource) are stable as of Angular 22 — use them for async data derived from signals.
- Use the [`inject`](https://angular.dev/api/core/inject) function for dependencies from here on, not constructor injection.

## Mandatory Materials

**Videos**

1. [Signals Explained Deeply](https://youtu.be/6W6gycuhiN0) *(long, but thorough)*
2. [Your first signal](https://youtu.be/KtEWoFElU9k)
3. [Signals Comeback](https://youtu.be/nQ2A30cD3Q8)

**Reading**

- [Signals — official docs](https://angular.dev/guide/signals)
  - [Writable signals](https://angular.dev/guide/signals#writable-signals)
  - [Computed signals](https://angular.dev/guide/signals#computed-signals)
  - [Linked signals](https://angular.dev/guide/signals/linked-signal)
  - [Input signals](https://angular.dev/guide/components/inputs)
  - [Output signals](https://angular.dev/guide/components/outputs)
  - [Effects](https://angular.dev/guide/signals#effects)
- [Angular University guide to signals](https://blog.angular-university.io/angular-signals/)
  - [Signals for components](https://blog.angular-university.io/angular-signal-components/)
- [Injection Context](https://angular.dev/guide/di/dependency-injection-context)
- [Signals vs ngOnChanges](https://blog.logrocket.com/signals-vs-ngonchanges-angular-state-management/)

## Testing

> Add a test that exercises a `computed()` signal:
>
> - Set up a component with a writable signal and a derived `computed()`.
> - In the test, update the writable signal and assert the computed value and the rendered DOM both reflect the change after `fixture.detectChanges()`.

## Optional Resources

### Signals Cheat Sheet

| What                          | API                              |
| ----------------------------- | -------------------------------- |
| Create writable state         | `const count = signal(0)`        |
| Read a signal                 | `count()`                        |
| Write                         | `count.set(1)` / `count.update()` |
| Derive                        | `const double = computed(() => count() * 2)` |
| Required input                | `name = input.required<string>()` |
| Optional input w/ default     | `size = input<Size>('md')`       |
| Model (two-way) input         | `value = model<string>('')`      |
| Output                        | `clicked = output<MouseEvent>()` |
| From Observable               | `data = toSignal(http.get<T>(url))` |
| To Observable                 | `toObservable(count)`            |
| Side effect                   | `effect(() => console.log(count()))` *(avoid)* |

### Further Reading

- [Resources](https://angular.dev/guide/signals/resource)
- [`afterNextRender` / `afterRender`](https://angular.dev/api/core/afterNextRender)
