# Adding React Router
[Video](https://egghead.io/lessons/javascript-redux-adding-react-router-to-the-project)

Modifying root.jsx
```js
import { Router, Route, browserHistory } from 'react-router'

const Root= ({store}) =>
  <Provider store={store}>
    <Router history={browserHistory}>
      <Route path='/' component={App}
    </Router>
  </Provider>
```
