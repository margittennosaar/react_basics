# Working with Props

## Learning outcome

Practice working with props and creating a configurable, reusable component.

## Task

Build a reusable BookInfo component that displays information about a book. The BookInfo component should take two props - "title" and "author." It should output the received data between `<h2>` (title) and `<p>` (author) tags.

In the App component, render at least two instances of the BookInfo component.

One of those BookInfo components must receive a title of _"The Little Prince"_ and an author of _"Antoine de Saint-Exupéry"_. For the other instance, choose any book title and author of your preference.

### Practice

[Practice in CodeSandbox](https://codesandbox.io/p/sandbox/working-with-props-tvxqd7)

## Solution

[Solution in CodeSandbox](https://codesandbox.io/p/sandbox/working-with-props-solution-s8tdnn)

<details>
  <summary>Solution</summary>

```js
// App.jsx
import BookInfo from './BookInfo';
import './styles.css';

const App = () => {
  return (
    <div className="books">
      <BookInfo title="The Little Prince" author="Antoine de Saint-Exupéry" />
      <BookInfo title="Another Book Title" author="Another Author" />
    </div>
  );
};

export default App;
```

```js
// BookInfo.jsx
import React from 'react';

const BookInfo = ({ title, author }) => {
  return (
    <div className="book">
      <h2>{title}</h2>
      <p>{author}</p>
    </div>
  );
};

export default BookInfo;
```

</details>
