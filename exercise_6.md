# State and useState in React

## Learning outcome

This exercise helps practice using the useState hook to manage state in a React functional component, allowing the component to dynamically update and display changes in the UI.

## Task

- Complete the TODOs in the Counter.js file:

  - Use the useState hook to declare a state variable named count with an initial value of 0.
  - Define the increment function to update the count state by incrementing it.
  - Define the decrement function to update the count state by decrementing it.

- Use the Counter Component in App
- Verify that clicking the "Increment" button increases the count and clicking the "Decrement" button decreases the count.

### Practice

[Practice in CodeSandbox](https://codesandbox.io/p/sandbox/ex-6-state-and-usestate-in-react-65pdwz)

## Solution

[Solution in CodeSandbox](https://codesandbox.io/p/sandbox/ex-6-state-and-usestate-in-react-solution-6vs94j)

<details>
  <summary>Solution</summary>

```js
// App.js
import Counter from './Counter';
import './styles.css';

const App = () => {
  return (
    <main>
      <h1>React State and useState Exercise</h1>
      <Counter />
    </main>
  );
};

export default App;
```

```js
// Counter.js
import React, { useState } from 'react';

const Counter = () => {
  const [count, setCount] = useState(0);

  const increment = () => {
    setCount(count + 1);
  };

  const decrement = () => {
    setCount(count - 1);
  };

  return (
    <div>
      <h2>Counter: {count}</h2>
      <button onClick={increment}>Increment</button>
      <button onClick={decrement}>Decrement</button>
    </div>
  );
};

export default Counter;
```

</details>
