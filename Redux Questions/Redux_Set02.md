### 1.What do you understand by ACTIONs in Redux's architecture? Explain with example.

actions are plain JavaScript objects that represent events or payloads of data describing something that has occurred in the application

### 2. What are reducers in Redux's architecture? Show with an example.

reducers are functions responsible for specifying how the application's state changes in response to actions. Reducers take the current state and an action as arguments and return a new state based on the action type. Reducers must be pure functions, meaning they should not modify the existing state; instead, they should return a new state object.

```js
// Reducer
const counterReducer = (state = 0, action) => {
  switch (action.type) {
    case "INCREMENT":
      return state + 1;
    case "DECREMENT":
      return state - 1;
    default:
      return state;
  }
};
```

### 3. Explain the typical data flow in an application made using React and Redux (Redux Lifecycle for an application).

The typical data flow in a React application that utilizes Redux follows a unidirectional pattern. Understanding the Redux lifecycle involves recognizing how actions, reducers, the store, and React components interact

`Action Dispatch:` User or system interactions trigger the dispatch of actions.

`Reducer Handling:` Reducers receive actions and determine how the state should change.

`State Update:` The store updates its state based on the reducer's response.

`Store Notification:` Subscribed components are notified of the state change.

`React Component Update:` React components connected to the store re-render based on the updated state.

### 4.Name all the Redux Store methods. Explain each one of them in details with examples as to when to use them?

`createStore(reducer, [preloadedState], [enhancer]):` Creates a Redux store that holds the complete state tree of your application.

```js
import { createStore } from "redux";
import rootReducer from "./reducers";

const store = createStore(rootReducer);
```

`store.dispatch(action):` Dispatches an action, triggering a state change in the store.

```js
store.dispatch({ type: "INCREMENT" });
```

`store.getState():` Retrieves the current state from the store.

```js
const currentState = store.getState();
```

`store.subscribe(listener):` Adds a change listener to the store. It will be called any time an action is dispatched, potentially resulting in a state change.

```js
const unsubscribe = store.subscribe(() => {
  console.log("State updated:", store.getState());
});

// To unsubscribe later
unsubscribe();
```

### 9.What are middlewares in reducers? What are they used for? (Most asked interview question) Watch this video to understand

Middleware in the context of Redux refers to a way to augment or extend the behavior of the Redux store's dispatch function. It provides a third-party extension point between dispatching an action and the moment it reaches the reducer. Middleware can intercept actions, perform asynchronous operations, modify actions, or stop them from reaching the reducer altogether.

`Purpose of Middleware in Redux:`

`Asynchronous Operations:` Middleware allows you to handle asynchronous operations, such as making API calls, by intercepting an action and delaying its processing until the asynchronous operation is complete.

`Logging and Debugging:` Middleware can log information about dispatched actions, the current state, or other relevant data for debugging purposes. This helps in understanding how actions flow through the system.

`Conditionally Dispatching Actions:` Middleware can inspect actions and decide whether to let them proceed to the reducer. This enables conditional dispatching based on certain criteria.

`Modifying Actions:` Middleware can modify or transform actions before they reach the reducer. This is useful for injecting additional information or modifying the action payload.
