# 11. Authentication, Authorization and Guards [3h]

## Introduction

The mock backend uses JWT. This chapter adds a login view, stores the token, attaches it to outgoing requests via an **HTTP interceptor**, protects routes with a **functional route guard**, and uses the user's role to toggle features in the UI.

## Goal

### Theory

By the end of this chapter you should be able to explain:

- The difference between authentication (who you are) and authorization (what you may do).
- The difference between session and token authentication.
- How a JWT travels from login → localStorage → request header → backend.
- What a **functional interceptor** is (`HttpInterceptorFn`) and how it differs from the old class-based one.
- What a **functional route guard** is (`CanActivateFn`) and when it runs.
- Why storing tokens in `localStorage` is pragmatic here but not ideal for production.

### Practice

> Create a login view: username input, password input, login button. Register its `/login` route in `app.routes.ts`.
>
> On successful login, store the JWT in `localStorage` and redirect to `/products`. On failure, show an error.
>
> Show the current user somewhere in the UI by calling `/api/auth/profile`.
>
> Add a logout button that clears the token and redirects to `/login`.
>
> Register a **functional HTTP interceptor** in `app.config.ts` that:
> - Attaches `Authorization: Bearer <token>` if a token exists.
> - On a 401 response, clears the token and redirects to `/login`.
>
> Register a **functional route guard** that blocks access to app routes when no token is present. Leave `/login` public so a logged-out user can still reach it.
>
> Use the backend's roles to enable/disable the edit, create, and delete buttons. Only customers can view the cart and add to it.

#### Rules

- Interceptors and guards are **functional** per the modern style guide.
- Store `jwt` in [`localStorage`](https://developer.mozilla.org/en-US/docs/Web/API/Window/localStorage).

#### Folder Structure

```text
├── src/app
│   ├── core                        -- app-wide singletons
│   │   ├── guards
│   │   │   ├── auth.guard.ts
│   │   │   ├── auth.guard.spec.ts
│   │   ├── interceptors
│   │   │   ├── auth.interceptor.ts
│   │   │   ├── auth.interceptor.spec.ts
│   │   ├── services
│   │       ├── auth.service.ts
│   │       ├── auth.service.spec.ts
│   ├── features
│   │   ├── auth
│   │       ├── login               -- login container + view
│   │           ├── login.ts
│   │           ├── login.scss
│   │           ├── login.html
│   │           ├── login.spec.ts
│   ├── shared
│       ├── types
│           ├── users.types.ts      -- User/Role model, used across features
│.......<the previous files>................................
```

### Notes from the Mock Backend

- JWT-based authentication.
- Only the auth paths are secured. `/api/auth/profile` needs the JWT header; other endpoints don't.
- `src/assets/users.json` in the mock backend lists available users.

## Mandatory Materials

**Videos**

1. [Session vs Token Authentication](https://www.youtube.com/watch?v=UBUNrFtufWo)
2. [Auth Interceptor](https://youtu.be/suTtA0Hlwlk)

**Reading**

- [Angular Interceptors](https://angular.dev/guide/http/interceptors) — focus on the functional `HttpInterceptorFn` form.
- [Auth Interceptor](https://medium.com/@ryanchenkie_40935/angular-authentication-using-the-http-client-and-http-interceptors-2f9d1540eb8) *(older but conceptually solid)*.
- [Route Guards](https://angular.dev/guide/routing/route-guards) — focus on the functional `CanActivateFn` form.

## Testing

> Add a test for the functional interceptor:
>
> - Register it via `provideHttpClient(withInterceptors([authInterceptor]))` in `TestBed`.
> - Fire a request through `HttpClient` with a token in storage; assert the `Authorization` header on the outgoing request.
> - Simulate a 401 and assert the token is cleared and navigation happened.
>
> Add a test for the functional guard:
>
> - Call it with a stub `Router`; assert it returns `true` when a token exists and a redirect `UrlTree` when it doesn't.

## Optional Resources

- [Angular Role-based Authorization](https://jasonwatmore.com/post/2018/11/22/angular-7-role-based-authorization-tutorial-with-example)
- [OWASP: JWT best practices](https://cheatsheetseries.owasp.org/cheatsheets/JSON_Web_Token_for_Java_Cheat_Sheet.html)
