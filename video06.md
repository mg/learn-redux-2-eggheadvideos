# Navigating with React Router Link
[Video](https://egghead.io/lessons/javascript-redux-navigating-with-react-router-link)

#### Adding optional filter to path
```js
<Route path='/(:filter)' component={App}/>
```

#### Component that generates navigation links
```js
import React from 'react'
import { Link } from 'react-router'

export const FilterLink= ({filter, children}) =>
  <Link
    to={filter === 'all' ? '' : filter}
    activeLink={{
      textDecoration: 'none',
      color: 'black',
    }}
  >
    {children}
  </Link>

export default FilterLink
```
 
