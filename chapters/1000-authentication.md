# 10. Authentication, Authorization and Guards [3h]

**Goal:** get familiar with Route Guards and protect your app's routes from unauthorized access.

## Mandatory Materials

**Videos**

1. [Session vs Token Authentication](https://www.youtube.com/watch?v=UBUNrFtufWo)
2. [Auth Interceptor](https://youtu.be/suTtA0Hlwlk)

**Reading**
- [Angular Interceptors](https://angular.io/guide/http#intercepting-requests-and-responses)
- [Auth Interceptor](https://medium.com/@ryanchenkie_40935/angular-authentication-using-the-http-client-and-http-interceptors-2f9d1540eb8)
    - Store the `jwt` token in [localstorage](https://developer.mozilla.org/en-US/docs/Web/API/Window/localStorage)
- [Route Guards](https://angular.io/guide/router-tutorial-toh#milestone-5-route-guards)

### Notes from the Mock Backend
- It uses JWT for authentication.
- Only the authentication module paths are secured.
    - `http://localhost:3000/api/auth/profile` needs a JWT token in the request headers for it to work.
    - The other API paths are not secured.
- Check `src/assets/users.json` for more information regarding already available users.

## Online Shop:

> Create a new login view, containing a text input for the username, a password input for the password and a login button.
>
> Add somewhere in your application information about the current logged-in user (call `/api/auth/profile`).
>
> Also add a logout button, which when called, removes the token from the localstorage and redirects the user to the login page.
>
> Automatically redirect the user to the login view each time he opens or refreshes the application. When pressing the login button, send an appropriate request to the backend. If the request succeeds, redirect the user to the product page, otherwise display an error message.
>
> Use the roles returned by the backend to disable the edit, create and delete buttons if the user is not an administrator. Only allow customers to view the shopping cart and to add products in it.

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

