# Using mapDispatchToProps() shorthand notation
[Video](https://egghead.io/lessons/javascript-redux-using-mapdispatchtoprops-shorthand-notation)

If the params match up, we can map this

```js
const mapDisptachToProps= dispatch =>({
  onTodoClick(id) {
    dispatch(toggleTodo(id))
  }
})
```

to this

```js
connect(
  mapStateToProps,
  { onTodoClick: toggleTodo }
)(TodoList)
```
