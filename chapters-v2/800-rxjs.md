# 8. RxJS [3h]

## Introduction

RxJS is a library for working with **streams of values over time**. Angular uses it under the hood for `HttpClient`, forms' `valueChanges`, and router params. You will not write giant RxJS pipelines in this training — signals handle most of the UI reactivity — but you must be able to read RxJS, subscribe safely, and bridge it to signals.

This content used to live inside the Routing chapter. It's its own chapter now because RxJS is a distinct mental model worth a focused pass.

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
- Reading route params as Observables: `ActivatedRoute.paramMap`, `queryParamMap`.
- Converting between RxJS and signals: `toSignal()` and `toObservable()`.

### Practice

> Convert one route parameter read in your Online Shop from the signal-input form (Chapter 7) to an Observable form, and back. Keep the signal-input form as the final state — this is just to feel both shapes.
>
> Specifically:
>
> - In the product-detail component, inject `ActivatedRoute` with `inject(ActivatedRoute)`.
> - Subscribe to `paramMap` and log the id when it changes. Use `takeUntilDestroyed()` so the subscription cleans up with the component.
> - Rewrite that same code using `toSignal(route.paramMap)` and log via a `computed()`. Compare.
> - Revert to the signal-input approach from Chapter 7 for the actual app code.

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
- [Reading route state — observable form](https://angular.dev/guide/routing/read-route-state#reading-parameters-on-a-route)
- [RxJS interop](https://angular.dev/ecosystem/rxjs-interop)

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
