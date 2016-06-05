# Fetching Data on Route Change
[Video](https://egghead.io/lessons/javascript-redux-fetching-data-on-route-change)

Use ``componentDidMount()`` and ``componentDidUpdate(prevProps)`` to fetch new data from server.

```js
class MyComponent extends React.Component {
  componendDidMount() {
    fetchData(this.props.filter).then(data => console.log(data))
  }

  componentDidUpdate(prevProps) {
    if(this.props.filter !=== prevProps.filter) {
      fetchData(this.props.filter).then(data => console.log(data))      
    }
  }
}
```
