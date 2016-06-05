# Supplying the Initial State
[Video](https://egghead.io/lessons/javascript-redux-supplying-the-initial-state)

When creating the store, we can supply an initial state as the last parameter.

```js
const myPersistedState= {
  reducer1: {},
  reducer3: {},
}

const reducers= combineReducers(
  reducer1,
  reducer2,
  reducer3,
)

// initial state for reducer1 and reducer2 will be overridden by myPersistedState
const store= createStore(
  reducers,
  myPersistedState,
)
```
