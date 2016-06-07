# Dispatching Actions Asynchronously with Thunks
[Video](https://egghead.io/lessons/javascript-redux-dispatching-actions-asynchronously-with-thunks)

##### The Thunk Middleware
```js
const thunk= store => next => action =>
  typeof action === 'function' ?
    action(store.dispatch) :
    next(action)
```
