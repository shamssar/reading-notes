# Redux - Combined Reducers

###  Why choose Redux instead of the Context API for global state?

By using the combineReducer method, you can organize multiple reducers and track them through one global state via Redux, and only need to use one provider avoiding "context hell".
### What is the purpose of a reducer?

 The purpose of the reducer is to limit all state changes to the actions defined in the switch statement.
### What does an action contain?

 An action will contain an object with the type (for switch case logic) and 
 ### Why do we need to copy the state in a reducer?

we need to copy the state because state is immutable so we need to overwrite it with the exsiting state plus the changes we have made

### immutable state

* state that can't be modified and must be overwritten with new state
### time travel in redux

* the redux developer tools keeps track previous states allowing you to view those previous state values
### action creator

* action creator is a function that returns an object containing the action type, and payload
### reducer

* a reducer is a function that takes in state in an action, then depending on the action object, the reducer function must update the state in an immutable manner, and return the new state. source
### dispatch

* dispatch calls the state change with an action object