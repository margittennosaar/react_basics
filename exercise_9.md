# Conditional rendering and useRef usage

## Learning outcome

In this project, you create a simple a React application that allows a user to log in and view their profile. The app will display a login prompt component initially. Once the user logs in, the app will display the user's profile component. If user logs out from profile, it will take user back to the login promt component.

## Task

- Import the UserProfile and LoginPrompt components into the App component, and pass the correct functions and/or data to the components.
- Add conditional rendering to display the UserProfile component if the user.isLoggedIn is true, otherwise, display the LoginPrompt component.
- In the LoginPrompt component, use the useRef hook to create a reference to the input element.
- In UserProfile component, include handleLogOut function in the onClick event to log the user out

### Practice

[Practice in CodeSandbox](https://codesandbox.io/p/sandbox/ex-9-conditional-rendering-tvyh48)

## Solution

[Solution in CodeSandbox](https://codesandbox.io/p/sandbox/ex-9-conditional-rendering-solution-9mhlgl)

<details>
  <summary>Solution</summary>

```js
// App.js
import { useState } from 'react';
import UserProfile from './UserProfile';
import LoginPrompt from './LoginPrompt';
import './styles.css';

const App = () => {
  const [user, setUser] = useState({
    name: '',
    isLoggedIn: false,
  });

  const handleLogIn = (name) => {
    setUser({ ...user, name: name, isLoggedIn: true });
  };
  const handleLogOut = () => {
    setUser({ ...user, isLoggedIn: false });
  };

  return (
    <main>
      <h1>Conditional rendering</h1>
      <div>
        {user.isLoggedIn ? (
          <UserProfile user={user.name} handleLogOut={handleLogOut} />
        ) : (
          <LoginPrompt handleLogIn={handleLogIn} />
        )}
      </div>
    </main>
  );
};

export default App;
```

```js
// LoginPrompt.js
import { useRef } from 'react';

const LoginPrompt = ({ handleLogIn }) => {
  const inputRef = useRef(null);

  return (
    <div>
      <p>Please log in to see your profile.</p>
      <div>
        <label htmlFor="name">Your first name</label>
        <input type="text" id="name" ref={inputRef} />
      </div>
      <button onClick={() => handleLogIn(inputRef.current.value)}>
        Log in
      </button>
    </div>
  );
};

export default LoginPrompt;
```

```js
// UserProfile.js
const UserProfile = ({ user, handleLogOut }) => (
  <div>
    <h1>Welcome, {user}!</h1>
    <button onClick={handleLogOut}>Log out</button>
  </div>
);

export default UserProfile;
```

</details>
