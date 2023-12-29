# Forms, controlled components and conditional rendering

## Learning outcome

In this project, the main aim is to learn how to build a React app using controlled components and conditional rendering. You'll create Form and View components as child components, and you'll practice how to pass input data from the Form component to the View component when the onChange event is triggered.

## Task

- Complete the TODOs in the **App.js** file:

  - Write a function called `handleChange` to store user input values in the `'details'` variable as an object.
  - Import the **Form** component and provide the `handleChange` function to it.
  - Import the **View** component and provide the `details` object to it.

- Create a **Form.js** component that includes a form element with various inputs and corresponding labels:
  - First name (input type: 'text')
  - Last name (input type: 'text')
  - Phone (input type: 'number')
  - Email (input type: 'email')
  - Role (select with options: 'student', 'teacher', 'other')
- Utilize a single `onChange` event handler on the form element to capture input changes.

- Develop a **View.js** component to display data from the `'details'` object.
- Implement conditional rendering to display the content of the View component **only if the 'details' variable is not null**.

### Practice

[Practice in CodeSandbox](https://codesandbox.io/p/sandbox/ex-8-forms-and-user-input-d2wkmp)

## Solution

[Solution in CodeSandbox](https://codesandbox.io/p/sandbox/ex-8-forms-and-user-input-solution-lcnf92)

<details>
  <summary>Solution</summary>

```js
// App.js

import { useState } from 'react';
import Form from './Form';
import View from './View';
import './styles.css';

const App = () => {
  const [details, setDetails] = useState();

  const handleChange = (e) => {
    const { name, value } = e.target;
    setDetails({ ...details, [name]: value });
  };

  return (
    <main>
      <h1>Forms and User Input</h1>
      <Form handleChange={handleChange} />
      <View details={details} />
    </main>
  );
};

export default App;
```

```js
// Form.js
const Form = ({ handleChange }) => {
  return (
    <form onChange={(e) => handleChange(e)}>
      <fieldset id="details">
        <legend>Your details</legend>
        <div>
          <label htmlFor="firstname">First Name</label>
          <input type="text" id="firstname" name="firstname" />
        </div>
        <div>
          <label htmlFor="lastname">Last Name</label>
          <input type="text" id="lastname" name="lastname" />
        </div>
        <div>
          <label htmlFor="phone">Phone</label>
          <input type="number" id="phone" name="phone" />
        </div>
        <div>
          <label htmlFor="email">Email</label>
          <input type="email" id="email" name="email" />
        </div>
        <div>
          <label htmlFor="role">Role</label>
          <select name="role" id="role">
            <option value="defaultOption" disabled>
              Select your option
            </option>

            <option value="student" defaultValue>
              student
            </option>
            <option value="teacher">teacher</option>
            <option value="other">other</option>
          </select>
        </div>
      </fieldset>
    </form>
  );
};

export default Form;
```

```js
// View.js
const View = ({ details }) => {
  if (details) {
    const { firstname, lastname, role, phone, email } = details;
    return (
      <div>
        <h2>Your form inputs</h2>
        <div>
          <p>
            {firstname} {lastname} {phone} {email} {role}
          </p>
        </div>
      </div>
    );
  }
};

export default View;
```

</details>
