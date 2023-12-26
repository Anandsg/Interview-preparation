### What were the 10 new features that were introduced in ES6? Explain each one of them in detail?

`let and const:`
let and const provide block-scoped variable declarations, improving variable scoping in comparison to var. let is mutable, allowing reassignment, while const is immutable once assigned.

```js
let x = 5;
const PI = 3.14;
```

`Arrow Functions:`

Arrow functions introduce a concise syntax for writing functions, especially useful for short anonymous functions. They inherit the this value from their enclosing scope.

```js
// Traditional function
function add(x, y) {
  return x + y;
}

// Arrow function
const add = (x, y) => x + y;
```

`Template Literals:`

Template literals allow the embedding of expressions inside string literals using backticks (`). This provides a more readable way to concatenate strings and include variables.

```
const name = "John";
const greeting = `Hello, ${name}!`;
```

`Spread and Rest Operators:`

The spread (...) and rest (...) operators enable working with arrays and object literals more conveniently. Spread is used for spreading elements, while rest is used for collecting elements.

```js
// Spread operator for arrays
const arr1 = [1, 2, 3];
const arr2 = [...arr1, 4, 5];

// Rest operator for function parameters
function sum(...numbers) {
  return numbers.reduce((acc, num) => acc + num, 0);
}
```

`Classes:`

ES6 introduced the class syntax for creating classes in JavaScript. It provides a more familiar and convenient way to define and instantiate objects with constructor functions.

```js
class Person {
  constructor(name, age) {
    this.name = name;
    this.age = age;
  }

  sayHello() {
    console.log(`Hello, my name is ${this.name}.`);
  }
}
```

`Map and Set:`

ES6 introduced two new built-in data structures, Map and Set. Map allows the use of any data type as a key, and Set stores unique values.

```js
// Map
const myMap = new Map();
myMap.set('key', 'value');
const value = myMap.get('key');

// Set
const mySet = new Set([1, 2, 3, 1]);
```

### 2. Call, Apply, Bind. When to use what ? Can you give an example?

`call`, `apply`, and `bind` are methods in JavaScript that are used to manipulate the this context of a function. They are often referred to as "function methods" and are used in situations where you need to explicitly set the value of this for a function.

`call:`
The call method is used to invoke a function with a specified this value and individual arguments provided as separate arguments.

```js
let name = {
  firstName: "Anand",
  lastName: "Gadugin",
};

let printFullName = function (hometown) {
  console.log(this.firstName + " " + this.lastName + " " + "from" + " " + hometown);
};

printFullName.call(name, "Gadag");

let name2 = {
    firstName: "Akshay",
    lastName: "Saini",
};

printFullName.call(name2, "Hubli");
```

`apply:`
The apply method is similar to call, but it takes an array-like object as its second argument, which represents the arguments to be passed to the function.
javascript

```js
let name = {
  firstName: "Anand",
  lastName: "Gadugin",
};

let printFullName = function (hometown) {
  console.log(this.firstName + " " + this.lastName + " " + "from" + " " + hometown);
};

printFullName.call(name, "Gadag");

let name2 = {
    firstName: "Akshay",
    lastName: "Saini",
};

printFullName.call(name2, ["Hubli", "Blr"]); // like this
```

`bind:`
The bind method creates a new function with the same body as the original function but with a fixed this value. The new function can be invoked later.

```js
// Using bind
let boundFunction = printFullName.bind(name, "Gadag");
boundFunction();
```

So basically

```js
let name = {
  firstName: "Anand",
  lastName: "Gadugin",
};

let printFullName = function (hometown) {
  console.log(this.firstName + " " + this.lastName + " " + "from" + " " + hometown);
};

// Using call
printFullName.call(name, "Gadag");

let name2 = {
  firstName: "Akshay",
  lastName: "Saini",
};

// Using call with a different object
printFullName.call(name2, "Hubli");

// Using apply
printFullName.apply(name, ["Gadag"]);

// Using bind
let boundFunction = printFullName.bind(name, "Gadag");
boundFunction();
```

### 3. What are different ways to store data in browser? Explain each one of them and when should we use what?

`LocalStorage:` LocalStorage is a web storage API that allows you to store key-value pairs in the browser. The data is persistent and remains even when the browser is closed.

`SessionStorage:` Similar to LocalStorage, SessionStorage is a web storage API for storing key-value pairs. However, the data is only available for the duration of the page session (as long as the browser tab is open).

### 4. What are generator function in javascript ? How are they different from normal function?

Generator functions are a special type of function in JavaScript introduced with ECMAScript 2015 (ES6). They allow you to pause and resume the execution of a function, yielding values one at a time. Generator functions are denoted by the use of the function\* syntax and the yield keyword.

```js
function* generateNumbers() {
  yield 1;
  yield 2;
  yield 3;
}

const generator = generateNumbers();

console.log(generator.next()); // { value: 1, done: false }
console.log(generator.next()); // { value: 2, done: false }
console.log(generator.next()); // { value: 3, done: false }
console.log(generator.next()); // { value: undefined, done: true }
```

### 5. Difference between arr.foreach, array.map and array.filter? Take example input array and explain the output which you will get

`forEach:`
Purpose: forEach is used for iterating over each element in an array and performing an operation on each element. (it does not create a new array).

```js
const numbers = [1, 2, 3, 4, 5];

numbers.forEach((num, index) => {
  console.log(`Element at index ${index}: ${num}`);
});
```

output:

```js
Element at index 0: 1
Element at index 1: 2
Element at index 2: 3
Element at index 3: 4
Element at index 4: 5
```

`map:`
Purpose: map is used for creating a new array by applying a function to each element of the original array. (A new array containing the results of applying the provided function to each element.)

```js
const output = arr.map(double);

console.log(output);

const output2 = arr.map((x) => x * 2);

console.log(output2);
```

`filter:`
Purpose: filter is used for creating a new array with elements that satisfy a specific condition. (A new array containing elements that pass the test implemented by the provided function.)

```js
const numbers = [1, 2, 3, 4, 5];

const evenNumbers = numbers.filter(num => num % 2 === 0);
console.log(evenNumbers);
```

output:

```
[2, 4]
```
