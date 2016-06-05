# Filtering Redux State with React Router Params
[Video](https://egghead.io/lessons/javascript-redux-filtering-redux-state-with-react-router-params)

#### VisibleTodoList.jsx
```js
const mapStateToProps= (state, props) => ({
  todos: getVisibleTodos(
    state.todos,
    props.filter,
  )
})
```

#### App.jsx
```js
const App= ({params}) =>
  <div>
    <AddTodo/>
    <VisibleTodoList filter={params.filter || 'all'}/>
    <Footer/>
  </div>
```

#### server.js
Update express to serve the app on all paths
```js
app.get('/*', (req, res) => {
  res.sendFile(path.join(__dirname, 'index.html'))
})
```
