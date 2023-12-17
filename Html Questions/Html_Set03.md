## HTML Interview questions SET03

### 1. Explain the concept of web storage in HTML5. What are the different types of storage and when to use what?

Web storage in HTML5 refers to the ability of web applications to store data locally on a user's device. This storage mechanism allows developers to store key-value pairs persistently or session-specifically.

`Local Storage:` Data stored using local storage persists across browser sessions and even when the user closes and reopens the browser. Suitable for storing data that needs to be retained between visits or sessions, such as user preferences, settings, or cached data.

`when to use?`: When you need to store data persistently across multiple sessions & For long-term storage of user preferences, settings, or cached data.

`Session Storage:` Data stored using session storage is only available for the duration of a single browser session. Ideal for storing temporary data that is only needed for the current session, such as form data or state information.

`when to use?`: When you need to store data for the duration of a single browser session & For temporary storage of data that is only relevant during the current session.

### 2. What is new about the relationship between the `<header>` and `<h1>` tags in HTML5?

In HTML5, the relationship between the `<header> `and `<h1>` tags has evolved to provide a more semantically meaningful and flexible structure for web documents. The `<header>` element represents introductory content or a group of navigation links, and the `<h1>` element represents the main heading or topic of the content within a section or article.

### 3. What are the New tags in Media Elements in HTML5?

`<audio>:` The `<audio>` element is used to embed audio content on a webpage.

`<video>:` The `<video>` element is used to embed video content on a webpage.

`<source>:` The `<source>` element is used within `<audio>` and `<video>` elements to specify alternative media files and their types.

### 4. Why do you think the addition of drag-and-drop functionality in HTML5 is important? How will you make an image draggable in HTML5?

se it enhances user interaction and provides a more intuitive and dynamic user experience. It allows users to easily manipulate and organize content by dragging items from one location to another.

`Making an Image Draggable in HTML5:`

```
<!DOCTYPE html>

<-- Html body and other code-->

    function drop(event) {
      event.preventDefault();
      var data = event.dataTransfer.getData("text/plain");
      var draggedElement = document.getElementById(data);

      // Get the mouse coordinates when the drop occurs
      var offsetX = event.clientX - draggedElement.width / 2;
      var offsetY = event.clientY - draggedElement.height / 2;

      // Position the dragged element at the drop location
      draggedElement.style.position = "absolute";
      draggedElement.style.left = offsetX + "px";
      draggedElement.style.top = offsetY + "px";
    }
  </script>

</body>
</html>
```

### 5. What are Web Workers?

Web Workers are a feature in web development that enable the execution of JavaScript code in the background, separate from the main execution thread of a web page. The main purpose of Web Workers is to perform parallel processing, allowing certain tasks to run concurrently without affecting the responsiveness of the user interface.

### 7. What is a manifest file in HTML5?

In HTML5, a manifest file refers to the Web App Manifest. The Web App Manifest is a JSON (JavaScript Object Notation) file that provides metadata about a web application. This metadata includes information about the application's name, icons, theme colors, display modes, and other properties.

### 8. Explain The Key Differences Between LocalStorage And SessionStorage Objects.

`localStorage:` The data stored in `localStorage` persists beyond the current session and remains available even when the browser is closed and reopened. It has a broader scope and is accessible across multiple tabs or windows of the same browser as long as they are part of the same origin (same protocol, domain, and port).

`sessionStorage:` The data stored in `sessionStorage` is session-specific and is limited to the duration of the page session. It is accessible only within the same tab or window where it was set and is cleared when the tab or window is closed.

### 9. When should we use cookies?

Session Management, User Authentication, Personalization, Shopping Carts in E-commerce, Tracking and Analytics, Cross-Site Communication

### 10. What is specificity in css? Important Interview question.

In CSS, specificity is a set of rules that determines which style rules are applied to an element. It is a way of resolving conflicts when multiple CSS rules target the same element and try to apply conflicting styles.

### 11. How many types of CSS can be included in HTML?

In HTML, there are three main ways to include CSS namely Inline CSS, Internal or Embedded CSS, External CSS.

### 12. Explain the layout of HTML? Where does the header go, where does nav go , where does footer go etc.

`<head>:` The `<head>` section contains meta-information about the HTML document, such as the title, character set, linked stylesheets, scripts, and other metadata.

Navigation Section `(<nav>)`: The `<nav>` element is used to define a navigation menu. It often contains a list of links to different sections of the website.

Footer Section `(<footer>)`: The `<footer>` element is used to define the footer section of a page. It often contains copyright information, links to privacy policies, terms of service, and other footer-related content.
