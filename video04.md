# Refactoring the Entry Point
[Video](https://egghead.io/lessons/javascript-redux-refactoring-the-entry-point)

#### configureStore.js
```js
import reducers from './reducers'
import { loadState, saveState } from './localeStorage'
export default const configureStore= () => {
  // rehydrate state
  // createStore()
  // setup save state
  return store
}
```

#### root.jsx
```js
import React from 'react'
import { Provider } from 'react-redux'
import App from './app'

const Root= ({store}) => (
  <Provider store={store}>
    <App/>
  </Provider>
)

export default Root
```

#### index.jsx
```js
import 'babel-polyfill'
import React from 'react'
import { render } from 'react-dom'
import configureStore from './app/configureStore'
import Root from './app/root'

const store= configureStore()

render(
  <Root store={store}/>,
  document.getElementById('app')
)
```
