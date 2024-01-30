# Section 3: React Essentials - Basics

This section covers the main React concepts like Components, JSX, Props, State & More.

## Exercise 1

The first task was about creating and using a Component. The name of the new component is MainGoal and it is used in the App component.

### Solution

```
import React from 'react';

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

## Exercise 2

The second task was about otputting dynamic content.

### Solution

```
import React from 'react';

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

## Exercise 3

The third exercisse was about working with Props. I have added the map function which was not required but it makes the code better.

#### Solution
```
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
          ].map(goal => (<CourseGoal {...goal} />))
        }
      </ul>
    </div>
  );
}

export default App;
```