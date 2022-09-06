# Redux - Asynchronous Actions
## Redux Middleware and Side Effects​

It only knows how to synchronously dispatch actions, update the state by calling the root reducer function, and notify the UI that something has changed. Earlier, we said that Redux reducers must never contain «side effects». However, any real app will need to do these kinds of things somewhere. Redux middleware were designed to enable writing logic that has side effects.

## Using the Redux Thunk Middleware​

As it turns out, Redux already has an official version of that «async function middleware», called the Redux «Thunk» middleware. The thunk middleware allows us to write functions that get dispatch and getState as arguments.

Configuring the Store​

The Redux thunk middleware is available on NPM as a package called redux-thunk.

## Saving Todo Items​

We also need to update the server whenever we try to create a new todo item. We need a way to write one function that accepts text as its parameter, but then creates the actual thunk function so that it can use the text value to make the API call. Our outer function should then return the thunk function so that we can pass to dispatch in our component. The component only knows that it needs to dispatch some value when the user presses enter.

The last thing we need to change here is updating our todos reducer. When we make a POST request to /fakeApi/todos, the server will return a completely new todo object .