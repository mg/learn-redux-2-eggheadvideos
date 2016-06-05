# Dispatching Actions with the Fetched Data
[Video](https://egghead.io/lessons/javascript-redux-dispatching-actions-with-the-fetched-data)

####

```js
class MyComponent extends React.Component {
  componendDidMount() {
    this.fetchData()
  }

  componentDidUpdate(prevProps) {
    if(this.props.filter !=== prevProps.filter) {
      this.fetchData()
    }
  }

  fetchData() {
    fetchData(this.props.filter).then(data => {
      // dispatch an action that accepts data
    })
  }
}
```
