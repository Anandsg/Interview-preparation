### what is process.nextTick ?

process.nextTick is a method in Node.js that allows a callback to be added to the next tick of the event loop. It provides a way to execute a callback function immediately after the current event loop cycle, before continuing with any other I/O events or timers.

```js
console.log("Start");

process.nextTick(() => {
  console.log("Next Tick Callback");
});

console.log("End");
```

In this example, "Start" and "End" will be printed first, and then "Next Tick Callback" will be printed. The process.nextTick callback is executed before the event loop moves to the next phase.

### Question 7: how can you check if a variable is an array?

To check if a variable is an array in JavaScript, you can use the Array.isArray() method.

```js
let myVariables = [1,2,3,4];
if(Array.isArray(myVariables)){
  console.log("This is an array");
} else {
  console.log("This is not an array")
}
```
