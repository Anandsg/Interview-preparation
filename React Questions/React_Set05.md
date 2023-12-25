### 1.What is React Router?When should we use it?Give code example and explain it in detail.

React Router is a standard library for routing in React applications. It enables the navigation and dynamic rendering of components based on the URL. React Router helps you build single-page applications where different components are displayed based on the route

```
// App.jsx
import React from 'react';
import { BrowserRouter as Router, Route, Link, Switch } from 'react-router-dom';
import Home from './Home';
import About from './About';
import Contact from './Contact';
import NotFound from './NotFound';

const App = () => {
  return (
    <Router>
      <div>
        <nav>
          <ul>
            <li>
              <Link to="/">Home</Link>
            </li>
            <li>
              <Link to="/about">About</Link>
            </li>
            <li>
              <Link to="/contact">Contact</Link>
            </li>
          </ul>
        </nav>

        <hr />

        {/* Route components are rendered based on the current URL */}
        <Switch>
          <Route path="/" exact component={Home} />
          <Route path="/about" component={About} />
          <Route path="/contact" component={Contact} />
          <Route component={NotFound} />
        </Switch>
      </div>
    </Router>
  );
};

export default App;
```

### 2. How to pass data between sibling components using React router?

Let's say we have two sibling components, Sender and Receiver, and we want to pass data from Sender to Receiver through the URL.

```
// App.jsx
import React from 'react';
import { BrowserRouter as Router, Route, Link } from 'react-router-dom';
import Sender from './Sender';
import Receiver from './Receiver';

const App = () => {
  return (
    <Router>
      <div>
        <nav>
          <ul>
            <li>
              <Link to="/sender">Sender</Link>
            </li>
            <li>
              <Link to="/receiver">Receiver</Link>
            </li>
          </ul>
        </nav>

        <hr />

        {/* Define routes for Sender and Receiver */}
        <Route path="/sender" component={Sender} />
        <Route path="/receiver" component={Receiver} />
      </div>
    </Router>
  );
};

export default App;
```

### What is `useCallback`? When should we use it?

`useCallback` is a React Hook that is used to memoize functions, preventing them from being recreated on every render. This can be useful in scenarios where you have a function that depends on certain dependencies, and you want to avoid unnecessary re-creation of that function to optimize performance.

### 4. What does useMemo do? Give code example to explain when will you use it.

useMemo is a React Hook that is used for memoization. It memoizes the result of a computation, ensuring that the computation is only re-executed when the dependencies change. This can be particularly useful when you have expensive calculations or operations that you want to avoid repeating on every render.

```
import React, { useState, useMemo } from 'react';

const FactorialCalculator = ({ number }) => {
  const calculateFactorial = (num) => {
    console.log(`Calculating factorial for ${num}`);
    if (num === 0 || num === 1) {
      return 1;
    }
    return num * calculateFactorial(num - 1);
  };

  // Using useMemo to memoize the result of the factorial calculation
  const factorial = useMemo(() => calculateFactorial(number), [number]);

  return (
    <div>
      <p>Factorial of {number} is: {factorial}</p>
    </div>
  );
};

const App = () => {
  const [inputNumber, setInputNumber] = useState(5);

  return (
    <div>
      <input
        type="number"
        value={inputNumber}
        onChange={(e) => setInputNumber(parseInt(e.target.value))}
      />
      <FactorialCalculator number={inputNumber} />
    </div>
  );
};

export default App;
```

### 6. What is the use of context API ? When should we use it? How does Context Api work?

The Context API in React is a mechanism for sharing state between components without explicitly passing props through the component tree. It provides a way to pass data down to deeply nested components without having to manually pass props at each level. Context is often used for sharing global data or application state that many components need access to.

When to Use the Context API: Global State Management, Avoiding Prop Drilling, Sharing Configuration Settings

### 7. What is the use of babel ?

`Code Splitting:` Babel supports code splitting, a technique used to split code into smaller chunks that can be loaded on demand. This helps improve page load times by reducing the initial payload.

`Tree-shaking:` Babel supports tree-shaking, a technique that eliminates dead code (unused modules or functions) during the build process. This helps reduce the size of the final bundle.
