# 7. RxJS [3h]

## Introduction

RxJS is a library for working with **streams of values over time**. Before signals, it was the de-facto reactive primitive in Angular — every existing codebase you join will be full of it. Angular still uses it under the hood for `HttpClient`, forms' `valueChanges`, router params, and much more.

You just learned signals in Chapter 6; this chapter is the twin story. You won't write giant RxJS pipelines in this training — signals handle most of the UI reactivity — but you must be able to read RxJS, subscribe safely, and bridge it to signals (and vice-versa).

## Goal

### Theory

By the end of this chapter you should be able to explain:

- What an **Observable** is, and how it differs from a Promise.
- What **subscribing** and **unsubscribing** mean, and the memory leak that unsubscribing prevents.
- The three unsubscription strategies in Angular:
  - `takeUntilDestroyed()` *(preferred since v16)*,
  - the `| async` pipe in templates,
  - manual `Subscription.unsubscribe()` in `ngOnDestroy`.
- What a **Subject** is, and how **BehaviorSubject** relates to a signal.
- Common operators you will actually use: `map`, `filter`, `switchMap`, `tap`, `catchError`, `combineLatest`, `distinctUntilChanged`.
- Converting between RxJS and signals: `toSignal()` and `toObservable()`.
- Where you'll meet RxJS in Angular even if you write signal-first code: `HttpClient` return values (Chapter 9), form `valueChanges` (Chapter 10), router params (Chapter 8).

### Practice

> This chapter is exploration-only — nothing to merge into the Online Shop permanently. Work in a throwaway branch or a scratch component.
>
> **Exercise 1 — Observable vs signal.** In a scratch component (or `app.component.ts`), expose a `BehaviorSubject<number>` incremented by a button. Read it in the template two ways:
>
> - With `| async`.
> - With `toSignal(subject)` and render the signal in the template.
>
> Confirm both render the same value. Note that `toSignal` auto-cleans the subscription.
>
> **Exercise 2 — takeUntilDestroyed.** In the same scratch component, `subject.subscribe(v => console.log(v))` directly in a field initializer and chain `.pipe(takeUntilDestroyed())`. Destroy the component (navigate away or remove it from the template) and confirm the logging stops.
>
> **Exercise 3 — RxJS → signal → RxJS.** Create a `signal(0)`, convert it to an Observable with `toObservable()`, pipe it through `map(v => v * 2)`, and subscribe. Update the signal and watch the values flow.
>
> **Discard the branch.** You will not keep this code; the Online Shop stays signal-first. The point of the chapter is pattern recognition and the interop bridges — when you reach Routing in Chapter 8, you'll know that `ActivatedRoute.paramMap` is an Observable and *why* we still prefer signal inputs there.

#### Rules

- **Never** leave a subscription without a cleanup path. Use `takeUntilDestroyed()` or `| async` wherever possible.
- Prefer `toSignal()` to reading an Observable in the template with `| async` when the value drives component logic too.
- Inject services with the [`inject`](https://angular.dev/api/core/inject) function.

## Mandatory Materials

**Videos**

1. [RxJS in 100 Seconds](https://www.youtube.com/watch?v=ewcBfE2SwaM)
2. [Observables explained](https://youtu.be/Tux1nhBPl_w)

**Reading**

- [RxJS — overview](https://rxjs.dev/guide/overview)
- [Observables vs Promises](https://www.syncfusion.com/blogs/post/angular-promises-versus-observables.aspx)
- [Managing RxJS subscriptions](https://www.thisdot.co/blog/best-practices-for-managing-rxjs-subscriptions)
- [`takeUntilDestroyed`](https://angular.dev/ecosystem/rxjs-interop/take-until-destroyed)
- [`AsyncPipe`](https://angular.dev/api/common/AsyncPipe)
- [Subjects](https://www.learnrxjs.io/learn-rxjs/subjects) — note that a signal behaves most like a `BehaviorSubject`.
- [RxJS interop](https://angular.dev/ecosystem/rxjs-interop) — `toSignal`, `toObservable`, and when to reach for each.

## Testing

> Write a test for an Observable-driven value:
>
> - Create a small service with a `BehaviorSubject` exposing a count.
> - Build a tiny container that reads it via `toSignal`.
> - In the test, mutate the subject and assert the rendered value updated.

## Optional Resources

### RxJS Cheat Sheet (the subset you will actually use)

| Need                                    | Operator                                   |
| --------------------------------------- | ------------------------------------------ |
| Transform each value                    | `map(v => ...)`                            |
| Drop values that don't match            | `filter(v => ...)`                         |
| Swap to a new stream on each value      | `switchMap(v => http.get(...))`            |
| Side effect without changing the stream | `tap(v => console.log(v))`                 |
| Handle errors                           | `catchError(err => of(fallback))`          |
| Combine the latest of multiple          | `combineLatest([a$, b$])`                  |
| Skip duplicates                         | `distinctUntilChanged()`                   |
| Debounce                                | `debounceTime(300)`                        |
| Stop when component destroys            | `.pipe(takeUntilDestroyed())`              |

### Further Reading

- [RxJS Marble Diagrams](https://rxmarbles.com)
- [Learn RxJS](https://www.learnrxjs.io)
- [Angular `inject` function](https://youtu.be/_quyWq4NnRM) *(video)*
