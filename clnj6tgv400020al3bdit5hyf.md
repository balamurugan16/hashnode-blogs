---
title: "Smart and Dumb React components"
datePublished: Mon Oct 09 2023 17:49:09 GMT+0000 (Coordinated Universal Time)
cuid: clnj6tgv400020al3bdit5hyf
slug: smart-and-dumb-react-components
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/xkBaqlcqeb4/upload/92154ba62268da9c8b606170df76227c.jpeg
tags: javascript, frontend, reactjs, programming-ciovqvfcb008mb253jrczo9ye

---

React is the popular choice in the web development community to build UI. It leverages the concept of components where the UI will be broken down into individual, reusable chunks. When this idea came out, it was revolutionary, and still it is. React is unopinionated as well, meaning that there are no enforcements like Angular. Unopinionated approaches often tend to be exploited rather than leveraged. In React, the component hierarchy is very important because it ensures readability and the code base can be easily scaled, managed and unit-tested. Keeping that point in mind, In this article we will cover one of the underrated approaches to architecture components in React.

Smart and Dumb components (also known as container/presentation pattern) is an approach where the Dumb components take care of how the data is shown (UI) and the Smart components take care of the business logic and handle external dependencies and side effects like API requests etc.

So we will build a basic Todo App in this example to explain this pattern. Here the `TodoList.js` and `TodoForm.js` are Dumb components and the `App.js` is the smart component.

```jsx
// TodoList.js
import React from 'react';
import { Todo } from '../store/todo.slice';

function TodoList({ todos, deleteTodo }) {
  return (
    <ul>
      {todos.map((todo) => (
        <li key={todo.id}>
          <p>{todo.text}</p>
          <button
            onClick={() => deleteTodo(todo.id)}
            data-testid={`todo-${todo.id}`}
          >
            Delete
          </button>
        </li>
      ))}
    </ul>
  );
}

export default TodoList;
```

```jsx
// TodoForm.js
import React, { useState } from 'react';

function TodoForm({ addTodo }) {
  const [inputText, setInputText] = useState('');

  const handleSubmit = (e) => {
    e.preventDefault();
    if (inputText.trim() !== '') {
      addTodo(inputText);
      setInputText('');
    }
  };

  return (
    <form onSubmit={handleSubmit} className="flex gap-2">
      <input
        placeholder="Add a To-Do"
        value={inputText}
        onChange={(e) => setInputText(e.target.value)}
      />
      <button type="submit">Add</button>
    </form>
  );
}

export default TodoForm;
```

```jsx
import React from 'react';
import { useDispatch, useSelector } from './store';
import { addTodo, deleteTodo } from './todo.slice';
import TodoForm from './TodoForm';
import TodoList from './TodoList';

function TodoApp() {
  const todos = useSelector((state) => state.todoSlice);
  const dispatch = useDispatch();

  const handleAddTodo = (text: string) => {
    dispatch(addTodo(text));
  };

  const handleDeleteTodo = (id: number) => {
    dispatch(deleteTodo(id));
  };

  return (
    <div className="w-full flex justify-center flex-col h-full items-center">
      <TodoForm addTodo={handleAddTodo} />
      <TodoList todos={todos} deleteTodo={handleDeleteTodo} />
    </div>
  );
}

export default TodoApp;
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1696873610651/278b9498-4fef-4ffd-b822-9e85c65b84de.png align="center")

If you look closely, The `TodoList.js` and the `TodoForm.js` components are called pure functions, which means that given an input, the component will only render one output, which usually can be achieved when there are no external dependencies for the component. In the `App.js`, takes care of dealing with the Redux store and provides the functionality to the dumb components via props. As you can see, the `addTodo` and `deleteTodo` functions are defined in the smart component and passed to the dumb components.

### Advantages:

* The dumb components can be **reused** throughout the application.
    
* Easily enforcing separations of concern like the UI will be handled in the dumb components and the business logic will be handled in the Smart components.
    
* Testing dumb components will be very easy as they are pure functions and there will be no need to mock any libraries or external dependencies which reduces a lot of effort.
    

In the above example, considering that you have implemented unit testing for `TodoList.js`, `TodoForm.js`, and the `todo.slice.js`, the main `App.js` technically doesn’t need to be unit tested because if you look closely, all the parts of the code are already tested individually, so ultimately you will get the confidence that your application will work.

### Disadvantages:

* The same approach can also be implemented using Hooks. The business logic can be wrapped in a custom hook and all the components can be kept as dumb components. For me, a mix of both approaches will work fine.
    
* This approach can be an overkill for a smaller application.