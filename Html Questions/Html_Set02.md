## HTML Interview questions SET02

### 1. What is the difference between position absolute and relative.

`Relative Positioning` (position: relative;): When an element is set to `position: relative;`, it is positioned relative to its normal position in the document flow. It will be offset from its normal position based on the values of top, right, bottom, or left properties.

`Absolute Positioning` (position: absolute;): When an element is set to `position: absolute;`, it is removed from the normal document flow and positioned relative to its nearest positioned ancestor (an ancestor with a position value other than static) or the initial containing block (usually the <html> element).

### 2. In how many ways you can display HTML elements?

In HTML and CSS, there are several ways to control the display of elements on a webpage.

`block:` The element generates a block-level box. It starts on a new line and stretches the full width of its containing element. Examples: `<div>, <p>, <h1> to <h6>, <ul>, <ol>, <li>, <table>, <form>,` etc.

```
.block-element {
  display: block;
}
```

`inline:` The element generates an inline-level box. It does not start on a new line, and only takes up as much width as necessary. Examples: `<span>, <a>, <strong>, <em>, <img>, <br>,` etc.

```
.inline-element {
  display: inline;
}
```

`inline-block:` The element generates an inline-level box, but it behaves as a block-level box.
It does not start on a new line and takes up as much width as necessary, but you can apply width and height to it.

```
.inline-block-element {
  display: inline-block;
}
```

### 3. What is the difference between “display: none” and “visibility: hidden”, when used as attributes to the HTML element.

`display: none;`: Completely removes the element from the document flow. The element is not rendered, and its space is collapsed.

`visibility: hidden;`: Hidden but still occupies space. when you want to hide an element but still reserve its space, allowing it to remain interactable.

### 4. How to specify the link in HTML '<a>' tag and explain the target attribute? What do the different target statuses in <a> tag mean?

In HTML, the `<a>` (anchor) tag is used to create hyperlinks, allowing users to navigate to another web page

```
<a href="URL">Link Text</a>
```

the target attribute in the `<a>` tag. The target attribute specifies how the linked content should be displayed. It can take different values:

```
<a href="https://www.example.com" target="_self">Visit Example.com</a>

```

`_self:` Default behavior. The linked content is displayed in the same frame or window as the original page.

### 5. In how many ways can we specify the CSS styles for the HTML element?

There are several ways to specify CSS styles for HTML elements. The choice of method depends on factors such as the scope of styling, reusability.

`Inline Styles:`

```
<element style="property: value;">
```

`Description:`

```
<p style="color: red; font-size: 16px;">This is a red paragraph with a font size of 16px.</p>
```

`Internal Styles (Style Tag):`

```
<head>
  <style>
    selector {
      property: value;
    }
  </style>
</head>
```

`External Styles (Linking to a Stylesheet):`

```
<head>
  <link rel="stylesheet" type="text/css" href="styles.css">
</head>
```

`<link> Tag:` The `<link>` tag is used to link external resources, typically stylesheets, and icons, to an HTML document.

`<a> Tag:` The `<a>` tag, or anchor tag, is used to create hyperlinks, allowing users to navigate to another web page, a location within the same page, or external resources.

### 7. When to use scripts in the head and when to use scripts in the body?

` Scripts in the <head>:` Scripts that are essential for the structure or initial rendering of the webpage. Scripts that load external resources (e.g., stylesheets or libraries) needed for the page.

```
<head>
  <script src="https://example.com/library.js"></script>
  <script>
    // Your custom initialization script
    window.onload = function() {
      // Perform actions after the page has fully loaded
    };
  </script>
</head>
<body>
  <!-- Body content -->
</body>
```

`Scripts at the End of <body>:` Scripts that enhance user interactions, manipulate the DOM, or are not critical for the initial page load. Deferred scripts that do not block the rendering of the initial page content.

```
<head>
  <!-- Stylesheets and critical scripts -->
</head>
<body>
  <!-- Body content -->

  <script src="https://example.com/non-essential.js"></script>
  <script>
    // Your custom script for enhancing user interactions
  </script>
</body>
```

### 8. What are forms and how to create forms in HTML? What are the default behaviours of form that you know?

`Creating Forms in HTML:` To create a form in HTML, we use the `<form>` element. Within the `<form>` element, you can include various input elements, buttons, and other form-related elements. Here's a basic example:

```
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Sample Form</title>
</head>
<body>
  <form action="/submit" method="post">
    <!-- Form inputs go here -->
    <label for="username">Username:</label>
    <input type="text" id="username" name="username" required>

    <label for="password">Password:</label>
    <input type="password" id="password" name="password" required>

    <input type="submit" value="Submit">
  </form>
</body>
</html>
```

By default, when a user submits a form, the data is sent to the URL specified in the `action` attribute using the HTTP method specified in the `method` attribute.

### 9. How to handle events in HTML?

Handling events directly in the HTML markup using inline event attributes. This method is straightforward but can be less maintainable for complex applications.

```
<button onclick="handleButtonClick()">Click me</button>

<script>
  function handleButtonClick() {
    alert('Button clicked!');
  }
</script>
```

### 10. What are some of the advantages of HTML5 over its previous versions?

`New Semantic Elements:` HTML5 introduces new semantic elements like `<header>, <nav>, <footer>, <article>, <section>, and <aside>.` These elements provide clearer structure and meaning to web content

`Audio and Video Support:` HTML5 includes native support for embedding audio and video elements `(<audio> and <video>).` This eliminates the need for third-party plugins (like Flash) and simplifies the process of integrating multimedia content into web pages.

`Improved Form Controls:` HTML5 enhances form controls with new input types like email, url, tel, date, and more. Additionally, attributes such as `placeholder`, `required`, and `pattern` provide better control and validation of user input.

### 11. How can we include audio or video in a webpage?

To include audio or video in a webpage, you can use the `<audio> `and `<video>` elements, respectively. These elements allow you to embed multimedia content directly into your HTML document

`<audio> Element for Audio:`

```
<audio controls>
  <source src="audio.mp3" type="audio/mp3">
  Your browser does not support the audio tag.
</audio>
```

`<video> Element for Video:`

```
<video width="640" height="360" controls>
  <source src="video.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video>
```

### 12. What are Semantic Elements?Explain each one of them. WHere would you use them?

Semantic elements in HTML are tags that carry meaning about the structure and content of the webpage.

`<header>:` The `<header>` element represents the introductory content of a section or a page and typically contains headings, logos, navigation menus, and other header-related content.

`<nav>:` The `<nav>` element represents a navigation menu, allowing you to group together links that navigate the user within the current page or to other pages.

`<section>:` The `<section> `element represents a thematic grouping of content within the document.

`<footer>:` The `<footer>` element represents the footer of a section or a page. It typically contains metadata, copyright information, links to related documents, or contact details.

### 13. What are the significant goals of the HTML5 specification?

`Improved Support for Multimedia:` HTML5 introduces native support for embedding audio and video elements `(<audio> and <video>) `without the need for third-party plugins.

`Improved Forms and Input Controls:` HTML5 includes new input types (e.g., email, url, tel) and attributes (e.g., placeholder, required, pattern) to enhance form controls and improve user input validation.

`Canvas for Graphics and Animations:` The `<canvas>` element provides a drawing surface that can be used for rendering graphics, creating animations, and other dynamic content using JavaScript. This enhances the capabilities for creating interactive and visually appealing web applications.
