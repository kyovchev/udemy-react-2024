# Section 3: React Essentials

This section covers the main React concepts like Components, JSX, Props, State & More.

# Exercise 1

The first task was about creating and using a Component. The name of the new component is MainGoal and it is used in the App component.

## My Solution

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