# Outputting Dynamic Content

## Learning outcome

Create a React component to display the name and title of a user.

## Task

Modify the **User** component code to dynamically display the user data from the **userData** object. Replace the placeholder text in the `<h2>` and `<p>` elements with the corresponding values from the **userData** object. Ensure that the user's first name, last name, and title are correctly displayed in the rendered component.

When the User component is rendered within the App component, it should display the user's first name and last name in the `<h2>` element and the user's title in the `<p>` element.

### Practice

[Practice in CodeSandbox](https://codesandbox.io/p/sandbox/outputting-dynamic-content-ffv333)

## Solution

[Solution in CodeSandbox](https://codesandbox.io/p/sandbox/outputting-dynamic-content-solution-lhgvtt)

<details>
  <summary>Solution</summary>

```js
import './styles.css';

export const userData = {
  firstName: 'Margit', // replace with your first name
  lastName: 'Tennosaar', // replace with your last name
  title: 'Teacher', // replace with your title
};

// Edit the User component code to output the userData data
export function User() {
  return (
    <div className="card">
      <h2>
        {userData.firstName} {userData.lastName}
      </h2>
      <p>{userData.title}</p>
    </div>
  );
}

// DON'T edit the App component code
function App() {
  return (
    <div id="app">
      <h1>Time to Practice</h1>
      <User />
    </div>
  );
}
```

</details>
