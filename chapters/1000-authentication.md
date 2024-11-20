# 10. Authentication, Authorization and Guards [3h]

**Goal:** get familiar with Route Guards and protect your app's routes from unauthorized access.

## Mandatory Materials

**Videos**

1. [Session vs Token Authentication](https://www.youtube.com/watch?v=UBUNrFtufWo)
2. [Auth Interceptor](https://youtu.be/suTtA0Hlwlk)

**Reading**

- [Angular Interceptors](https://angular.dev/guide/http/interceptors)
- [Auth Interceptor](https://medium.com/@ryanchenkie_40935/angular-authentication-using-the-http-client-and-http-interceptors-2f9d1540eb8)
  - Store the `jwt` token in [localstorage](https://developer.mozilla.org/en-US/docs/Web/API/Window/localStorage)
- [Route Guards](https://angular.dev/guide/routing/common-router-tasks#preventing-unauthorized-access)

## Online Shop:

> Create a new login view with a text input for the username, a password input for the password, and a login button.
>
> When the login button is clicked, send the appropriate request to the backend. If the request is successful, redirect the user to the product page; otherwise, display an error message.
>
> Add a logout button that, when clicked, removes the token from local storage and redirects the user to the login page.
>
> Automatically redirect the user to the login view whenever a 401 response is received.
>
> Use the roles returned by the backend to disable the edit, create, and delete buttons if the user is not an administrator. Only allow customers to view the shopping cart and add products to it.
>
> Display information about the currently logged-in user somewhere in your application (e.g., header) (call `/api/auth/profile`).

### Folder Structure

```text
├── src/app
│   ├── guards
│   │   ├── auth.guard.ts
│   ├── interceptors
│   │   ├── auth.interceptor.ts
│   ├── services
│   │   ├── auth.service.ts
│   ├── modules
│       ├── shared
│           ├── types
│               ├── users.types
│.......<the previous files>................................
```

## Further Resources (Optional):

- [Angular Role-based Authorization](https://jasonwatmore.com/post/2018/11/22/angular-7-role-based-authorization-tutorial-with-example)
- [Angular Authentication: Using Route Guards](https://medium.com/@ryanchenkie_40935/angular-authentication-using-route-guards-bf7a4ca13ae3)
