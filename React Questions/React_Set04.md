### 1.What is reconciliation in React?

Reconciliation in React refers to the process of updating the user interface to reflect changes in the underlying data or state. When the state or props of a component change, React needs to figure out what part of the UI needs to be updated to reflect those changes efficiently.

### What are fragments? How are they better than other div elements?

In React, fragments are a way to group multiple children elements without adding an additional parent container to the DOM. They are represented by the React.Fragment component or the shorthand syntax `<>...</>`

```
import React from 'react';

const MyComponent = () => {
  return (
    <>
      <p>Child 1</p>
      <p>Child 2</p>
    </>
  );
};
```

### 3. What element get introduced into the DOM when we use fragments? How does it work?

When you use fragments in React, they do not introduce any additional element into the DOM. Unlike a regular container element like `<div>`, which adds an extra DOM node to the structure, fragments don't create a new parent element. Fragments exist purely in the React Virtual DOM and do not have a corresponding HTML representation.

### 5. Why React uses className over class attribute?

the attribute used for defining the class of an HTML element is named `className` instead of `class`. This is because class is a `reserved` keyword in JavaScript, and JSX is a syntax extension that allows embedding XML-like code within JavaScript. Therefore, to avoid naming conflicts with the JavaScript keyword class, React uses className to define the CSS class for elements.

### 6.What is children prop? When should we use it ? Give an example to explain it

the children prop is a special prop that allows components to accept and render content or components passed as children between the opening and closing tags of the component. This is particularly useful when you want to create reusable components that can encapsulate and manipulate arbitrary content.
