## 7. Authentication, Authorization and Guards [3h]

**Goal:** get familiar with Route Guards and protect your app's routes from unauthorized access.

#### Required:

*Videos*

1. [Session vs Token Authentication](https://www.youtube.com/watch?v=UBUNrFtufWo)

*Reading*
- [Route Guards](https://angular.io/guide/router-tutorial-toh#milestone-5-route-guards)

*Notes*
- At this point, you will not have a Cookie or a JWT to use for authentication if you use the MockServer. You will need to keep the a `isLoggedIn` flag somewhere (for authentication persistance check [localStorage](https://developer.mozilla.org/en-US/docs/Web/API/Window/localStorage) and view the data in your Browser `Developer Tools/Application`).
- If you are testing this against a real backend which uses cookie session authentication, you can use the [HttpClient options parameters](https://angular.io/guide/http#requesting-data-from-a-server) `withCredentials?: boolean` on each of your requests to automatically *persist/send* the received cookies each time you send them.

#### Online Shop:

> Create a new login view, containing a text input for the username, a password input for the password and a login button.
>
> Automatically redirect the user to the login view each time he opens or refreshes the application. When pressing the login button, send an appropriate request to the backend. If the request succeeds, redirect the user to the product page, otherwise display an error message.
>
> Use the roles returned by the backend to disable the edit, create and delete buttons if the user is not an administrator. Only allow customers to view the shopping cart and to add products in it.

#### Further Resources (Optional):

- [Angular Role-based Authorization](https://jasonwatmore.com/post/2018/11/22/angular-7-role-based-authorization-tutorial-with-example)
- [Angular Authentication: Using Route Guards](https://medium.com/@ryanchenkie_40935/angular-authentication-using-route-guards-bf7a4ca13ae3)
- [Angular Interceptors](https://angular.io/guide/http#intercepting-requests-and-responses)
