## HTML Interview questions SET01

### 1. Are the `HTML tags` and `elements` the same thing?

`HTML tags` are fundamental building block of HTML. It is a keyword surrounded by angle brackets, such as `<p>` for a paragraph or `<img>` for an image. Tags are used to define and mark up HTML elements.

`elements` are consists of a start tag, content, and an end tag (if applicable). For example, a paragraph element `<p>` consists of a start tag `<p>`, content the actual text or other elements within the paragraph, and an end tag `</p>`. Some elements, like the line break `<br>` or image `<img>`, don't have closing tags.

### 2. What are `tags` and `attributes` in HTML?

`tags` are keywords surrounded by angle brackets `(<>)`. They define and structure the elements on a webpage.

`attributes` are always included in the opening tag and are written as name/value pairs.

### 3. What are `void` elements in HTML?

`Void` elements, also known as `self-closing` or `empty elements`, are HTML elements that do not have a closing tag. Instead, they stand alone as a single tag and may include attributes.

for example:

```
<img src="example.jpg" alt="An example image">
```

### 4. What are different types of lists in HTML? Explain the difference between each one of them.

There are 3 types:

```
ordered lists
unordered lists, and definition lists
```

`Ordered Lists (<ol>)`: An ordered list is used to represent a list of items in a specific order or sequence. The `(<ol>)` element is used to define an ordered list, and each list item is defined using the `<li>` (list item) element.

for example:

```
<ol>
  <li>First item</li>
  <li>Second item</li>
  <li>Third item</li>
</ol>
```

`Unordered Lists (<ul>)`: An unordered list is used to represent a collection of items without any specific order or sequence. The `<ol>` element is used to define an ordered list, and each list item is defined using the `<li>` (list item) element.

for example:

```
<ul>
  <li>Item one</li>
  <li>Item two</li>
  <li>Item three</li>
</ul>
```

`Definition Lists (<dl>, <dt>, and <dd>)`: A definition list is used to represent a list of terms and their corresponding definitions. The `<dt>` (definition term) element is used to define terms, and the `<dd>` (definition description) element is used to define their corresponding definitions.

for example:

```
<dl>
  <dt>Term 1</dt>
  <dd>Definition 1</dd>
  <dt>Term 2</dt>
  <dd>Definition 2</dd>
</dl>
```

### 5. What is the ‘class’ attribute in HTML?What is the difference between the ‘id’ attribute and the ‘class’ attribute of HTML elements?

The `class` attribute is used to assign one or more class names to an HTML element. Class names are used to apply styles to multiple elements with a common set of properties.

for example:

```
<p class="highlight">This is a highlighted paragraph.`</p>`
```

The `id` attribute is used to uniquely identify a single HTML element on a page.

for example:

```
<div id="header">This is the header.</div>
```

### 6. How to optimize website assets `loading`?

There are several ways that we can optimize website assets loading

- Reduce the number of elements on a page, such as images, scripts, and stylesheets, to minimize the number of HTTP requests required to load the page

- Combine multiple CSS or JavaScript files into a single file to reduce the number of requests.

- Minify CSS, JavaScript, and HTML files to remove unnecessary characters, whitespace, and comments, reducing file sizes.

- Compress images to reduce file sizes without significant loss of quality.

### 7. What is the difference between `<strong>`, `<b>` tags and `<em>`, `<i>` tags?

The `<strong>, <b>, <em>,` and `<i>` tags in HTML are used to apply styles and convey semantic meaning to text

`<strong>` Tag: Represents text that is of strong importance, usually indicating that the text should be emphasized for semantic reasons.

`<b>` Tag: it was used to make text bold for styling purposes.

`<em>` Tag: Represents text that should be emphasized for semantic reasons, indicating a change in emphasis or stress.

`<i>` Tag: it was used to make text italic for styling purposes.

### 8. What is the significance of `<head>` and `<body>` tag in HTML?

`<head>` Tag: it contains meta-information about the HTML document, which is not displayed on the webpage itself.

`<body>` Tag: it contains the actual content of the webpage that will be displayed in the browser.

### 9. Can we display a web page inside a web page or Is nesting of webpages possible?

In HTML, it is not possible to directly embed or nest an entire web page inside another web page.

### 10. What are `inline` elements? What are block level elements? What is the difference between them?

`Inline Elements:` Inline elements do not start on a new line and only take up as much width as necessary and They do not force a new line to begin after the element.

for example:

```
`<span>, <a>, <strong>, <em>, <img>, <br>, <i>, <code>, etc.`
```

`Block-Level Elements:` Block-level elements start on a new line and stretch out to the full width of their container, forcing a new block or "box" to begin.

for example:

```
`<div>, <p>, <h1> to <h6>, <ul>, <ol>, <li>, <table>, <form>, etc.`
```

### 11. In how many ways can we position an HTML element? What are the permissible values of the position attribute? Explain the exact difference each one of them in your own words.

`Static:` Elements are placed in the normal flow of the document. Any positioning properties specified have no effect.

`Relative:` Elements are positioned relative to their normal position in the document flow. Shifting them using top, right, bottom, or left does not affect the layout of other elements.

`Absolute:` Elements are removed from the normal document flow and positioned relative to their nearest positioned ancestor or the initial containing block. They don't affect the layout of other elements.

`Fixed:` Elements are removed from the normal document flow and positioned relative to the viewport. They remain fixed in their position even during page scrolling.
