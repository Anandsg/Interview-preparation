### Question 1: What is the difference between `let` and `const`? What is the difference between `let` and `var`?

|                  | `let`                                                               | `const`                                                                  | `var`                                                                       |
| ---------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------------ | --------------------------------------------------------------------------- |
| **Mutability**   | Variables declared with `let` are mutable.                          | Variables declared with `const` are immutable.                           | Variables declared with `var` are mutable.                                  |
| **Reassignment** | Values assigned to variables declared with `let` can be reassigned. | Values assigned to variables declared with `const` cannot be reassigned. | Values assigned to variables declared with `var` can be reassigned.         |
| **Block Scope**  | Variables declared with `let` have block scope.                     | Variables declared with `const` have block scope.                        | Variables declared with `var` have function scope.                          |
| **Hoisting**     | Variables declared with `let` are hoisted, but not initialized.     | Variables declared with `const` are hoisted, but not initialized.        | Variables declared with `var` are hoisted and initialized with `undefined`. |
| **Example**      | ```js                                                               | ```js                                                                    | ```js                                                                       |
|                  | let x = 10;                                                         | const y = 30;                                                            | var z = 50;                                                                 |
|                  | x = 20; // Valid                                                    | // y = 40; // Invalid, will throw an error                               | z = 60; // Valid                                                            |

This README provides a quick reference guide on the differences between `let`, `const`, and `var` in JavaScript. Feel free to copy and paste this into your project's README file, and customize it as needed.

### Question 2 : what is output of this function

```js
function sample () {

for (let i=0; i<=5;i++) {

setTimeout (() => console.log(i), 1000 );
   }
}
```

There is a common issue related to the use of setTimeout inside a loop. The for loop runs `synchronously`, and the setTimeout is `asynchronous`. This means that by the time the setTimeout callbacks are executed, the loop has already completed, and the value of i will be the final value, which is `6` in this case.

### Question 3 : what is output of this

```js
SetTimeout(()=> {
console.log("a");
},2000)

console.log("b") ;
```

The setTimeout function schedules the execution of the provided function after a delay of 2000 milliseconds (2 seconds). Meanwhile, the console.log("b") statement is executed immediately.

"b" will be printed to the console immediately.
After 2 seconds, "a" will be printed to the console.

Output will be:

```
b
a
```

### Question 4: how can you print a first and b later with. You are not allowed to use any extra setTimeouts?

```js
function delay(ms) {
  return new Promise(resolve => setTimeout(resolve, ms));
}

async function printOrder() {
  await delay(2000);
  console.log("a");
  console.log("b");
}

printOrder();
```

In this example, the `delay` function returns a promise that resolves after a specified number of milliseconds. The printOrder function uses `await` to wait for the delay of 2000 milliseconds before printing "a" and "b" sequentially. This way, "a" is printed first, and "b" is printed later, meeting the specified requirement without using additional setTimeout calls.
