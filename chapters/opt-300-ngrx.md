# 11. Simple NgRx [8h]

**Goal:** Use NgRx for state management.

**Note:** Communicate with your mentor about this step, do no get stuck and try to do everything by yourself.

**Note:** Redux is usually used for medium to large scale projects, we will use it here for you to get an understanding of its fundamentals.

## Mandatory Materials

**Videos**

1. [NgRx Crash Course](https://www.youtube.com/watch?v=kx0VTgTtSBg)
2. [Original JS Redux](https://youtu.be/_shA5Xwe8_4) (a reference to the original Redux library)
3. [Ngrx Quickstart](https://youtu.be/f97ICOaekNU) (uses deprecated NgRx API)

**Reading**https://medium.com/@igorm573/state-management-with-ngrx-in-angular-66ddc61cdf14

- [State management with NgRx in Angular](https://medium.com/@igorm573/state-management-with-ngrx-in-angular-66ddc61cdf14)
- [NgRx: Store - Reducers, Actions](https://ngrx.io/guide/store)
- [NgRx: Effects](https://ngrx.io/guide/effects)
- [NgRx Docs](https://ngrx.io/docs)

## Online Shop:

> Add NGRX to your app by following these steps:
>
> - Create a reducer that manages the state for both products and the user.
> - Add actions for each user input handler, data loading event, etc.
> - Add effects to respond to data loading actions and call the necessary services.
> - Dispatch actions and select the state inside the components.
>
> Hints:
>
> - Include a loading flag indicator in each page's state to track loading status.
> - Install the [Redux DevTools](https://chrome.google.com/webstore/detail/redux-devtools/lmhkpmbekcpmknklioeibfkpmmfibljd?hl=en) Chrome plugin to debug your store.
> - Add the [Ngrx Store DevTools](https://ngrx.io/guide/store-devtools/install) to your application to enable DevTools functionality.

### Folder Structure

**Note**: The structure presented is for a brief understanding, the best practice will be to have a `state` folder per module.

```text
├── src/app
│   ├── app.state.ts
│   ├── modules
│       ├── shared
│           ├── state
│               ├── app.reducers.ts -- aggregates reducer, intialState and selectors. It has one reducer for user, products and shopping cart
│               ├── app.actions.ts
│               ├── app.effects.ts
│.......<the previous files>................................
```

## Further Resources (Optional):

- [NGRX Tips and Tricks](https://medium.com/@praveenpuglia/practical-ngrx-effects-tips-tricks-1935509c9fb6)
- [NGRX Example App](https://github.com/ngrx/platform/tree/master/projects/example-app/)
- [Redux from Scratch](https://youtu.be/hG7v7quMMwM)
