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

