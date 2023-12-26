### 1. what is the difference between `==` And `===`

`== (Equality Operator):`

- The == operator performs type coercion if the operands are of different types before making the comparison.
- It converts the operands to the same type (if possible) and then compares their values.
- The equality operator often leads to unexpected results due to type coercion

Example:

```js
'5' == 5;           // true (String '5' is coerced to Number 5)
false == 0;         // true (Boolean false is coerced to Number 0)
null == undefined;  // true (null and undefined are considered equal)
```

`=== (Strict Equality Operator):`

- The === operator, also known as the strict equality operator, does not perform type coercion.
- It compares both the values and the types of the operands. If the values and types are the same, the comparison evaluates to true; otherwise, it evaluates to false.

Example:

```js
'5' === 5;           // false (String '5' is not equal to Number 5 in value and type)
false === 0;         // false (Boolean false is not equal to Number 0 in type)
null === undefined;  // false (null and undefined are not equal in type)
```

### 2. What is the difference between `null` and `undefined`?

undefined: A variable or property is `undefined` when it has been declared but has not been assigned a value.

```js
let x;
console.log(x); // Output: undefined
```

null: The null value represents the intentional absence of any object value. It is often used to indicate that a variable or property should have no value or point to no object.

```js
let y = null;
console.log(y); // Output: null
```

### 3. what will the output (true or false) of the following be?Explain why?

```js
console.log(null === undefined)

console.log(null == undefined)
```

The output for the given code will be:

```js
console.log(null === undefined); // false
console.log(null == undefined);  // true
```

### 4. What is event bubbling and event capturing (Event Propagation)? what is the difference between them? Can you give a code example to explain how you can use event bubbling ?

`Event Bubbling:`
`Definition:` Event bubbling is the default behavior in which the event starts from the target element that triggered the event and bubbles up to the root of the DOM tree.
`Order:` The innermost element's event handler is executed first, followed by its parent's, and so on, until the event reaches the root of the DOM.
`Method:` Use addEventListener with the default false value for the third parameter to enable event bubbling.

Example for bubbling:

index.html with 3 divs

```js
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
    <style>
        div {
            min-width: 100px;
            border: 1px solid black;
            min-height: 100px;
            padding: 30px;
        }
    </style>
  </head>
  <body>
    <div id="grandparent">
      <div id="parent">
        <div id="child"></div>
      </div>
    </div>
    <script src="index.js"></script>
  </body>
</html>
```

index.js

```js
document.querySelector("#grandparent").addEventListener("click", () => {
  console.log("grand parent clicked");
}, false);

document.querySelector("#parent").addEventListener("click", () => {
  console.log("parent clicked");
}, false);

document.querySelector("#child").addEventListener("click", () => {
  console.log("child clicked");
}, false);

```

output:

```js
child clicked
parent clicked
grand parent clicked
```

`Event Capturing:`
`Definition:` Event capturing is the opposite of event bubbling. The event starts from the root of the DOM tree and captures its way down to the target element.
`Order:` The root's event handler is executed first, followed by its children's, until the event reaches the target element.
`Method:` Use addEventListener with the true value for the third parameter to enable event capturing.

Example for capturing:

```js
document.querySelector("#grandparent").addEventListener("click", () => {
  console.log("grand parent clicked");
}, true);

document.querySelector("#parent").addEventListener("click", () => {
  console.log("parent clicked");
}, true);

document.querySelector("#child").addEventListener("click", () => {
  console.log("child clicked");
}, true);
```

output:

```
grand parent clicked
parent clicked
child clicked
```

### 5. What is function currying? Can you create a curried function and explain?

Function currying is a technique in functional programming where a function is transformed into a sequence of functions, each taking a single argument. The curried functions are created by partially applying the original function to one or more arguments. This allows for more flexible and reusable code.

Example:

```js
let multiply = (x, y) => {
  console.log(x * y);
};

// Create a curried function with the first argument set to 2
let multiplyByTwo = multiply.bind(this, 2);

// Call the curried function with the second argument set to 5
multiplyByTwo(5); // Output: 10

// Create another curried function with the first argument set to 3
let multiplyByThree = multiply.bind(this, 3);

// Call the second curried function with the second argument set to 5
multiplyByThree(5); // Output: 15
```

### 6. What is an IIFE (Immediately Invoked function expression)? Can you give an example?

An Immediately Invoked Function Expression (IIFE) is a function expression that is defined and executed immediately after its creation. It is a common JavaScript pattern used to create a private scope for variables, avoid polluting the global namespace, and execute code immediately.

```js
(function() {
  // Code inside this function is executed immediately
  console.log('IIFE executed!');
})();
```
