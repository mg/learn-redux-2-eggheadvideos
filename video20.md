# Refactoring the Reducers
[Video](https://egghead.io/lessons/javascript-redux-refactoring-the-reducers)

####
Generating reducers
```js
const createList= filter => {
  return (state= [], action) => {
    if(action.filter !== filter) {
      return state
    }
    switch(action.type) {
      case 'RECIEVE_TODOS':
        return action.response.map(todo => todo.id)
      default:
        return state
    }
  }
}

const listByFilter= combineReducers({
  all: createList('all'),
  active: createList('active'),
  completed: createList('completed'),
})
```
