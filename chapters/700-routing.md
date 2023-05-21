# 7. Routing [3h]

**Goal:** understand the basics of Angular Routing and add routing to your project

## Important Note

### Observables 
From this point on you will be likely working with something called `Observables` which are given by library called [RxJs](https://rxjs.dev)
- These are a continuous stream of data, which you will subscribe to get data. 
- Keep in mind that how the order events happen, the logic is not executed line by line since its asyncronous.
- You will need to unsubscribe them to avoid memory leaks. **KEEP IN MIND**
  - [Unsubscribe from RxJs Observables](https://www.thisdot.co/blog/best-practices-for-managing-rxjs-subscriptions)
- [Observables vs Promises](https://www.syncfusion.com/blogs/post/angular-promises-versus-observables.aspx)

## Mandatory Materials

**Videos**

1. [Angular Router - The Basics](https://www.youtube.com/watch?v=Np3ULAMqwNo)

**Reading**

- [Angular Routing](https://angular.io/guide/router#the-basics)
- [Tour of Heroes: Routing](https://angular.io/tutorial/toh-pt5)
- [First App: Routing](https://angular.io/tutorial/first-app/first-app-lesson-10)
- [Routing with Observables: Accessing query parameters and fragments](https://angular.io/guide/router#accessing-query-parameters-and-fragments)

## Online Shop:

> Add a button next to each product from the product list. You can use it to navigate to a specific product's detail page.
>
> From the detail page of the product, the user may add it to his shopping cart (by pressing a button).
>
> Add Routing to your project and implement a navigation between the list of all products and the product detail page. Use [`<router-outlet>`](https://angular.io/guide/router#router-outlet) as a placeholder for the currently displayed component in your app.
>
> Add a navigation which redirects users from the default path ('/') to the '/products' page and displays by default the list of all products.
>
> Enhance your app with routing parameters, such that you can navigate to a specific product's detail page. Hint: Use [`snapshot`](https://angular.io/guide/router#snapshot-the-no-observable-alternative) to capture the product's ID as a navigation parameter and display it in the details page.

### Folder Structure

```text
├── src/app
│   ├── app-routing.module
│   ....<the previous files>................................
```