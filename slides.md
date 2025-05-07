---
# You can also start simply with 'default'
theme: seriph
# random image from a curated Unsplash collection by Anthony
# like them? see https://unsplash.com/collections/94734566/slidev
background: https://cover.sli.dev
# some information about your slides (markdown enabled)
title: DOM and EVENTS
info: |
  ## Slidev Starter Template
  Presentation slides for developers.

  Learn more at [Sli.dev](https://sli.dev)
# apply unocss classes to the current slide
class: text-center
# https://sli.dev/features/drawing
drawings:
  persist: false
# slide transition: https://sli.dev/guide/animations.html#slide-transitions
transition: slide-left
# enable MDC Syntax: https://sli.dev/features/mdc
mdc: true
# open graph
# seoMeta:
#  ogImage: https://cover.sli.dev
---

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

//Javascript
const container = document.getElementById("container");
```
</div>
<div v-click>

### 🔹 By Class
The DOM can be accessed using class names.

```html
<!-- HTML -->
<span class="greet">Hey there!</span>

//Javascript
const greet = document.getElementsByClassName("greet");
```
</div>
---

### 🔹 By Tag name 
<div v-click>
The DOM can be accessed by using the Tag name

```html
<!-- HTML -->
<p>I am a paragraph</p>

//Javascript
const paragraphs = document.getElementsByTagName("p");
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

//Javascript
const firstMonth = document.querySelector(".month"); // Selects the first <h2> with class "month"
const allMonths = document.querySelectorAll(".month"); // Selects all <h2> elements with class "month"
```
</div>
---


## CHANGING CONTENTS
<div v-click>

### 🔹 Change Text
Replace the text inside an element.

```html
<!-- HTML -->
<h2 class="month">January</h2>

//Javascript
const firstMonth = document.querySelector(".month");
firstMonth.textContent = "New Month";
```
</div>

<div v-click>

### 🔹 Change HTML
Replace the inner HTML structure of an element.

```html
<!-- HTML -->
<span class="greet">Hey there!</span>

//Javascript
const greet = document.querySelector(".greet");
greet.innerHTML = "<div>Inner HTML was changed</div>";
```
</div>
---

### 🔹 Creating and Inserting Elements
<div v-click>

Create a new element and add it to the page

```html
//Javascript
const newDiv = document.createElement("div"); // creates a div element
newDiv.textContent = "I was created!"; // adds text content
document.body.appendChild(newDiv); // appends to the body
```
</div>

<div v-click>

### 🔹 Removing Elements
Use .remove() to delete an element from the DOM.

```html
<!-- HTML -->
<p>I am a paragraph</p>

//Javascript
const paragraphs = document.getElementsByTagName("p");
paragraphs[0].remove(); // removes the first paragraph
```
</div>

---

### 🔹 Changing styles
<div v-click>

Use .style to modify CSS properties directly from JavaScript.

```html
<!-- HTML -->
<div class="design">My design</div>;

//Javascript
const design = document.querySelector(".design");
design.style.color = "blue"; 
design.style.fontSize = "24px";
```
</div>

<div v-click>

### 🔹 Changing Attributes
Use setAttribute to update attributes like src, alt, or href.

```html
<!-- HTML -->
<img id="profile" src="default.jpg" alt="profile photo">

//Javascript
const profileImg = document.getElementById("profile");
profileImg.setAttribute("src", "new-profile.jpg");
profileImg.setAttribute("alt", "Updated profile photo");
```
</div>
---

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
</div>
---

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

</div>
---

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
</div>
---

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
</div>
---

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
</div>
---

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
  <input type="text" placeholder="Enter username" id="username" name="username" />
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
</div>
---

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
</div>
---

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

  allItems.addEventListener("click", function (e) { // Listen for clicks on the <ul>
    if (e.target.tagName === "LI") { // Check if the clicked element is a <li>
      alert(`You clicked on ${e.target.textContent}`); // Show the clicked item's text
    }
  });
</script>
```
</div>
---

## The Event Object
<div v-click>

Every event handler receives an event object that contains information about the event.
```html
<script>
  button.addEventListener("click", function (e) {
  console.log(e.target); // The element that triggered the event
  console.log(e.type);   // The type of event (e.g., "click")
  e.preventDefault();    // Prevent default action if needed
});
</script>
```
</div>
---

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
    console.log("Outer clicked");
  });

  document.getElementById("inner").addEventListener("click", (e) => {
    console.log("Inner clicked");
    e.stopPropagation(); // Stops bubbling to outer
  });
</script>
```
</div>
---

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
document.addEventListener("keydown", function (e) {
  console.log("Key pressed:", e.key);
  if (e.key === "Enter") {
    alert("Enter key was pressed!");
  }
});
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
const greetEvent = new CustomEvent("greet", {
  detail: "Hello from custom event!"
});

element.addEventListener("greet", function (e) {
  console.log(e.detail); // Access custom message
});

element.dispatchEvent(greetEvent);
```

</div>