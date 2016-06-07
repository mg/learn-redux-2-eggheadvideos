# Normalizing Api Responses with Normalizr
[Video](https://egghead.io/lessons/javascript-redux-normalizing-api-responses-with-normalizr))

#### schema.js
```js
import { Schema, arrayOf } from 'normalizr'

export const todo= new Schema('todos')
export const arrayOfTodos= arrayOf(todo)
```

#### actions.js
```js
import { normalizr } from 'normalizr'
import * as schema from './schema'

export const fetchTodos= filter => (dispatch, getState) => {
  return api.fetchTodos(filter).then(
    response => {
      normalize(response, schema.arrayOfTodos)
      dispatch({
        type: 'FETCH_TODOS_SUCCESS',
        filter,
        response: normalize(response, schema.arrayOfTodos),
      })
    },
    error => {
    },
  )
}

export const addTodo= text => dispatch =>
  api.addTodo(text).then(
    response => {
      dispatch({
        type: 'ADD_TODO_SUCCESS'
        response: normalize(response, schema.todo)
      })
    }
  )
```
