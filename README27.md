# Hook
Hooks are a new addition in React 16.8. They let you use state and other React features without writing a class.


## Motivation
* It’s hard to reuse stateful logic between components.
* Complex components become hard to understand.
* Classes confuse both people and machines.


## Hooks API
This example renders a counter. When you click the button, it increments the value:
import React, { useState } from 'react';
```
function Example() {
  // Declare a new state variable, which we'll call "count"
  const [count, setCount] = useState(0);

  return (
    <div>
      <p>You clicked {count} times</p>
      <button onClick={() => setCount(count + 1)}>
        Click me
      </button>
    </div>
  );
}
```
Here, useState is a Hook.

## Effect Hook
The Effect Hook, useEffect, adds the ability to perform side effects from a function component.

For example, this component sets the document title after React updates the DOM:
import React, { useState, useEffect } from 'react';
```
function Example() {
  const [count, setCount] = useState(0);

  // Similar to componentDidMount and componentDidUpdate:
  useEffect(() => {
    // Update the document title using the browser API
    document.title = `You clicked ${count} times`;
  });

  return (
    <div>
      <p>You clicked {count} times</p>
      <button onClick={() => setCount(count + 1)}>
        Click me
      </button>
    </div>
  );
}
```
## Rules of Hooks
Hooks are JavaScript functions, but they impose two additional rules:

* Only call Hooks at the top level. Don’t call Hooks inside loops, conditions, or nested functions.

* Only call Hooks from React function components. Don’t call Hooks from regular JavaScript functions. (There is just one other valid place to call Hooks — your own custom Hooks. We’ll learn about them in a moment.)

## The State Hook
Declaring a State Variable
In a class:
```
class Example extends React.Component {
  constructor(props) {
    super(props);
    this.state = {
      count: 0
    };
  }
  ```
In a function component:
```
import React, { useState } from 'react';

function Example() {
  // Declare a new state variable, which we'll call "count"
  const [count, setCount] = useState(0);
  ```
## Reading State
In a class:
```
 <p>You clicked {this.state.count} times</p>
 ```
In a function component:
```
  <p>You clicked {count} times</p>
  ```
## Updating State
In a class:

```
  <button onClick={() => this.setState({ count: this.state.count + 1 })}>
    Click me
  </button>
  ```
In a function component:
```
  <button onClick={() => setCount(count + 1)}>
    Click me
  </button>
  ```


  References:
  
  [Introducing Hooks](https://reactjs.org/docs/hooks-intro.html#motivation)

  [Hooks API](https://reactjs.org/docs/hooks-overview.html)

  [The State Hook](https://reactjs.org/docs/hooks-state.html)