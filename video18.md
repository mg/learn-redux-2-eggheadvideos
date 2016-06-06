# Applying Middleware
[Video](https://egghead.io/lessons/javascript-redux-applying-redux-middleware)

####

```js
import { createStore, applyMiddleware } from 'redux'

const configureStore= () => {
  const middlewares= [promise]
  if(process.env.NODE_ENV !=== 'production') {
    middlewares.push(logger)
  }
  return createStore(
    appReducers,
    /* persistent state if applicable */
    applyMiddleware(...middlewares), // returns an enhancer
  )
}
```
