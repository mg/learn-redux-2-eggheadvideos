# Wrapping dispatch() to Log Actions
[Video](https://egghead.io/lessons/javascript-redux-wrapping-dispatch-to-log-actions)

In configureStore.js
```js
const addLoggingToDispatch= store => {
  const rawDispatch= store.dispatch
  if(!console.group || process.NODE_ENV !== 'production') {
    return rawDispatch
  }
  return action => {

    console.group(action.type)
    console.log('%c prev state', 'color: gray', store.getState())
    console.log('%c action', 'color: blue', action)
    const returnValue= rawDispatch(action)
    console.log('%c next state', 'color: green', store.getState())
    console.groupEnd(action.type)    
    return returnValue
  }
}

store.dispatch= addLoggingToDispatch(store)
```
