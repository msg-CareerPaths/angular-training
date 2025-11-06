# 7. Signals [1 day]

**Goal:** Understanding signals and how they replace and enhance the application. 

We have used until now the old way of using the @Input and @Output decorators because some of the older apps you might work on still use them.

## Mandatory Materials

**Videos**

1. [Signals Explained Deeply](https://youtu.be/6W6gycuhiN0) (long video, but goes in full depth)
2. [Your first signal](https://youtu.be/KtEWoFElU9k)
3. [Signals Comeback](https://youtu.be/nQ2A30cD3Q8)

**Reading**

- [Signals Official Docs](https://angular.dev/guide/signals)
  -  [Writable Signals](https://angular.dev/guide/signals#writable-signals)
  -  [Computed Signals](https://angular.dev/guide/signals#computed-signals)
  -  [Linked Signals](https://angular.dev/guide/signals/linked-signal)
  -  [Input Signals](https://angular.dev/guide/components/inputs)
  -  [Output Signals](https://angular.dev/guide/components/outputs)
  -  [Effects](https://angular.dev/guide/signals#effects)
- [Signals Angular University Guide](https://blog.angular-university.io/angular-signals/)
  - [Signals for Components](https://blog.angular-university.io/angular-signal-components/) 
- [Injection Context](https://angular.dev/guide/di/dependency-injection-context)
- [Signals vs ngOnChanges](https://blog.logrocket.com/signals-vs-ngonchanges-angular-state-management/)

### Rules

- All your components should switch to an [OnPush](https://angular.dev/best-practices/skipping-subtrees) change detection strategy.
- All your components should use signals as much as possible going forward.
  - Use [RxJs Interops](https://angular.dev/ecosystem/rxjs-interop) when needed.
- Avoid using effects unless a common sense rule applies ([see this also](https://angular.dev/guide/signals#use-cases-for-effects):
```
    As per Angular Team:
    - Logging data being displayed and when it changes, either for analytics or as a debugging tool.
    - Keeping data in sync with window.localStorage.
    - Adding custom DOM behavior that can't be expressed with template syntax.
    - Performing custom rendering to a canvas, charting library, or other third party UI library.
    
    Other (maybe) valid use cases:
    
    - Fetching data from an API when a signal changes. (use untracked as safety net)
    - As a bridge between reactive context and non-reactive context (e.g.: updating form when signal changes)
```
- Don't use [resources](https://angular.dev/guide/signals/resource) (at the moment of writing they are still experimental)
- Use the [inject](https://angular.dev/api/core/inject) function going forward.


## Online Shop

>
> Convert all your app components so they are using signals wherever possible. This will be the way going forward.
>
