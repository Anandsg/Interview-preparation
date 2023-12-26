### How to iterate inside and object and print all the values inside it without the keys? Give a code example?

To iterate through the values inside an object without printing the keys, you can use a for...in loop to access each key and then use the key to retrieve the corresponding value from the object.

Example:

```js
const myObject = {
  key1: 'value1',
  key2: 'value2',
  key3: 'value3',
};

for (const key in myObject) {
  if (myObject.hasOwnProperty(key)) {
    const value = myObject[key];
    console.log(value);
  }
}
```

### What is NaN property in JavaScript?

NaN stands for "Not-a-Number." It is a special value that represents the result of an operation that should return a number but doesn't

Example:

```js
const result = "Hello" / 2;
console.log(result); // Output: NaN
```

### Explain pass by value and pass by reference? Give code example of how you would pass by reference in javascript?

`Pass by Value:` In pass by value, a copy of the actual value is passed to the function. The original value is not affected by any changes made to the parameter inside the function.

```js
function updateValue(value) {
  value = 42;
}

let originalValue = 10;
updateValue(originalValue);
console.log(originalValue); // Output: 10 (unchanged)
```

`Pass by Reference:` JavaScript is always pass by value, but when objects (including arrays and functions, which are objects) are passed as arguments to functions, their reference is passed. This means that changes made to the object inside the function will affect the original object outside the function.

```js
function updateArray(array) {
  array.push(42);
}

let originalArray = [1, 2, 3];
updateArray(originalArray);
console.log(originalArray); // Output: [1, 2, 3, 42] (changed)
```

### What's the difference between event.preventDefault() and event.stopPropagation() methods in JavaScript?

`event.preventDefault():` The event.preventDefault() method is used to prevent the default action of an event. Every event in the browser has a default action associated with it. For example, clicking a link typically navigates to a new page, submitting a form sends the form data, and pressing the "Enter" key in a text field submits the form.

`event.stopPropagation():` The event.stopPropagation() method is used to stop the propagation of an event through the DOM. When an event occurs on an element, it can trigger handlers on that element and its ancestors (capturing phase) and descendants (bubbling phase).

### What are higher order function ? Explain with code example.

A higher-order function is a function that takes one or more functions as arguments or returns a function as its result.

```js
// Higher-order function that takes a function as an argument
function executeOperation(operation, value) {
  return operation(value);
}

// Functions to be passed as arguments
function square(x) {
  return x * x;
}

function double(x) {
  return x * 2;
}

// Using the higher-order function with different operations
console.log(executeOperation(square, 5));  // Output: 25 (square of 5)
console.log(executeOperation(double, 8));  // Output: 16 (double of 8)
```
