# Data Passing with User Input

## Learning outcome

This exercise helps practice passing data from child to parent components based on user input, reinforcing the concept of props and state in React.

## Task

- Complete the TODOs in the ChildComponent.js file:

  - Use the useState hook to declare a state variable named userInput to store the input value.
  - Define the handleChange function to update the userInput state when the input changes.
  - Add an onChange event to handle changes in the input.
  - Bind the 'userInput' to the handleClick

- In the App.js file, update the handleClick function to receive the user input and set it as the message.
- Verify that clicking the "Send Message to Parent" button, the message is displayed in the parent component.

### Practice

[Practice in CodeSandbox](https://codesandbox.io/p/sandbox/ex-7-data-passing-with-user-input-86pv9d)

## Solution

[Solution in CodeSandbox](https://codesandbox.io/p/sandbox/ex-7-data-passing-with-user-input-solution-n88dsp)

<details>
  <summary>Solution</summary>

```js
// App.js
import { useState } from 'react';
import ChildComponent from './ChildComponent';
import './styles.css';

const App = () => {
  const [message, setMessage] = useState('');

  const handleClick = (userInput) => {
    setMessage(userInput);
  };

  return (
    <main>
      <h1>Data Passing with User Input</h1>
      <ChildComponent handleClick={handleClick} />
      <p>{message}</p>
    </main>
  );
};

export default App;
```

```js
// ChildComponent.jsx
import React, { useState } from 'react';

const ChildComponent = ({ handleClick }) => {
  const [userInput, setUserInput] = useState();

  const handleChange = (e) => {
    setUserInput(e.target.value);
  };

  return (
    <div>
      <input
        type="text"
        placeholder="Enter your message"
        onChange={handleChange}
      />
      <button onClick={() => handleClick(userInput)}>
        Send Message to Parent
      </button>
    </div>
  );
};

export default ChildComponent;
```

</details>
