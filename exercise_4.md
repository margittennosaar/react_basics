# Component Composition

## Learning outcome

To practice component composition and the use of the [children](https://react.dev/learn/passing-props-to-a-component#passing-jsx-as-children) prop (a special prop that allows wrapping a component around another component) in React.

## Task

In this task, you will be working on building a reusable BookCard component that can be employed as a wrapper around any JSX code related to a book.

1. Create a new functional component named BookCard within the BookCard.js file.
2. Ensure that the BookCard component takes a title prop as an input.
3. Output the name prop as a title inside the BookCard component.
4. Allow the BookCard component to be a wrapper around any JSX code by utilizing the children prop.
5. Output the wrapped JSX code below the title.
6. Test the final BookCard component by using it as follows:

```js
<BookCard title="The Art of Programming">
  An insightful journey through the world of programming, exploring both theory
  and practical applications.
  <button>Read More</button>
</BookCard>
```

### Practice

[Practice in CodeSandbox](https://codesandbox.io/p/sandbox/component-composition-c3zjq6)

## Solution

[Solution in CodeSandbox](https://codesandbox.io/p/sandbox/component-composition-solution-6w2j24)

<details>
  <summary>Solution</summary>

```js
// App.jsx
import React from 'react';
import BookCard from './BookCard';
import './styles.css';

const App = () => {
  return (
    <div className="books">
      <BookCard title="The Art of Programming">
        An insightful journey through the world of programming, exploring both
        theory and practical applications.
        <button>Read More</button>
      </BookCard>
    </div>
  );
};

export default App;
```

```js
// BookCard.jsx
import React from 'react';

const BookCard = ({ title, children }) => {
  return (
    <div className="book">
      <h2>{title}</h2>
      <p>{children}</p>
    </div>
  );
};

export default BookCard;
```

</details>
