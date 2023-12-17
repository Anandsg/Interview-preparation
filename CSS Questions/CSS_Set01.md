## CSS Interview questions SET01

### 1. What is the Box model in CSS? Which CSS properties are a part of it?

The CSS Box Model is a fundamental concept that describes the layout and sizing of elements on a web page. It conceptualizes each HTML element as a rectangular box with four main components: `content, padding, border, and margin.`

```
+-----------------------------------------+
|                  Margin                 |
|   +--------------------------------+    |
|   |              Border            |    |
|   |   +------------------------+   |    |
|   |   |         Padding        |   |    |
|   |   |  +------------------+  |   |    |
|   |   |  |      Content      | |   |    |
|   |   |  +------------------+  |   |    |
|   |   +------------------------+   |    |
|   +--------------------------------+    |
|                                         |
+-----------------------------------------+
```

### 2. What is specificity?

Specificity in CSS refers to the set of rules that determine which style rules are applied to an element when there are conflicting styles. It's a way of resolving conflicts between different CSS selectors targeting the same element.

`Number of ID Selectors:` The more ID selectors in a selector, the higher the specificity.

`Number of Class and Attribute Selectors:` The more class selectors, attribute selectors, and pseudo-class selectors in a selector, the higher the specificity.

`Number of Type Selectors:` The more type selectors in a selector, the higher the specificity.

### 3. How to align a block element inside another element? Give code example.

To align a block element inside another element, you can use CSS properties such as `margin`, `position`, or `flexbox`, depending on your specific layout requirements.

for example:

```
    .container {
      position: relative;
      width: 300px;
      height: 200px;
      background-color: #eee;
    }

    .centered {
      position: absolute;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%);
      width: 100px;
      height: 100px;
      background-color: #3498db;
    }
```

### 4. Difference between Static, Relative, Absolute and Fixed position?

`Static Position (position: static;):` This is the default positioning for all elements. The top, right, bottom, and left properties have no effect when position is static.

`Relative Position (position: relative;):` The top, right, bottom, and left properties can be used to offset the element from its normal position without affecting the position of other elements.

`Absolute Position (position: absolute;):` Elements with position: absolute; are removed from the normal document flow and positioned relative to their nearest positioned ancestor.

`Fixed Position (position: fixed;):` Elements with position: fixed; are removed from the normal document flow and positioned relative to the viewport (browser window). The element remains `fixed` in its position even when the page is scrolled.

### 5. Difference between visibility:hidden; and display:none;

visibility: hidden; and display: none; are both CSS properties used to hide elements on a web page.

`Visibility (visibility: hidden;):` The visibility property is used to hide or show an element without affecting the layout of the page.

`Display (display: none;):` The display property is used to completely remove an element from the layout of the page.

### 1. What is shadow DOM?Give an example.

The Shadow DOM (Document Object Model) is a web standard that allows encapsulation of a DOM subtree and its associated CSS styles, scripts, and markup into a container, known as a "shadow tree." This encapsulation helps in creating isolated components on a web page, preventing styles and scripts from bleeding into or being affected by the outer document.

for example:

```
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Shadow DOM Example</title>
  <style>
    /* Styles outside the Shadow DOM */
    .outer-container {
      border: 1px solid #ccc;
      padding: 10px;
      margin: 20px;
    }

    /* Styles inside the Shadow DOM */
    .inner-container {
      display: block;
      background-color: #f0f0f0;
      padding: 10px;
    }
  </style>
</head>
<body>

<!-- Regular DOM element -->
<div class="outer-container">
  <p>This is a regular DOM element.</p>
</div>

<!-- Element with Shadow DOM -->
<div id="shadow-container"></div>

<script>
  // Access the shadow container
  const shadowContainer = document.getElementById('shadow-container');

  // Create a shadow root for the element
  const shadowRoot = shadowContainer.attachShadow({ mode: 'open' });

  // Create an element inside the shadow root
  const innerElement = document.createElement('div');
  innerElement.classList.add('inner-container');
  innerElement.textContent = 'This is inside the Shadow DOM.';

  // Append the inner element to the shadow root
  shadowRoot.appendChild(innerElement);
</script>

</body>
</html>
```

- The regular DOM element with the class outer-container has some styles defined outside the Shadow DOM.
- The element with the ID shadow-container is used to demonstrate the Shadow DOM. The attachShadow method is used to create a shadow root for this element.
- Inside the shadow root, an element with the class inner-container is created, and styles defined within the shadow DOM are applied to it.

### 2. How to build a triangle in css? Give code example.

```
.tri {
  height: 0px;
  width: 0px;
  border-left: 50px solid transparent;
  border-right: 50px solid transparent;
  border-bottom: 88px solid black;
}
```

### 3. What are pseudo elements?Give Examples.

Pseudo-elements in CSS are used to style specific parts of an element. They allow you to style certain parts of an element's content or generate additional content without modifying the HTML markup. Pseudo-elements are denoted by a double colon (::) followed by the name of the pseudo-element.

```
::before and ::after
These pseudo-elements are used to insert content before and after the content of an element, respectively.
```

### 4. What are Data attributes?

These attributes are prefixed with "data-" followed by a descriptive name, allowing developers to associate arbitrary data with HTML elements without affecting the element's default behavior or styling.

Synrax:

```
<div data-attribute-name="value">Content</div>
```
