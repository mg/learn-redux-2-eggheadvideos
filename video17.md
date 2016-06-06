# The Middleware Chain
[Video](https://egghead.io/lessons/javascript-redux-the-middleware-chain)

####

```js
const wrapDispatchWithMiddlewares= (store, middlewares) => {
  middlewares.slice().reverse().forEach(middleware => {
    store.dispatch= middleware(store)(store.dispatch)
  })
}
```

##### Logger Middleware
```js 
const logger= store => next => {
  if(!console.group || process.NODE_ENV !== 'production') {
    return next
  }

  return action => {
    console.group(action.type)
    console.log('%c prev state', 'color: gray', store.getState())
    console.log('%c action', 'color: blue', action)
    const returnValue= next(action)
    console.log('%c next state', 'color: green', store.getState())
    console.groupEnd(action.type)    
    return returnValue
  }
}
```

##### Promise Middleware
```js
const promise= store => next => action => {
  if(typeof action.then === 'function') {
    return action.then(next)
  }
  return next(action)
}
```
