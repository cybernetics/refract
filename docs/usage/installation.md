# Installation

Refract is available for a number of reactive programming libraries. For each library, a Refract integration is available for both React and Redux.

Available packages:

| | [React](https://github.com/facebook/react) | [Redux](https://github.com/reduxjs/redux) |
| --- | --- | --- |
| **[Callbag](https://github.com/callbag/callbag)** | refract-callbag | refract-redux-callbag |
| **[Most](https://github.com/cujojs/most)** | refract-most | refract-redux-most |
| **[RxJS](https://github.com/reactivex/rxjs)** | refract-rxjs | refract-redux-rxjs |
| **[xstream](https://github.com/staltz/xstream)** | refract-xstream | refract-redux-xstream |

The examples below assume you're using `RxJS` - if you're using a different library, use the table above to find the correct package names.

## React Packages

The React packages don't require much set up - you just need to install the package (usually via `npm` or `yarn`):

```
npm install --save refract-rxjs
```

## Redux Packages

The Redux packages involve an extra step to apply the Refract enhancer to your Redux store:

1. Install the latest stable version (again usually via `npm` or `yarn`):

    ```
    npm install --save refract-redux-rxjs
    ```

1. Import the Refract store enhancer and apply it to your redux store. This process is explained in detail in the Redux documentation: [`Configuring your store`](https://redux.js.org/recipes/configuring-your-store).

    For example:

    ```js
    import { compose, createStore } from 'redux'
    import { refractEnhancer } from 'refract-redux-rxjs'

    import reducers from './store'

    const store = createStore(reducers, {}, refractEnhancer())

    export default store
    ```

    _(Note that this example is unrealistically simple!)_