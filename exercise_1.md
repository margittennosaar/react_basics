# Building & Using a Components

## Learning outcome

Create a basic React components and use it in the JSX code of another component.

## Task

1. Create a Basic Component:

   Create a new React component named BasicComponent. This component should be a functional component and can be as simple as a div element with some text content.

2. Use BasicComponent in another component:

   Create a second React component named ParentComponent.
   Import and use the BasicComponent within the JSX code of ParentComponent.

3. Integrate in App component:

   Finally, import and render the ParentComponent in your main App component or any other higher-level component in your React application.

### Practice

[Practice in CodeSandbox](https://codesandbox.io/p/sandbox/building-using-a-component-mwyyvq)

## Solution

[Solution in CodeSandbox](https://codesandbox.io/p/sandbox/building-using-a-component-solution-s8zxk8)

<details>
  <summary>Solution</summary>

```js
// App.jsx
import ParentComponent from './ParentComponent';
import './styles.css';

const App = () => {
  return (
    <main>
      <h1>My first React app</h1>
      <ParentComponent />
    </main>
  );
};

export default App;
```

```js
// ParentComponent.jsx
import BasicComponent from './BasicComponent';

const ParentComponent = () => {
  return (
    <div>
      <h2>Parent Component</h2>
      <BasicComponent />
    </div>
  );
};

export default ParentComponent;
```

```js
// BasicComponent.jsx
const BasicComponent = () => {
  return (
    <div>
      <p>This is a basic React component!</p>
    </div>
  );
};

export default BasicComponent;
```

</details>
