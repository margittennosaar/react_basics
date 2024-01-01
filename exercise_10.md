# List and keys

## Learning outcome

In this project, you will practice using lists and keys in React to display dynamic data, as well as how to conditionally display content based on certain criteria or the state of your React application. The application you are going to build is a 'Book Lister,' which displays a list of books. Each book will have a title, author, and a description. By default, all book descriptions are hidden, and users can toggle the visibility of the description with an onclick event.

## Task

- Modify `BookList` component. This is where you'll show your list of books.
  - Implement mapping of the books array from `books.js` to render each book using the `Book` component.
  - Ensure each `Book` component receives the necessary props including a `showDescription` prop to determine if the current book's description should be displayed based on its `ID` comparison with `activeBookId`.
- Modify `Book` component:
  - Use the `showDescription` prop to conditionally render the book's description in `Book.js`.
  - Include a button to toggle the visibility of the description. The button text should change based on the description's visibility state. If `showDescription` is `false` then button text is "show description" else "hide description".

### Practice

[Practice in CodeSandbox](https://codesandbox.io/p/sandbox/ex-10-list-and-keys-pzqty5)

## Solution

[Solution in CodeSandbox](https://codesandbox.io/p/sandbox/ex-10-list-and-keys-solution-4hswc7)

<details>
  <summary>Solution</summary>

```js
// App.js
import BookList from './BooksList';

import './styles.css';

const App = () => {
  return (
    <main>
      <h1>List and keys</h1>
      <BookList />
    </main>
  );
};

export default App;
```

```js
// BookList.js
import { useState } from 'react';
import { books } from './books.js';
import Book from './Book';

const BookList = () => {
  const [activeBookId, setActiveBookId] = useState(null);

  const visibilityHandler = (id) => {
    setActiveBookId(activeBookId === id ? null : id);
  };

  if (books.length === 0) {
    return <p>No books available.</p>;
  }

  return (
    <section className="card-grid">
      {books.map((book) => (
        <Book
          key={book.id}
          {...book}
          showDescription={book.id === activeBookId}
          visibilityHandler={() => visibilityHandler(book.id)}
        />
      ))}
    </section>
  );
};

export default BookList;
```

```js
// Book.js
const Book = ({
  title,
  author,
  description,
  showDescription,
  visibilityHandler,
}) => {
  const buttonText = showDescription ? 'hide description' : 'show description';

  return (
    <div className="card">
      <h2>{title}</h2>
      <p>{author}</p>
      {showDescription && <p className="description">{description}</p>}
      <button onClick={visibilityHandler}>{buttonText}</button>
    </div>
  );
};

export default Book;
```

</details>
