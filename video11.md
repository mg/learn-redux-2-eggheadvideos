# Normalizing the State Shape
[Video](https://egghead.io/lessons/javascript-redux-normalizing-the-state-shape)

Change a array state into an object state using id's as keys.

Use ``combineReducers()`` anywhere in your application to compose your reducers.

Putting a dynamic key in object
```js
return  {
  ...state,
  [action.id]: todo(state[action.id], action)
}
```

Map an object to an array with a selector
```js
const getAllTodos= state => state.allIds.map(id => state.byId[id])
```
