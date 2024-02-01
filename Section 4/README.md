# Section 4: React Essentials - Deep Dive

This section covers Fragments, Forwarding Props, Flexible Components, Two-Way-Binding & More.

## Exercise 1: Using Fragments

The task was to output two components without nesting them in a div.

### Solution

```jsx
function App() {
  return (
    <>
      <h1>Summary</h1>
      <p>{text}</p></>;
    </>
  );
}

export default App;
```

## Exercise 2: Forwarding Props

The task was to modify the Input component so it either returns a textarea element or an input element, depending on whether a richText prop and the Input component had to forward all other props directly to the returned textarea or input elements.

### Solution

```jsx
export default function Input({ richText, ...props }) {
  return (
    <>
      { richText ? <textarea {...props}></textarea> : <input {...props} /> }
    </>
  );
}
```

## Exercise 3: Creating Flexible Components

The task was to build a highly re-usable, custom Button component that can be used in multiple ways (look at the code of the solution).

### Solution

```jsx
export default function Button({ children, mode = "filled", Icon, ...props}) {
  let cssClasses = `button ${mode}-button`;
  if (Icon) {
    cssClasses += " icon-button";
  }
  if (props.className) {
    cssClasses += " " + props.className;
  }

  return (
    <button className={cssClasses} {...props}>
      { Icon && (
        <span className="button-icon">
          <Icon />
        </span>
      )}
      <span>{children}</span>
    </button>
  );
}
```

## Exercise 4: Two-Way-Binding



### Solution

```jsx

```