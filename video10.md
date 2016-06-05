# Co-locating Selectors with Reducers
[Video](https://egghead.io/lessons/javascript-redux-colocating-selectors-with-reducers

The pattern is to
- 1. Export the **reducer** as the default export.
- 2. Export any functions that prepare the state for visual representation as a named export.

Thought: allow the **selector** to accept an optional **map** function that will map the data to JSX components


#### Selector co-located with a reducer
Both reducers and selectors work with a state object but do now know the mount point in the root state.

```js
export defult reducer

export const getVisisbleTodos= (state, filter) => {
  ...
}
```

#### State mount point selectors co-located with root reducer
```js
import { combineReducers } from 'redux'
import todos, { * as fromTodos } from './todo-reducer'

const appState= combineReducers({
  todos
})

export default appState

export const getVisibleTodos= (state, filter) => fromTodos.getVisibleTodos(state.todos, filter)
```

#### Use selector from root reducer in component
```js
import { getVisibleTodos } from 'app/reducers'

const mapStateToProps= (state, { params }) =>({
  todos: getVisibleTodos(state, params.filter || 'all'),
})
