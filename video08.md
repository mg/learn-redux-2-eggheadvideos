# Using withRouter() to Inject the Params into Connected Components
[Video](https://egghead.io/lessons/javascript-redux-using-withrouter-to-inject-the-params-into-connected-components)

- 1. Remove ``({param})`` from ``App.jsx``
- 2. Use ``withRouter()`` decorator in ``VisibleTodoList`` component. This only works on version > 3.0.0 of React Router

```js
import { withRouter } from 'react-router'

const mapStateToProps= (state, { params }) => ({
  todos: getVisibleTodos(
    state.todos,
    params.filter || 'all', // params is injected by withRouter decorator
  )
})

const VisibleTodoList= withRouter(connect(
  mapStateToProps,
)(TodoList))
```
