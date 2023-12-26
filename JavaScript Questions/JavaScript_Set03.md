### Question 1: What is output of this.

```js
setImmediate(() => {
  console.log("first");
});

setTimeout(() => {
  console.log("second");
});

console.log("third");
```

- The console.log("third") statement is executed immediately.
- The setImmediate callback is executed in the next iteration of the event loop, so "first" is printed.
- The setTimeout callback is scheduled to be executed after a minimum of 1 millisecond, but there's no guaranteed order when compared to setImmediate

So, the expected output will be:

```
third
first
second
```

### Question 2 : Difference between SetImmidiate and Process.nexttick

`process.nextTick:` Executes the callback at the end of the current event loop cycle, before continuing to the next cycle.

`setImmediate:` Executes the callback in the next iteration of the event loop, but after I/O events.

### Question 3: What is difference between promise and call back

`Callback:`

- Callbacks are functions that are passed as arguments to other functions.
- They are commonly used in asynchronous programming to specify what should happen after the completion of an asynchronous operation.
- Callbacks can lead to "callback hell" or "pyramid of doom" when multiple asynchronous operations are nested, making the code harder to read and maintain.
- Error handling in callbacks can be challenging, and it may result in error-prone code.

`Promise:`

- Promises are objects representing the eventual completion or failure of an asynchronous operation.
- They provide a more structured way to handle asynchronous code, especially when dealing with multiple async operations sequentially or in parallel.
- Promises help mitigate callback hell and make code more readable by allowing a more linear flow of logic.
- Promises have built-in error handling through the .catch() method, making it easier to manage errors in asynchronous code.

### Question 4 : What is output ?

```js
let a = new Promise((resolve, reject) => {
  reject({ msg: 'Something went wrong' });
});

a.then(resolve => {
  console.log(resolve);
}).catch(err => {
  console.log(err.msg);
});
```

Explaination:

- You create a new Promise called a.
- In the executor function of the Promise, you immediately reject it with an object containing a msg property.
- You use a.then() to handle the resolution of the Promise, but since it was rejected, the then block is skipped.
- You use a.catch() to handle the rejection, and it logs the error message ('Something went wrong') to the console.

So, the output will be:

```
Something went wrong
```

### Question 5 : what is output ?

```js
async function myFunction() {
  await delay(6000);

  setTimeout(() => {
    console.log("first");
  }, 10000);

  console.log("second");
}

myFunction();
```

- await delay(6000) pauses the execution of the myFunction for 6000 milliseconds (6 seconds).
- After waiting for 6000 milliseconds, the function proceeds to the next line.
- setTimeout(() => { console.log("first"); }, 10000) schedules the execution of the callback after 10000 milliseconds (10 seconds), but it doesn't block the execution of the function.
- console.log("second") is executed immediately after await delay(6000).

```
second
first      -->  is printed after 10 seconds
```

### Question 6 : What is function definition ?

A function definition in programming is a block of code that specifies the actions or computations performed by a function when it is invoked or called. In JavaScript, a function can be defined using the `function` keyword. Here's the basic syntax for function definition:

```js
function functionName(parameters) {
  // Code block or statements
  // Actions or computations to be performed
  // Optionally, return a value
}
```