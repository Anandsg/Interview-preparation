### 1.What are props in React? What is the difference between React state and props.

`Props:` are a mechanism for passing data from a parent component to its child components in React. They allow you to communicate and share information between components

```
import React from "react";

const Greet = (props) => {
  return <div>{props.name}</div>;
};

const App = () => {
  return (
    <div>
      <Greet name="John" />
    </div>
  );
};

export default App;
```

2. What is prop drilling in React? What are the better ways to prevent prop drilling which you know?

Prop drilling occurs when a parent component generates its state and passes it down as props to its children components that do not consume the props – instead, they only pass it down to another component that finally consumes it.

Example of props drilling :

```
import React, { useState } from "react";

const App = () => {
  const [profile, setProfile] = useState({ name: "Anand" });
  return <Header profile={profile} />;
};

const Header = ({profile}) => {
  return (
    <div>
      <h2>this is header</h2>
      <Content profile={profile} />
    </div>
  );
};

const Content = ({profile}) => {
  return (
    <div>
      <h2>{profile.name}</h2>
    </div>
  )
}

export default App;
```

`Ways to Prevent Prop Drilling:` using Context API, Redux, Higher order component, Custom hooks

### 3.What are error boundaries? How is the error boundary different from other components?

Error boundaries are special React components that catch JavaScript errors anywhere in their component tree and log those errors, display a fallback UI, and prevent the entire application from crashing.

### 4.What are React Hooks? How are hooks different from normal functions?

React Hooks are functions that enable functional components to use state and other React features that were previously only available in class components. They were introduced in React version 16.8 to address the complexity and verbosity of managing stateful logic in functional components.

`Differences from Normal Functions`

`State in Functional Components:`

`Normal Functions:` Regular functions (non-hooks) do not provide a built-in way to manage state within functional components. State is typically managed in class components using this.state and this.setState.
`React Hooks:` Hooks like useState enable functional components to manage state locally. State can be declared and updated within the functional component itself.

### 5. What are the 2 rules that must be followed while using React Hooks? What is the reason behind such rules?

`Only Call Hooks at the Top Level:`

Hooks must always be called at the top level of a functional component or a custom hook. They should not be called conditionally or within loops, nested functions, or other control flow statements.

```
import React, { useState, useEffect } from 'react';

const MyComponent = () => {
  const [count, setCount] = useState(0);

  useEffect(() => {
    // Effect code here
  }, [count]);

  // Component code here

  return <div>{count}</div>;
};
```

`Only Call Hooks from React Functions:`

Hooks must only be called from functional components or custom hooks. They should not be called from regular JavaScript functions, class components, or any non-functional context.

```
import React, { useState, useEffect } from 'react';

const MyComponent = () => {
  const [count, setCount] = useState(0);

  useEffect(() => {
    // Effect code here
  }, [count]);

  // Component code here

  return <div>{count}</div>;
};
```

### When does a functional component rerender? (Explain lifecycle of functional components?)

functional components are a type of component that is defined as a JavaScript function. With the introduction of React Hooks, functional components can now also have state and lifecycle features

`Mounting Phase:`
`useEffect with an empty dependency array ([]):`

The code inside this useEffect runs after the first render. It is equivalent to componentDidMount in class components.
This is where you perform actions that should only happen once when the component is mounted.
useEffect with a cleanup function:

If the useEffect function returns a cleanup function, it will be executed when the component is unmounted.
This is equivalent to componentWillUnmount in class components.

`Updating Phase:`
`useEffect with dependencies:`

If you pass dependencies to the dependency array in useEffect, the code inside the useEffect will run whenever any of those dependencies change.
This is similar to the componentDidUpdate lifecycle method in class components.
useEffect without dependencies:

If you omit the dependency array, the useEffect code will run after every render.
This is similar to componentDidUpdate in class components without a specific check for changes.

`Unmounting Phase:`
`Cleanup function in useEffect:`

If the useEffect has a cleanup function, it will be executed when the component is unmounted.
This is equivalent to componentWillUnmount in class components.

### 7. When does the return statement of a functional component get called?

The `return` statement is called during the initial render when the component is mounted.

### 8. What is the use of useEffect React Hooks? When does the useEffect hook get called in the lifecycle of react functional components?

useEffect is a React Hook that allows you to perform side effects in your functional components. Side effects can include data fetching, subscriptions, manually changing the DOM, or any other operations that are not part of the component rendering process.

The useEffect hook gets called during the lifecycle of a React functional component in three main scenarios:

`Mounting Phase:` When the component is initially rendered (mounted), the useEffect hook with an empty dependency array ([]) is called after the first render.

```
useEffect(() => {
  // Code here runs after the first render (componentDidMount)
  return () => {
    // Cleanup code (componentWillUnmount)
  };
}, []);
```

`Updating Phase:` When the component is re-rendered due to changes in state or props, the useEffect hook with dependencies is called after each render.

```
useEffect(() => {
  // Code here runs after every render (componentDidUpdate)
  return () => {
    // Cleanup code (runs before the next effect)
  };
}, [dependency1, dependency2]);
```

`Unmounting Phase:` If the useEffect hook returns a cleanup function, that cleanup function is called before the component is unmounted.

```useEffect(() => {
  // Code here runs after the first render (componentDidMount)
  return () => {
    // Cleanup code (componentWillUnmount)
  };
}, []);
```
