### What is Redux?

Redux is a state management library for JavaScript applications, particularly those built with libraries or frameworks like React. It provides a predictable state container that helps manage the state of an application in a consistent and scalable way

### 2.Why do we even need redux? How is it better than context API?

Redux and the Context API in React serve different purposes, but they both address the challenge of state management in applications. The choice between Redux and the Context API often depends on the specific requirements and complexity of the application.

`Why Use Redux?`
`Centralized State Management:`

Redux provides a centralized store for managing the state of the entire application. This makes it easy to reason about the state and ensures a single source of truth.

`Predictable State Changes:`

Redux enforces a strict unidirectional data flow, making it predictable how state changes occur in the application. Actions trigger changes, and reducers specify how the state should be updated.

`Debugging Capabilities:`

Redux DevTools offer powerful debugging capabilities, allowing developers to track state changes, inspect the state at any point in time, and even time-travel through actions.

`Middleware Support:`

Redux has a middleware architecture that allows developers to extend the behavior of the store. This is useful for handling asynchronous operations, logging, and other side effects.

### What is Flux?

Flux is an architectural pattern used for building scalable and maintainable web applications. It was developed by Facebook to address the challenges of managing the flow of data in large and complex React applications. Flux is not a library or a framework; instead, it's a set of principles and patterns that guide the organization of code and data flow in an application.

### 6.Is it true that Redux can only be used with React?

`No`, it is not true that Redux can only be used with React. While Redux was originally created in the context of React applications, it is a standalone state management library for JavaScript and can be used with `various libraries`.

### 7. How do you decided which state to make a reducer and which statue you want to make local state?

The decision often involves considering the nature of the state, the component's responsibilities, and the overall application architecture.
