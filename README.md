# React Todo App

This is a todo app built with React. It allows you to add, toggle, and delete tasks from a list. The tasks are stored in the local storage of your browser, so they persist even after you refresh the page.

## How to use

To use this app, you need to have Node.js and npm installed on your computer. Then, follow these steps:

1. Clone this repository or download the zip file.
2. Navigate to the project folder and run `npm install` to install the dependencies.
3. Run `npm start` to start the development server.
4. Open [http://localhost:3000] in your browser to see the app.

## How it works

The main component of this app is `App.js`, which contains the following logic:

- It uses the `useState` hook to create a state variable called `todos`, which is an array of objects with the following properties: `id`, `title`, and `completed`.
- It uses the `useEffect` hook to sync the `todos` state with the local storage. Whenever the `todos` state changes, it updates the local storage with the new value. It also initializes the `todos` state with the value from the local storage when the component mounts.
- It defines a function called `addTodo`, which takes a title as an argument and adds a new todo object to the `todos` state. It uses the `crypto.randomUUID()` function to generate a unique id for each todo.
- It defines a function called `toggleTodo`, which takes an id and a completed status as arguments and updates the corresponding todo object in the `todos` state with the new status.
- It defines a function called `deleteTodo`, which takes an id as an argument and removes the corresponding todo object from the `todos` state.
- It renders two child components: `NewTodoForm` and `TodoList`. It passes the `addTodo`, `toggleTodo`, and `deleteTodo` functions as props to these components.

The `NewTodoForm` component is responsible for rendering a form that allows you to enter a new todo title and submit it. It uses the `onSubmit` prop to call the `addTodo` function from the parent component.

The `TodoList` component is responsible for rendering a list of todos. It uses the `todos`, `toggleTodo`, and `deleteTodo` props to access the data and functions from the parent component. It renders each todo as a child component called `TodoItem`.

The `TodoItem` component is responsible for rendering a single todo. It uses the `todo`, `toggleTodo`, and `deleteTodo` props to access the data and functions from the parent component. It renders a checkbox, a label, and a button for each todo. It uses the `onChange` event of the checkbox to call the `toggleTodo` function with the id and checked status of the todo. It uses the `onClick` event of the button to call the `deleteTodo` function with the id of the todo.
