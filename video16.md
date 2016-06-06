# Wrapping Dispatch to Recognize Promises
[Video](https://egghead.io/lessons/javascript-redux-wrapping-dispatch-to-recognize-promises)

```js
const addPromiseSupportToDispatch= store => {
  const rawDispatch= store.dispatch
  return action => {
    if(typeof action.then === 'function') {
      return action.then(rawDispatch)
    }
    return rawDispatch(action)
  }
}
```
