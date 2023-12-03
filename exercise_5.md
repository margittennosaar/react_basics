# Event handlers

## Learning outcome

Practice event handling in a React app.

## Task

The task involves updating book details (title, author, genre, and reading status) when a button is pressed in the App component. Note that the input fields are currently non-functional, and you're focusing on event handling.

1. Open the provided React project containing the App component.
2. Identify the "Add book" button within the component.
3. Implement an event handler function, handleClick, that is triggered when the "Add book" button is clicked.
4. Inside the handleClick function, update the book details:

- Set the book title to "title".
- Set the author to "author".
- Set the genre to "genre".
- Set the reading status (isRead) to true.

5. Test your implementation by clicking the "Add book" button and confirming that the book details have been successfully modified (use console.log before and after event)

**Important Note:** The current input fields are non-functional, and you are not required to fetch values from them. Focus on practicing event handling.

### Practice

[Practice in CodeSandbox](https://codesandbox.io/p/sandbox/reacting-to-events-wn7x8w)

## Solution

[Solution in CodeSandbox](https://codesandbox.io/p/sandbox/reacting-to-events-solution-9jtgd8)

<details>
  <summary>Solution</summary>

```js
// Your goal is to change the title, author, genre and reading status when the button in the App component is pressed
// You DON'T need to fetch the values entered into the <input /> fields
import './styles.css';

export const book = {
  title: '',
  author: '',
  genre: '',
  isRead: true,
};

// Please note: The Add book does not actually work!
// This exercise is just about practicing event handling
// Ignore the inputs; you'll learn to handle user input later.

function App() {
  function handleClick() {
    book.title = 'title';
    book.author = 'author';
    book.genre = 'genre';
    book.isRead = true;
  }

  return (
    <div id="app">
      <h1>Add book</h1>
      <div>
        <label>Title</label>
        <input type="text" />
      </div>

      <div>
        <label>Author</label>
        <input type="text" />
      </div>

      <div>
        <label>Genre</label>
        <select name="genre">
          <option value="mystery">Mystery</option>
          <option value="science_fiction">Science Fiction</option>
          <option value="history_fiction">Historical Fiction</option>
        </select>
      </div>

      <button onClick={handleClick}>Add book</button>
    </div>
  );
}

export default App;
```

</details>
