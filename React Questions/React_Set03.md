### 1.What are the different ways to style a React component?

- Inline Styles: Define styles directly in the JSX using the style attribute
- CSS Stylesheets: Create separate CSS files and import them into your React components.
  jsx
- CSS Modules: Use CSS Modules to scope CSS locally to a specific component.

### 2.Name a few techniques to optimize React app performance? Explain with code examples.

Optimizing the performance of a React application is crucial for delivering a smooth user experience. Here are a few techniques and best practices

`Code Splitting:`

Break your code into smaller chunks to be loaded on demand. This reduces the initial load time, Use React's React.`lazy` and Suspense for code splitting.

```js
const MyComponent = React.lazy(() => import('./MyComponent'));

const App = () => (
  <React.Suspense fallback={<div>Loading...</div>}>
    <MyComponent />
  </React.Suspense>
);
```

```js
<img src="image.jpg" alt="Example" loading="lazy" />
```

`Memoization:`

Use the React.memo higher-order component to memoize functional components and prevent unnecessary renders.

```js
const MemoizedComponent = React.memo(({ prop1, prop2 }) => {
  // Component logic
});
```

`Debouncing and Throttling:`

Use debouncing and throttling techniques to control the frequency of certain operations, like handling user input or resizing events.

```js
import { debounce } from 'lodash';

const handleSearch = debounce(searchFunction, 300);
```

### 3. What is the way for Parent to Child Communication? Give code example.

parent-to-child communication is achieved by passing props from a parent component to a child component. The parent component can pass data or functions as props, and the child component can access and use these props.

`ParentComp.js`

```js
import React, { useState } from "react";
import ChildComp from "./ChildComp";

const ParentComp = () => {
  const [message, setMessage] = useState("Hello from parent");
  const updateMsg = () => {
    setMessage("Update msg from parent");
  };
  return (
    <div>
      <h2>Parent Message : {message}</h2>
      <ChildComp message={message} updateMsg={updateMsg} />
    </div>
  );
};

export default ParentComp;
```

`ChildComp.js`

```js
import React from "react";

const ChildComp = ({ message, updateMsg }) => {
  return (
    <div>
      <p>Received from Parent: {message}</p>
      <button onClick={updateMsg}>Update message</button>
    </div>
  );
};

export default ChildComp;
```

### 5. What are the way to communicate between sibling components?

Communicating between sibling components in React typically involves lifting state up to a common ancestor (usually their parent or a higher-level component) and passing down props or functions.

`Lifting State Up:` Lift the shared state up to a common ancestor (parent or higher-level component) and pass it down to both siblings as props.

```js
// ParentComponent.jsx
import React, { useState } from 'react';
import SiblingComponentA from './SiblingComponentA';
import SiblingComponentB from './SiblingComponentB';

const ParentComponent = () => {
  const [sharedState, setSharedState] = useState('Initial state');

  const updateSharedState = (newState) => {
    setSharedState(newState);
  };

  return (
    <div>
      <SiblingComponentA sharedState={sharedState} updateSharedState={updateSharedState} />
      <SiblingComponentB sharedState={sharedState} />
    </div>
  );
};

export default ParentComponent;
```

```js
// SiblingComponentA.jsx
import React from 'react';

const SiblingComponentA = ({ sharedState, updateSharedState }) => {
  return (
    <div>
      <h3>Sibling Component A</h3>
      <p>Shared State: {sharedState}</p>
      <button onClick={() => updateSharedState('New state from A')}>Update State from A</button>
    </div>
  );
};

export default SiblingComponentA;
```

```js
// SiblingComponentB.jsx
import React from 'react';

const SiblingComponentB = ({ sharedState }) => {
  return (
    <div>
      <h3>Sibling Component B</h3>
      <p>Shared State: {sharedState}</p>
    </div>
  );
};

export default SiblingComponentB;
```

6. What are Higher Order Components in React? explain with code example. (Favourite Interview Question)

Higher Order Components (HOCs) in React are functions that take a component and return a new enhanced component with additional props, state, or behavior

```js
// HigherOrderComponent.jsx
import React, { Component } from 'react';

const withEnhancement = (WrappedComponent) => {
  class WithEnhancement extends Component {
    constructor(props) {
      super(props);
      this.state = {
        additionalData: 'Data from HOC',
      };
    }

    render() {
      // Pass the original props and additional data to the wrapped component
      return <WrappedComponent {...this.props} additionalData={this.state.additionalData} />;
    }
  }

  return WithEnhancement;
};

export default withEnhancement;
```

```js
// OriginalComponent.jsx
import React from 'react';
import withEnhancement from './HigherOrderComponent';

const OriginalComponent = ({ additionalData, otherProp }) => {
  return (
    <div>
      <h2>Original Component</h2>
      <p>Additional Data: {additionalData}</p>
      <p>Other Prop: {otherProp}</p>
    </div>
  );
};

export default withEnhancement(OriginalComponent);
```

```js
// App.jsx
import React from 'react';
import OriginalComponent from './OriginalComponent';

const App = () => {
  return (
    <div>
      <h1>App Component</h1>
      {/* Use the enhanced OriginalComponent */}
      <OriginalComponent otherProp="Some value" />
    </div>
  );
};

export default App;
```

### 8. What are custom hooks in react? Can you design one? (Favourite interview question)

Custom hooks in React are functions that encapsulate reusable logic and can be shared across multiple components. They allow you to extract and share stateful logic, side effects, or any other functionality in a modular and reusable way.

```js
// useCounter.js
import { useState } from 'react';

const useCounter = (initialValue = 0, step = 1) => {
  const [count, setCount] = useState(initialValue);

  const increment = () => {
    setCount(count + step);
  };

  const decrement = () => {
    setCount(count - step);
  };

  return {
    count,
    increment,
    decrement,
  };
};

export default useCounter;
```

In this example:

- The `useCounter` custom hook encapsulates the logic related to counting.
- It uses the `useState` hook to manage the count state.
- The hook returns an object with the current count value, as well as functions to increment and decrement the count.

```js
// CounterComponent.jsx
import React from 'react';
import useCounter from './useCounter';

const CounterComponent = () => {
  // Using the custom hook
  const { count, increment, decrement } = useCounter(0, 2);

  return (
    <div>
      <h2>Count: {count}</h2>
      <button onClick={increment}>Increment</button>
      <button onClick={decrement}>Decrement</button>
    </div>
  );
};

export default CounterComponent;
```
