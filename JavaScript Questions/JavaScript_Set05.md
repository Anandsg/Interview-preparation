### 1. When do we use async await ?

`async/await` is used in JavaScript to simplify the handling of asynchronous code. It is particularly useful in scenarios where you need to work with promises, such as making API calls, reading from files, or any other asynchronous operation. Here are some common use cases for async/await:

example:

```js
async function fetchData() {
  try {
    const result = await fetch('https://api.example.com/data');
    const data = await result.json();
    console.log(data);
  } catch (error) {
    console.error('Error:', error);
  }
}
```

### 2. What is the reason behind writing await inside async function only?

The `await` keyword can only be used inside functions marked with the async keyword. This restriction is in place because the await keyword is designed to work with asynchronous operations, and using it implies a specific behavior related to the handling of promises.

### 3. What will the output of this be?

```js
async fun fun1() {
console.log('a');
console.log('b');
await setTimeout(() => console.log('c'), 1000)
await setTimeout(() => console.log('d'), 0)
console.log('e');
 }
fun1()
```

Explain the reason behind the answer?

Output:

```
a
b
e
d
c
```

explaintation :

- The fun1 function is declared as an asynchronous function using the async keyword.

- When fun1 is called, the first two console.log statements (a and b) are executed immediately.

- The await setTimeout(() => console.log('c'), 1000) line introduces a delay of 1000 milliseconds using setTimeout. During this delay, the control returns to the calling environment, allowing other synchronous tasks to proceed.

- The await setTimeout(() => console.log('d'), 0) line introduces a minimal delay of 0 milliseconds using setTimeout. Despite the delay being set to 0 milliseconds, it still behaves asynchronously and allows other synchronous tasks to execute before its callback.

- The console.log('e') statement is executed while waiting for the previous asynchronous tasks (timeouts) to complete.

- The callbacks inside the setTimeout functions are executed once their respective delays have passed. Since the delay for 'd' is minimal (0 milliseconds), it's the next to execute, followed by 'c'.

### 4. can you solve thee above problem, so that we get proper outputs ? Hint await should works properly.

To ensure that await works as expected with setTimeout, we can use a Promise-based approach. The setTimeout function does not inherently return a Promise

```js
async function fun1() {
  console.log('a');
  console.log('b');

  // Wrap setTimeout in a Promise
  const delay = (ms) => new Promise(resolve => setTimeout(resolve, ms));

  // Use await with the Promise-based delay
  await delay(1000);
  console.log('c');

  await delay(0);
  console.log('d');

  console.log('e');
}

fun1();
```

Output:

```
a
b
c
d
e
```

### 5. What are callback? What is Callback hell? Can you give an example of callback hell?

callback is a function passed as an argument to another function, which is then invoked inside the outer function. Callbacks are commonly used in asynchronous programming to handle tasks that depend on the completion of a prior operation.

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

In this example, `handleData` is a callback function passed to fetchData, and it gets executed once the `asynchronous` operation inside `fetchData` is complete.
