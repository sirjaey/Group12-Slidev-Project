---
transition: fade
class: lead
---

# Introduction to React.js

## Learning Journey: Past 2 Months

layout: center
class: heading

---

# Overview

- Introduction to React
- JSX (JavaScript XML)
- Components
- Example Codes

---

# What is React?

- **A JavaScript library** for building fast and interactive user interfaces.
- Created and maintained by **Facebook**.
- Focuses on building **reusable components**.

---

## layout: center

# React Logo

![React Logo](https://upload.wikimedia.org/wikipedia/commons/a/a7/React-icon.svg)

---

# What is JSX?

- JSX stands for **JavaScript XML**.
- It allows us to **write HTML** inside JavaScript.
- JSX makes writing React components **easier and more readable**.

---

# JSX Example

```jsx
const element = <h1>Hello, world!</h1>;

// Embedding JavaScript expressions
const name = "John";
const greeting = <h2>Hello, {name}!</h2>;
```

```jsx
// Applying inline CSS styling in JSX
const headingStyle = {
  color: "blue",
  textAlign: "center",
};

const styledHeading = <h1 style={headingStyle}>Styled Heading</h1>;
```

---

# JSX Example 2

-Use camelCase for CSS properties.

-Example: backgroundColor (✅) vs background-color (❌)

-The style attribute takes a JavaScript object.

-You can use external .css files too, but inline styles are handy for quick designs.

---

# React Components

Components are reusable building blocks in React.

They help organize the UI into small, manageable parts.

Two types:

Functional Components (modern)

Class Components (older)

---

# Components Functions

```jsx
// Basic Functional Component
function Welcome() {
  return <h1>Welcome to React!</h1>;
}
```

```jsx
// Component receiving props (dynamic data)
function GreetUser(props) {
  return <h2>Hello, {props.name}!</h2>;
}
```

```jsx
// Component with internal styling
function StyledMessage() {
  const messageStyle = { color: "green", fontSize: "20px" };
  return <p style={messageStyle}>This is a styled message!</p>;
}
```

---

# Combining Components

```jsx
function App() {
  return (
    <div>
      <Welcome />
      <GreetUser name="John" />
      <GreetUser name="Jane" />
      <StyledMessage />
    </div>
  );
}
```

---

# Combining Components

```jsx
function App() {
  return (
    <div>
      <Welcome />
      <GreetUser name="John" />
      <GreetUser name="Jane" />
      <StyledMessage />
    </div>
  );
}
```

# Welcome to DOM and EVENTS

---

# DOM

<div v-click>

Known as the **Document Object Model**. It is the interface that allows interaction with and manipulation of HTML and CSS using JavaScript. The DOM is the webpage described as an object. With the DOM, you are able to:

- Access and modify HTML elements
- Change styles and attributes
- Handle events
- Create, delete, or move elements
</div>

<div v-click>

### CSSOM

CSSOM stands for **CSS Object Model**. It allows JavaScript to read and modify styles via code.

</div>

<div v-click>

### BOM

Browser **Object Model** is the interface between JavaScript and the browser...

</div>

---

## ACCESSING DOM ELEMENTS

<div v-click>

### 🔹 By ID

The DOM can be accessed using element IDs.

```html
<!-- HTML -->
<div id="container">This is an example</div>

//Javascript const container = document.getElementById("container");
```

</div>
<div v-click>

### 🔹 By Class

The DOM can be accessed using class names.

```html
<!-- HTML -->
<span class="greet">Hey there!</span>

//Javascript const greet = document.getElementsByClassName("greet");
```

## </div>

### 🔹 By Tag name

<div v-click>
The DOM can be accessed by using the Tag name

```html
<!-- HTML -->
<p>I am a paragraph</p>

//Javascript const paragraphs = document.getElementsByTagName("p");
```

</div>
<div v-click>

### 🔹 By Using querySelector/querySelectorAll

This is the most recommended way of accessing the DOM

```html
<!-- HTML -->
<h2 class="month">January</h2>
<h2 class="month">February</h2>
<h2 class="month">March</h2>
<h2 class="month">April</h2>
<h2 class="month">May</h2>

//Javascript const firstMonth = document.querySelector(".month"); // Selects the
first
<h2>
  with class "month" const allMonths = document.querySelectorAll(".month"); //
  Selects all
  <h2>elements with class "month"</h2>
</h2>
```

## </div>

## CHANGING CONTENTS

<div v-click>

### 🔹 Change Text

Replace the text inside an element.

```html
<!-- HTML -->
<h2 class="month">January</h2>

//Javascript const firstMonth = document.querySelector(".month");
firstMonth.textContent = "New Month";
```

</div>

<div v-click>

### 🔹 Change HTML

Replace the inner HTML structure of an element.

```html
<!-- HTML -->
<span class="greet">Hey there!</span>

//Javascript const greet = document.querySelector(".greet"); greet.innerHTML = "
<div>Inner HTML was changed</div>
";
```

## </div>

### 🔹 Creating and Inserting Elements

<div v-click>

Create a new element and add it to the page

```html
//Javascript const newDiv = document.createElement("div"); // creates a div
element newDiv.textContent = "I was created!"; // adds text content
document.body.appendChild(newDiv); // appends to the body
```

</div>

<div v-click>

### 🔹 Removing Elements

Use .remove() to delete an element from the DOM.

```html
<!-- HTML -->
<p>I am a paragraph</p>

//Javascript const paragraphs = document.getElementsByTagName("p");
paragraphs[0].remove(); // removes the first paragraph
```

</div>

---

### 🔹 Changing styles

<div v-click>

Use .style to modify CSS properties directly from JavaScript.

```html
<!-- HTML -->
<div class="design">My design</div>
; //Javascript const design = document.querySelector(".design");
design.style.color = "blue"; design.style.fontSize = "24px";
```

</div>

<div v-click>

### 🔹 Changing Attributes

Use setAttribute to update attributes like src, alt, or href.

```html
<!-- HTML -->
<img id="profile" src="default.jpg" alt="profile photo" />

//Javascript const profileImg = document.getElementById("profile");
profileImg.setAttribute("src", "new-profile.jpg");
profileImg.setAttribute("alt", "Updated profile photo");
```

## </div>

### DOM Tree Example

<div v-click>

```html
<body>
  <div id="container">
    <h1>Hello</h1>
    <p>This is a paragraph.</p>
  </div>
</body>
```

JavaScript can navigate this like a tree:

```html
const container = document.getElementById("container");
console.log(container.children); // h1 and p
```

## </div>

# EVENTS

<div v-click>

Events are actions that occur in the browser (e.g., clicks, form submissions, key presses).  
JavaScript can respond to these actions using **event handlers**.

**Handlers** are functions that run in response to events.

</div>

<div v-click>

### 🔹 Common Event Types

- `click`: Triggered when an element is clicked
- `submit`: Triggered when a form is submitted
- `mouseover`: Triggered when the mouse hovers over an element
- `keydown`: Triggered when a key is pressed
- `input`: Triggered when the value of an input changes
- `change`: Triggered when the value of an input or select element is changed and loses focus

## </div>

## WAYS OF HANDLING EVENTS

In JavaScript, there are three primary ways to handle events. Below are the three main methods for handling events:

<div v-click>

### 🔹 HTML Attribute Method

In this method, the event handler is directly attached within the HTML element using an event attribute, such as `onclick`.

```html
<!--HTML-->
<button onclick="sayHello()">Click (HTML Attribute)</button>

<script>
  function sayHello() {
    alert("Hello from HTML attribute!");
  }
</script>
```

## </div>

### 🔹 DOM Property Method

<div v-click>

This method uses JavaScript to assign the event handler to the corresponding event property of an element (e.g., onclick).

```html
<!--HTML-->
<button id="btn2">Click (DOM Property)</button>

<script>
  const btn2 = document.getElementById("btn2");
  btn2.onclick = function () {
    alert("Hello from DOM property!");
  };
</script>
```

## </div>

### 🔹 addEventListener() Method

<div v-click>

This is the most flexible and recommended method for handling events. The addEventListener() method allows you to attach one or more event handlers to an element without overwriting existing ones.

```html
<!--HTML-->
<button class="btn3">Click (addEventListener)</button>

<script>
  const btn3 = document.querySelector(".btn3");

  function handleClick() {
    alert("I was clicked!!");
  }

  // You could also use an arrow function
  // const handleClick = () => alert("I was clicked!!");

  btn3.addEventListener("click", handleClick);
</script>
```

## </div>

## FORM EVENTS AND ADVANCED EVENT HANDLING

This section covers three important topics in event handling:

<div v-click>
1. Handling form submissions  
</div>

<div v-click>
2. Removing event listeners 
</div>

<div v-click> 
3. Event delegation (advanced pattern for dynamic content)
</div>

---

### 🔹 1. FORM SUBMIT EVENTS

<div v-click>

You can use JavaScript to handle form submissions and prevent the default behavior (such as page reload).

#### Example:

```html
<!--HTML-->
<form>
  <input
    type="text"
    placeholder="Enter username"
    id="username"
    name="username"
  />
  <button class="submit">Submit</button>
</form>

<script>
  const submit = document.querySelector(".submit");

  submit.addEventListener("click", function (e) {
    e.preventDefault(); // Prevents the form from actually submitting
    console.log("Form submitted!");
  });
</script>
```

## </div>

### 🔹 2. REMOVE EVENT LISTENER

<div v-click>

Sometimes, you may need to remove an event listener—for example, after an action has occurred or to optimize performance.

Example:

```html
<!-- HTML -->
<button class="submit">Submit</button>

<script>
  const submit = document.querySelector(".submit");

  function handleClick() {
    console.log("Clicked");
  }

  // Attach event
  submit.addEventListener("click", handleClick);

  // Remove event
  submit.removeEventListener("click", handleClick);
</script>
```

## </div>

### 🔹 3. EVENT DELEGATION

<div v-click>

Event delegation is a technique where a single event listener is attached to a parent element to manage events for its child elements. This is especially useful when elements are dynamically added.

Example:

```html
<!-- HTML -->
<ul id="list">
  <li>Item 1</li>
  <li>Item 2</li>
  <li>Item 3</li>
</ul>

<script>
  const allItems = document.getElementById("list"); // Select the parent <ul> element

  allItems.addEventListener("click", function (e) {
    // Listen for clicks on the <ul>
    if (e.target.tagName === "LI") {
      // Check if the clicked element is a <li>
      alert(`You clicked on ${e.target.textContent}`); // Show the clicked item's text
    }
  });
</script>
```

## </div>

## The Event Object

<div v-click>

Every event handler receives an event object that contains information about the event.

```html
<script>
  button.addEventListener("click", function (e) {
    console.log(e.target); // The element that triggered the event
    console.log(e.type); // The type of event (e.g., "click")
    e.preventDefault(); // Prevent default action if needed
  });
</script>
```

## </div>

## Event Propagation: Bubbling and Capturing

<div v-click>

Capturing: From the window down to the event target

Bubbling: From the event target up to the window (default phase)

```html
<!---HTML-->
<div id="outer">
  <button id="inner">Click Me</button>
</div>

<script>
  document.getElementById("outer").addEventListener("click", () => {
    console.log("Outer was clicked");
  });

  document.getElementById("inner").addEventListener("click", (e) => {
    console.log("Inner was clicked");
    e.stopPropagation(); // Stops bubbling to outer
  });
</script>
```

## </div>

Use e.stopPropagation() to stop the event from bubbling up.

To capture during the capturing phase, use:

```html
element.addEventListener("click", handler, { capture: true });
```

---

### Keyboard Events

<div v-click>

You can respond to user keyboard input using keydown, keyup, and keypress.

```html
document.addEventListener("keydown", function (e) { console.log("Key pressed:",
e.key); if (e.key === "Enter") { alert("Enter key was pressed!"); } });
```

</div>

<div v-click>

### Mouse Events

Beyond click, there are several mouse-related events:

- `dblclick`: Double-click

- `contextmenu`: Right-click (show context menu)

- `mousedown / mouseup`: Mouse button press/release

- `mouseenter / mouseleave`: When mouse enters or leaves an element

</div>

---

### Custom Events

<div v-click>

Create and dispatch your own events using CustomEvent.

```html
const greetEvent = new CustomEvent("greet", { detail: "Hello from custom event!"
}); element.addEventListener("greet", function (e) { console.log(e.detail); //
Access custom message }); element.dispatchEvent(greetEvent);
```

</div>

---

---

## layout: center

### Error Handling

<div v-click >

- try...catch
- e.message
- Error
- SyntaxError
- Custom error
</div>

---

Errors during program execution can happen for many reasons. The `try...catch` structure helps manage these errors without crashing the entire script. However, it only works with errors that happen at runtime.

This structure includes a `try` block, and optionally a `catch` block, a `finally` block, or both. Code inside the try block runs first. If an error occurs, the `catch` block is triggered. The `finally` block, if included, runs whether an error occurred or not

The syntax looks like this:

```js
function add(a, b) {
  return a + b;
}

try {
  add(3, 3); // This runs fine and doesn't throw an error
} catch (err) {
  // This block won't run because there's no error
  console.error(err);
} finally {
  // This always runs
  console.log("running the next code");
}
```

---

While the previous code uses error handling syntax, it doesn't actually trigger an error. So the `catch` block will never run in this specific case.

Instead, we'll use this code to catch an error instead

```js
function add(a, b) {
  if (typeof a !== "number" || typeof b !== "number") {
    throw new Error("Both arguments must be numbers");
  }
  return a + b;
}

try {
  add(3, "x"); // This will throw an error
} catch (err) {
  console.error("Caught an error:", err.message);
} finally {
  console.log("This always runs.");
}
```

---

### Custom Error

A custom error is an error you create yourself in code to handle specific situations that built-in errors don’t cover. Instead of just using general errors like `TypeError` or `SyntaxError,` you make your own named error to give a clearer message when something goes wrong.

Here's how to write it

```js
// Define a custom error
class AgeTooSmallError extends Error {
  constructor(message) {
    super(message);
    this.name = "AgeTooSmallError";
  }
}

// Using the function with error handling
try {
  checkAge(16); // This will throw the custom error
} catch (error) {
  if (error instanceof AgeTooSmallError) {
    console.log("Custom Error Caught:", error.message);
  } else {
    console.log("Some other error occurred.");
  }
}
```

---

---

## layout: center

### Promise and Async

<div v-click>fetch, async, await</div>

---

#### Promise

A Promise is a built-in JavaScript object that represents a value that may be available now, in the future, or never. It's used for handling asynchronous operations like loading data from a server.

Here is how to to write it:

<div v-click>

```js
let promise = new Promise((resolve, reject) => {
  // Simulate an asynchronous task, like a server request
  setTimeout(() => {
    let success = true; // Change to false to test reject
    if (success) {
      resolve("Task completed successfully!");
    } else {
      reject("Something went wrong.");
    }
  }, 1000);
});
// Using the promise
promise
  .then((result) => {
    console.log("Success:", result);
  })
  .catch((error) => {
    console.error("Error:", error);
  });
```

</div>

---

What’s happening:

- new Promise(...): Creates a new Promise object.
- resolve(...): Called when the task completes successfully.
- reject(...): Called when something goes wrong.
- .then(...): Runs if the promise is resolved.
- .catch(...): Runs if the promise is rejected.

---

### The fetch() API

<div v-click>

The `fetch()` API is a modern JavaScript method used to make HTTP requests, such as getting data from a server or an API. It is Promise-based, meaning it returns a Promise that resolves to a Response object.

</div>
<div v-click>

#### Key Features:

- Built into modern browsers (no need to install).
- Returns a Promise, which you can handle with `.then()` or `async/await.`
- Can make requests like `GET,` `POT,` `PUT,` `DELETE,` etc.
</div>

<div v-click>

#### How to write it with promise:

```js
fetch("https://official-joke-api.appspot.com/jokes/random")
  .then((response) => response.json()) // Convert response to JSON
  .then((data) => {
    console.log(`${data.setup} — ${data.punchline}`); // Display the joke
  })
  .catch((error) => {
    console.error("Error:", error); // Handle any errors
  });
```

</div>

---

<div v-click>

### Async and await

</div>

<div v-click>

Before `async` and `await`, we used Promises and `.then()` to handle asynchronous code. But `async/await` is a cleaner, more readable way to handle the same thing.

</div>

<div v-click>

#### The `async` Function

</div>

<div v-click>

The `async` function is a function that always returns a Promise. Even if you don't explicitly return a Promise, JavaScript wraps the result inside a Promise.

</div>

<div v-click>

#### for example:

</div>

<div v-click>

```js
async function sayHi() {
  return "Hi!";
}
sayHi().then(console.log); // Output: "Hi!"
```

Even though we just returned a string, `sayHi()` becomes a Promise because of the `async` keyword.

</div>

---

<div v-click>

### The `await` block

</div>

await pauses until a Promise finishes

```js
async function getJoke() {
  let response = await fetch(
    "https://official-joke-api.appspot.com/jokes/random"
  );
  let data = await response.json();
  console.log(data.setup, data.punchline);
}
```

- await fetch(...) waits until the fetch finishes
- await response.json() waits until the JSON is ready
- Then we log the joke

Without await, the function would run ahead without waiting.

---

<div v-click>

### Handling Errors with `try...catch`

</div>
<div v-click>

try...catch works just like with normal code, and it catches Promise rejections or network errors.

```js
async function getJoke() {
  try {
    let res = await fetch("https://api.badurl.com");
    let data = await res.json();
    console.log(data);
  } catch (error) {
    console.error("Oops! Something went wrong:", error);
  }
}
```

</div>

---

<div v-click>

### In Summary

| Concept       | Meaning                                   |
| ------------- | ----------------------------------------- |
| `async`       | Makes a function return a Promise         |
| `await`       | Pauses the code until the Promise is done |
| `try...catch` | Catches any errors in async code          |

</div>
