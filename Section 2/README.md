# Section 2. JavaScript Refresher

This section was about JavaScript and contained two exercises.

## Exercise 1
The first task was to write a function that accepts three input values a, b and c and returns a * b / c.

### My Solution
```javascript
function combine(a, b, c) {
    return a * b / c;
}
```

## Exercise 2
The second task was to write a function that transforms a list of numbers into a list of JavaScript objects where every object has a val key with the input array's number as a value.

### My Solution
```javascript
function transformToObjects(numberArray) {
    return numberArray.map(val => ({val: val}));
}
```