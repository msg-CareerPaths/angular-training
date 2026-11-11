# 9. Services and the HTTP Client [3h]

## Introduction

Services hold the logic that doesn't belong in a component - loading data, managing cross-component state, calling the backend. Angular's `HttpClient` is how you talk to HTTP APIs. In Angular 22 you lean on signals (`toSignal`, `httpResource`) or Observables (`HttpClient` methods return them), depending on the shape of the data.

## Goal

### Theory

By the end of this chapter you should be able to explain:

- What a service is, and how `@Service()` registers it at the root injector by default.
- How Angular's dependency injection resolves a service.
- How `HttpClient` returns `Observable`s, and how to turn them into signals with `toSignal`.
- How to configure the API base URL via `src/environments/`.
- What an **injection context** is and why `inject()` works in a class field initializer or a constructor.

### Practice

The logic you write here belongs in **container** components, not presentational ones.

> `ng generate environments` to create `src/environments/environment*.ts`.
>
> Put an `apiUrl` property in `src/environments/environment.ts` pointing at the mock backend.
>
> Create a `ProductsService`(generated with Angular CLI) that uses `inject(HttpClient)` and exposes:
> - `getAll()` → `Observable<Product[]>`
> - `getOne(id: string)` → `Observable<Product>`
> - `delete(id: string)` → `Observable<void>`
>
> *(You'll add `create()` and `update()` in [Chapter 10](1000-forms-and-validations.md), when the forms need them.)*
>
> In the products-list container, read all products via `toSignal(service.getAll(), { initialValue: [] })` and pass the signal to the presentational list.
>
> Now that data comes from the backend, delete `src/app/features/products/products.mocks.ts` and the mock imports you added in [Chapter 5](500-components.md).
>
> In the detail container, read the product by id the same way.
>
> Add a "Delete" button on the detail page that calls `delete()` and navigates back to the list.
>
> Create a `ShoppingCartService` with a `checkout()` method that creates an order to the backend. Wire it to a "Checkout" button on the cart page. The cart's items stay in the client for now; you'll move that state into a store in [Chapter 12](1200-ngrx.md).

#### Rules

- Services use **`@Service()`**.
- Use `inject()` for dependencies — not constructor parameters.
- Avoid subscribing manually in components. Prefer `toSignal()` or the `| async` pipe.

#### Folder Structure

```text
├── src
│   ├── environments
│   │   ├── environment.ts
│   │   ├── environment.development.ts
│   ├── app
│       ├── features
│           ├── products
│           │   ├── products.service.ts
│           │   ├── products.service.spec.ts
│           ├── shopping-cart
│               ├── shopping-cart.service.ts
│               ├── shopping-cart.service.spec.ts
│.......<the previous files>................................
```

## Mandatory Materials

**Videos**

1. [Angular HTTP Client Quick Start](https://www.youtube.com/watch?v=_05v0mrNLh0)

**Reading**

- [Quick start guide](https://blog.angular-university.io/angular-http/)
- [Creating a service](https://angular.dev/guide/di/creating-and-using-services)
- [Dependency Injection](https://angular.dev/guide/di)
- [Angular HTTP](https://angular.dev/guide/http)
- [Environment files](https://angular.dev/tools/cli/environments)
- [RxJS interop for signals](https://angular.dev/ecosystem/rxjs-interop)
- [DI explained in Angular](https://blog.logrocket.com/how-dependency-injection-works-in-angular/)
- [Injection context](https://angular.dev/guide/di/dependency-injection-context)

## Testing

> Add a test for `ProductsService`:
>
> - Use `HttpTestingController` to return a fake response for `getAll()`, then check the service returns the expected products.
> - Assert the correct URL and verb for `delete(id)`.
>
> Add a test for a container using the service:
>
> - Provide a stub service with a `getAll()` returning an in-memory array.
> - Assert the list renders N rows and that delete triggers the right service call.
>
> Reference: [Testing HTTP requests](https://angular.dev/guide/http/testing).

## Optional Resources

- [HTTP error handling](https://angular.dev/guide/http/making-requests#handling-request-failure)
- [Proxying to a backend server](https://angular.dev/tools/cli/serve#proxying-to-a-backend-server)
- [HTTP Interceptor](https://angular.dev/guide/http/interceptors)
- [Injection Tokens](https://angular.dev/guide/di/defining-dependency-providers#injection-tokens)
- [`httpResource` (Angular 22)](https://angular.dev/guide/http/http-resource) — signal-first HTTP for reactive loading.
