# Avoiding Race Conditions with Thunks
[Video](https://egghead.io/lessons/javascript-redux-avoiding-race-conditions-with-thunks)

Use a selector function to query the state to see if the state is already loading.

```js
export const action= filter => {
  return (dispatch, getState) => {
    // guard, if already loading then exit early
    if(getIsFetching(getState(), filter)) {
      return Promise.resolve()
    }

    // continue with action
  }
}
```
