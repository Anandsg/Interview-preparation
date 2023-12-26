### Hosting, callbacks, ES6 features

`Hoisting` is a JavaScript behavior where variable and function declarations are moved to the top of their containing scope during the compilation phase in other words we can access variables or functions even before initializing it or even before putting value in it.

example:

```js
console.log(x)
var x = 10;
```

`callback` is a function that is passed as an argument to another function and is executed after the completion of some asynchronous operation or at a later time.

example:

```js
function fetchData(callback) {
  // Simulating an asynchronous operation
  setTimeout(() => {
    const data = "Some data";
    callback(data);
  }, 1000);
}

function handleData(data) {
  console.log("Data received:", data);
}

// Using the callback
fetchData(handleData);
```

`ES6 Features:` Arrow Functions, let and const, Template Literals, Destructuring Assignment, Promises

### Difference between array.map and array.filter

`Array.map()` :

- `Purpose:` The map method is used to create a new array by applying a provided function to each element of the original array.
- `Return Value:` It returns a new array where each element is the result of applying the provided function to the corresponding element of the original array.
- `Usage:` It is often used when you want to transform each element of an array in a specific way.

example:

```
const numbers = [1, 2, 3, 4];

const doubledNumbers = numbers.map((number) => number * 2);

console.log(doubledNumbers); // Output: [2, 4, 6, 8]
```

`Array.filter()` :

- `Purpose:` The filter method is used to create a new array with elements that satisfy a certain condition.
- `Return Value:` It returns a new array containing only the elements that meet the specified condition.
- `Usage:` It is commonly used when you want to filter elements based on a particular criterion.

```js
const numbers = [1, 2, 3, 4];

const evenNumbers = numbers.filter((number) => number % 2 === 0);

console.log(evenNumbers); // Output: [2, 4]
```

### How to find the length of an object

In JavaScript, objects do not have a built-in length property like arrays. However, you can determine the number of properties (or keys) an object has by using the `Object.keys()`, `Object.values()`, or `Object.entries()` methods along with the length property.

example:

```js
const myObject = { a: 1, b: 2, c: 3 };

const numberOfProperties = Object.keys(myObject).length;

console.log(numberOfProperties); // Output: 3
```

### What are promises? 3 states of promises.

Promises are objects in JavaScript that represent the eventual completion or failure of an asynchronous operation. They provide a cleaner and more structured way to work with asynchronous code compared to traditional callback functions.

`Pending:`
The initial state of a promise.
The asynchronous operation associated with the promise is neither completed nor failed at this point.

`Fulfilled (Resolved):`
The state of a promise when the asynchronous operation has completed successfully.
If the promise is fulfilled, it will have a result (a value).

`Rejected:`
The state of a promise when the asynchronous operation has encountered an error or failed.
If the promise is rejected, it will have a reason (an error or failure message).
