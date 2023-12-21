### 1. What is React? What are the advantages of using React , compared to normal Javascript?

React is an open-source JavaScript library used for building user interfaces, particularly for single-page applications where user interactions are dynamic and frequent.

Advantages of React :

`Virtual DOM:` React uses a virtual DOM to improve performance. Instead of directly updating the real DOM for every change, React updates a virtual representation of the DOM and then efficiently updates the real DOM only where necessary.

`Component-Based Architecture:` React follows a component-based architecture, where UIs are built as a composition of reusable components.

`Declarative Syntax:` React uses a declarative syntax, which means you describe how your UI should look based on the application state.

`One-Way Data Binding:` React follows a unidirectional data flow, which makes it easier to understand how data changes over time. Data flows in a single direction, from parent to child components.

`React Hooks:` Introduced in React 16.8, hooks provide a way to use state and lifecycle features in functional components. This allows developers to use state and other React features without writing a class.

### 2. What is difference between library and framework? Is React a library or a framework? Explain the reason?

`library`: A library is a collection of pre-written code that can be used by developers to perform common tasks. It provides specific functions and methods that developers can call to achieve certain functionalities.

`framework`: Frameworks often come with a predefined structure, design patterns, and a set of tools to streamline the development process. Developers write code that fits into the framework, and the framework takes care of the flow of control.

### 3. What is useState() in React? What does usestate return? What does it take as argument? Give code example of usestate?

useState is hook that allows functional components to manage state.

`Return Value:` useState returns an array with two elements. The first element is the current state value, and the second element is a function that allows you to update the state.

`Arguments:` The useState function takes one argument, which is the initial state value.

Code example :

```
const App = () => {
  const [count, setIncrement] = useState(0); // UseState declaration

  const IncrementOnClick = () => {
    setIncrement(count + 1);
  };

  return (
    <div>
      <p>count : {count}</p>
      <button onClick={IncrementOnClick}>Increment</button>
    </div>
  );
};
```

### 4. What are state variables in react ? How are they different from normal variables? How do we decide when to use states and when to use normal variables?

State variables: state variables are used to store and manage the mutable data of a component. State allows components to keep track of information that can change over time.

example of state variable:

```
import React, { useState } from "react";

const App = () => {
  const [name, setName] = useState('Anand');
  return <div>{name}</div>
};

export default App;
```

Normal variables: Normal variables are mutable but changing them doesn't trigger a re-render in React.

```
import React from "react";
const App = () => {
  const name1 = "Anand1";

  return <div>{name1}</div>;
};

export default App;
```

### 5. What are keys in React? When should we use it? what is the advantage of keys?

key is a special attribute that is used to uniquely identify and differentiate between elements in a collection. Keys are primarily used when rendering lists of elements (such as an array of JSX elements) to help React identify which items have changed.

```
const ItemList = ({ items }) => {
  return (
    <ul>
      {items.map((item) => (
        <li key={item.id}>{item.name}</li>
      ))}
    </ul>
  );
};
```

### 6.What is JSX? How does JSX work?

JSX, or JavaScript XML, is a syntax extension for JavaScript that looks similar to XML or HTML. JSX is commonly associated with React, a JavaScript library for building user interfaces. JSX provides a more readable and concise way to write React components by allowing developers to write HTML-like code directly in their JavaScript files.

### 7. What is DOM? What is the virtual DOM? How does react use the virtual DOM to render the UI?

DOM (Document Object Model): The Document Object Model (DOM) is a programming interface for web documents. It represents the structure of a document as a tree of objects, where each object corresponds to a part of the document, such as elements, attributes, and text

`The Virtual DOM`: is a concept used by React to optimize the updating of the actual DOM. It is an in-memory representation of the actual DOM elements. Instead of directly manipulating the DOM every time the state of a React component changes, React uses a virtual DOM to perform a minimal set of updates and then efficiently applies those updates to the actual DOM.

`Virtual DOM Comparison:`
When the state of a component changes, React creates a new virtual DOM tree representing the updated state.

`Diffing Algorithm:` it is also known as "reconciliation" or "diffing" to compare the new virtual DOM with the previous one. It identifies the differences (or changes) between the two trees.

### 8.What are the differences between controlled and uncontrolled components? Design of controlled and unontrolled component and paste the code here?

`Controlled components` : React maintains and controls the state of the form elements. The component's state is managed through React, and any changes to the input values are handled by React through state updates.

```
import React, { useState } from "react";
const App = () => {
  const [inputValue, setInputValue] = useState("");

  const handleInputChange = (event) => {
    setInputValue(event.target.value);
  };
  return (
    <div>
      <input onChange={handleInputChange} value={inputValue} type="text" />
      <p>Input : {inputValue}</p>
    </div>
  );
};

export default App;
```

In this example:

- The input value is controlled by the inputValue state variable.
- The value attribute of the input is set to the controlled state (inputValue).
- The onChange event updates the state (inputValue) whenever the input value changes.

`Uncontrolled Components:` The form element's state is not managed by React. Instead, the DOM itself handles the state, and React only interacts with the DOM when necessary.

```
import React, { useRef } from "react";
const App = () => {
  const inputRef = useRef();

  const handleInputChange = () => {
    const InputValues = inputRef.current.value;
    console.log("uncontrolled input value:", InputValues);
  };
  return (
    <div>
      <input ref={inputRef} />
      <button onClick={handleInputChange}>Get Values</button>
    </div>
  );
};

export default App;
```

In this example:

- The input value is not controlled by React; it's managed directly by the DOM.
- The ref attribute is used to create a reference to the input element (inputRef).
- The value of the input is obtained directly from the DOM using inputRef.current.value when needed.
