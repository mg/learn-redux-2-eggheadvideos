# Persisting State to Locale Storage
[Video](https://egghead.io/lessons/javascript-redux-persisting-the-state-to-the-local-storage)

#### localeStorage.js
```js
export const loadState= () => {
  try {
    const serializedState= localStorage.getItem('state')
    if(serializedState === null) {
      return undefined
    }
    return JSON.parse(serializedState)
  } catch(err) {
    return undefined
  }
}

export const saveState= state => {
  try {
    const serializedState= JSON.stringify(state)
    localStorage.setItem('state', serializedState)
  } catch(err) {
    // ignore
  }
}
```
How to handle immutable.js?
- Object.keys() => toJS() => JSON.stringify()
- JSON.parse() => Object.keys() => fromJS()
- or use [Redux Immutable](https://github.com/gajus/redux-immutable)

### Use State from Locale Storage
```js
import throttle from 'lodash/throttle'
import { loadState, saveState } from './localeStorage'

// rehydrate state from locale storage
const persistedState= loadState()

// create store
const store= createStore(
  reducers,
  persistedState,
)

// save all state ...
store.subscribe(throttle(() => saveState(store.getState()), 1000)

// or only save some reducers
store.subscribe(throttle(() => {
  const state= store.getState()
  saveState({
    r1: state.r1,
    r2: state.r2,
  })
}), 1000)
```

#### node-uuid
A package to generate unique id's in UI code.
```js
import { v4 } from 'node-uuid'
v4() // -> unique hash string
```
