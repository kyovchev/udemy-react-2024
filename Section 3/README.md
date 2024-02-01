# Section 3: React Essentials - Basics

This section covers the main React concepts like Components, JSX, Props, State & More.

## Exercise 1: Building & Using a Component

The first task was about creating and using a Component. The name of the new component is MainGoal and it is used in the App component.

### Solution

```jsx
function MainGoal() {
    return "My main goal: To become a certified React developer."
}

function App() {
  return (
    <div id="app">
      <h1>Some header text</h1>
      <p>
        Some info text...
      </p>
      <MainGoal />
    </div>
  );
}

export default App;
```

## Exercise 2: Outputting Dynamic Content

The second task was about otputting dynamic content.

### Solution

```jsx
const userData = {
  firstName: 'Kaloyan',
  lastName: 'Yovchev',
  title: 'Instructor',
};

function User() {
  return (
    <div id="user" data-testid="user">
      <h2>
        {userData.firstName} {userData.lastName}
      </h2>
      <p>{userData.title}</p>
    </div>
  );
}

function App() {
  return (
    <div id="app">
      <h1>Time to Practice</h1>
      <p>Welcome on board of this course! You got this 💪</p>
      <User />
    </div>
  );
}

export default App;
```

## Exercise 3: Working with Props

The third exercise was about working with Props. I have added the map function which was not required but it makes the code better.

### Solution
```jsx
function CourseGoal({title, description}) {
  return (
    <li>
      <h2>{title}</h2>
      <p>{description}</p>
    </li>
  );
}

function App() {
  return (
    <div id="app" data-testid="app">
      <h1>Time to Practice</h1>
      <p>One course, many goals! 🎯</p>
      <ul>
        {
          [
            {
              title: "Title 1",
              description: "Description 1",
            },
            {
              title: "Title 2",
              description: "Description 2",
            }
          ].map(goal => <CourseGoal key={goal.title} {...goal} />)
        }
      </ul>
    </div>
  );
}

export default App;
```

## Exercise 4: Component Composition

Exercise about Component Composition. The goal of this exercise was to create a reusable Card component that takes a name prop as an input and, in addition, can be wrapped around any JSX code.

The final Card component, had to be usable like this:
```jsx
<Card name="Maria Miles">
  <p>
    Maria is a professor of Computer Science at the University of Illinois.
  </p>
  <p>
    <a href="mailto:blake@example.com">Email Maria</a>
  </p>
</Card>
```

### Solution

The file Card.js contains:

```jsx
export default function Card({ name, children }) {
  return (
    <div class="card">
      <h1>{name}</h1>
      {children}
    </div>
  );
}
```

## Exercise 5: Reacting to Events

It was about reacting to events. The goal was to update the data stored in the already existing user object once the "Login" button in the App component is pressed.

### Solution

```jsx
const user = {
  email: '',
  password: '',
  loggedIn: false,
};

function App() {
  function handleLogin() {
    user.email = "a@a.bg";
    user.password = "123";
    user.loggedIn = true;
  }
  return (
    <div id="app">
      <h1>User Login</h1>
      <p>
        <label>Email</label>
        <input type="email" />
      </p>

      <p>
        <label>Password</label>
        <input type="password" />
      </p>

      <p id="actions">
        <button onClick={handleLogin}>Login</button>
      </p>
    </div>
  );
}

export default App;
```

## Exercise 6: Configuring Event Handlers

Your task was to edit the button in the App component so that the already defined handleCreateUser function is called with a value for name.

### Solution
```jsx
const user = {
  name: '',
};

function App() {
  function handleCreateUser(name) {
    user.name = name;
  }

  return (
    <div id="app">
      <h1>User Login</h1>
      <p>
        <label>Name</label>
        <input type="text" />
      </p>

      <p id="actions">
        <button onClick={() => handleCreateUser("name")}>Create User</button>
      </p>
    </div>
  );
}

export default App;
```

## Exercise 7: Working with State

The task was to add an event listener to listen for clicks on the button that's already included in the App component. Upon a button click, the price should change from $100 to $75.

### Solution
```jsx
import { useState } from 'react'

export default function App() {
    const [ price, setPrice ] = useState(100);
    return (
        <div>
            <p>${price}</p>
            <button onClick={() => setPrice(75)}>Apply Discount</button>
        </div>
    );
}
```

## Exercise 8: Conditional Content

The task was to conditionally show a warning box once a user has clicked a specific button. Inside that warning dialog, another button allows users to dismiss the warning.

### Solution
```jsx
import { useState } from 'react'

export default function App() {
    const [ showWarning, setShowWarning ] = useState(false);

    return (
      <div>
        {showWarning && (
          <div id="alert">
            <h2>Are you sure?</h2>
            <p>These changes can't be reverted!</p>
            <button onClick={() => setShowWarning(false)}>Proceed</button>
          </div>
        )}
        {!showWarning && <button onClick={() => setShowWarning(true)}>Delete</button>}
      </div>    
    );
}
```

## Exercise 9: Dynamic Styling
The task was to dynamically apply a CSS class (active) to the p element in the provided React app. The class had be applied when the button is clicked for the first time.

### Solution
```jsx
import { useState } from 'react'

export default function App() {
    const [ isActive, setIsActive ] = useState(false);
    return (
        <div>
            <p className={isActive && "active"}>Style me!</p>
            <button onClick={() => setIsActive(!isActive)}>Toggle style</button>
        </div>
    );
}
```

## Exercise 10: Dynamic List Content

The task was to output a list of dummy todo items dynamically.

### Solution
```jsx
const DUMMY_TODOS = [
  'Learn React',
  'Practice React',
  'Profit!',
];

function Todo({ text }) {
    return <li>{text}</li>;
}

export default function App() {
  return (
    <ul>
      {DUMMY_TODOS.map(todo => <Todo key={todo} text={todo} />)}
    </ul>
  );
}
```