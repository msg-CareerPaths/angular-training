# 6. Signals [1 day]

## Introduction

Signals are Angular's native reactive primitive. They replace much of what you used to do with `@Input` getters, change-detection tricks, and hand-rolled Subjects.

**You've already been writing signal-based code.** The `input()` and `output()` you used in Chapter 5 are signals. This chapter zooms out, explains *why* they behave the way they do, and makes signals the center of the component model from here on. If you still have any lingering `@Input()` / `@Output()` decorators in a component you built earlier, now is the time to convert them to `input()` / `output()`.

A small bit of vocabulary first:

- A signal is **readable** — anything can call it (`count()`) to get the current value. All signals are readable.
- A signal is **writable** if you can change it (`count.set(1)`, `count.update(v => v + 1)`). `signal()` creates a writable signal.
- A signal is **derived (read-only)** if its value comes from other signals. `computed()` creates a read-only signal.

See the [Signals Cheat Sheet](#signals-cheat-sheet) at the end of this chapter for the APIs at a glance.

## Goal

### Theory

By the end of this chapter you should be able to explain:

- What a signal is.
- The three flavors: **writable**, **computed**, **linked**.
- Input signals, output signals, and model signals.
- What an **effect** is, and why effects are a last resort.
- `toSignal` / `toObservable` — the RxJS interop bridges.

  > **Note:** This point is hard to grasp without knowing RxJS, which is covered in the [next chapter](700-rxjs.md). Don't spend too much time on it here — a rough idea is enough (`toSignal`: Observable → Signal, `toObservable`: Signal → Observable). Move on to the RxJS chapter, where the interop will click.

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

**Writable (you can change the value):**

| Need                            | API                                   | Notes                                  |
| ------------------------------- | ------------------------------------- | -------------------------------------- |
| Local component state           | `const count = signal(0)`             | Default for anything you'll mutate.    |
| Model (two-way) input           | `value = model<string>('')`           | Parent and child both read + write.    |

**Read-only (anything can read, nothing can write):**

| Need                            | API                                                  | Notes                                             |
| ------------------------------- | ---------------------------------------------------- | ------------------------------------------------- |
| Derived value                   | `const double = computed(() => count() * 2)`         | Automatically updates when `count()` changes.            |
| Required input from parent      | `name = input.required<string>()`                    | Compile-time guarantee the parent passes it.      |
| Optional input w/ default       | `size = input<Size>('md')`                           | Returns `Signal<T>` with the fallback.            |
| From an Observable              | `data = toSignal(http.get<T>(url), { initialValue })`| Cleans up subscription automatically.             |

**Read / write actions:**

| Action                          | API                                                 |
| ------------------------------- | --------------------------------------------------- |
| Read                            | `count()`                                           |
| Set directly                    | `count.set(1)`                                      |
| Update from current             | `count.update(v => v + 1)`                          |

**Events out of the component:**

| Need                            | API                                                 |
| ------------------------------- | --------------------------------------------------- |
| Output signal                   | `clicked = output<MouseEvent>()` → `clicked.emit(e)` |

**Bridging RxJS (see [Chapter 7](700-rxjs.md)):**

| Direction                       | API                                                 |
| ------------------------------- | --------------------------------------------------- |
| Observable → Signal             | `toSignal(obs$, { initialValue })`                  |
| Signal → Observable             | `toObservable(sig)`                                 |

**Last resort:**

| Need                            | API                                                 |
| ------------------------------- | --------------------------------------------------- |
| Side effect on change           | `effect(() => console.log(count()))` *(avoid — see Rules)* |

### Further Reading

- [Resources](https://angular.dev/guide/signals/resource)
- [`afterNextRender` / `afterRender`](https://angular.dev/api/core/afterNextRender)
