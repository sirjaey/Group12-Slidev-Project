# Welcome to DOM and EVENTS

---

# DOM

Known as the **Document Object Model**. It is the interface that allows interaction with and manipulation of HTML and CSS using JavaScript. The DOM is the webpage described as an object. With the DOM, you are able to:

- Access and modify HTML elements
- Change styles and attributes
- Handle events
- Create, delete, or move elements

---

## ACCESSING DOM ELEMENTS

### 🔹 By ID

The DOM can be accessed using element IDs.

```html
<div id="container">This is an example</div>

const container = document.getElementById("container");
```

### 🔹 By Class

The DOM can be accessed using class names.

```html
<span class="greet">Hey there!</span>

const greet = document.getElementsByClassName("greet");
```

---

### 🔹 By Tag name

The DOM can be accessed by using the Tag name

```html
<p>I am a paragraph</p>

const paragraphs = document.getElementsByTagName("p");
```

### 🔹 By Using querySelector/querySelectorAll

This is the most recommended way of accessing the DOM

```html
<h2 class="month">January</h2>
<h2 class="month">February</h2>
<h2 class="month">March</h2>
<h2 class="month">April</h2>
<h2 class="month">May</h2>

<script>
  const firstMonth = document.querySelector(".month");
  const allMonths = document.querySelectorAll(".month");
</script>
```

---

## CHANGING CONTENTS

### 🔹 Change Text

Replace the text inside an element.

```html
<h2 class="month">January</h2>

<script>
  const firstMonth = document.querySelector(".month");
  firstMonth.textContent = "New Month";
</script>
```

### 🔹 Change HTML

Replace the inner HTML structure of an element.

```html
<span class="greet">Hey there!</span>

<script>
  const greet = document.querySelector(".greet");
  greet.innerHTML = "<div>Inner HTML was changed</div>";
</script>
```

---

### 🔹 Creating and Inserting Elements

Create a new element and add it to the page

```html
<script>
  const newDiv = document.createElement("div"); // creates a div element
  newDiv.textContent = "I was created!"; // adds text content
  document.body.appendChild(newDiv); // appends to the body
</script>
```

### 🔹 Removing Elements

Use .remove() to delete an element from the DOM.

```html
<p>I am a paragraph</p>

<script>
  const paragraphs = document.getElementsByTagName("p");
  paragraphs[0].remove(); // removes the first paragraph
</script>
```

---

### 🔹 Changing styles

Use .style to modify CSS properties directly from JavaScript.

```html
<div class="design">My design</div>

<script>
  const design = document.querySelector(".design");
  design.style.color = "blue";
  design.style.fontSize = "24px";
</script>
```

### 🔹 Changing Attributes

Use setAttribute to update attributes like src, alt, or href.

```html
<img id="profile" src="default.jpg" alt="profile photo" />

<script>
  const profileImg = document.getElementById("profile");
  profileImg.setAttribute("src", "new-profile.jpg");
  profileImg.setAttribute("alt", "Updated profile photo");
</script>
```

---

# EVENTS

Events are actions that occur in the browser (e.g., clicks, form submissions, key presses).  
JavaScript can respond to these actions using **event handlers**.

**Handlers** are functions that run in response to events.

### 🔹 Common Event Types

- `click`: Triggered when an element is clicked
- `submit`: Triggered when a form is submitted
- `mouseover`: Triggered when the mouse hovers over an element
- `keydown`: Triggered when a key is pressed
- `input`: Triggered when the value of an input changes
- `change`: Triggered when the value of an input or select element is changed and loses focus

---

## WAYS OF HANDLING EVENTS

In JavaScript, there are three primary ways to handle events. Below are the three main methods for handling events:

### 🔹 HTML Attribute Method

In this method, the event handler is directly attached within the HTML element using an event attribute, such as `onclick`.

```html
<button onclick="sayHello()">Click (HTML Attribute)</button>

<script>
  function sayHello() {
    alert("Hello from HTML attribute!");
  }
</script>
```

---

### 🔹 DOM Property Method

This method uses JavaScript to assign the event handler to the corresponding event property of an element (e.g., onclick).

```html
<button id="btn2">Click (DOM Property)</button>

<script>
  const btn2 = document.getElementById("btn2");
  btn2.onclick = function () {
    alert("Hello from DOM property!");
  };
</script>
```

---

### 🔹 addEventListener() Method

This is the most flexible and recommended method for handling events. The addEventListener() method allows you to attach one or more event handlers to an element without overwriting existing ones.

```html
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

---

## FORM EVENTS AND ADVANCED EVENT HANDLING

This section covers three important topics in event handling:

1. Handling form submissions

2. Removing event listeners

3. Event delegation (advanced pattern for dynamic content)

---

### 🔹 1. FORM SUBMIT EVENTS

You can use JavaScript to handle form submissions and prevent the default behavior (such as page reload).

#### Example:

```html
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

---

### 🔹 2. REMOVE EVENT LISTENER

Sometimes, you may need to remove an event listener—for example, after an action has occurred or to optimize performance.

Example:

```html
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

---

### 🔹 3. EVENT DELEGATION

Event delegation is a technique where a single event listener is attached to a parent element to manage events for its child elements. This is especially useful when elements are dynamically added.

Example:

```html
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

---

## Event Propagation: Bubbling and Capturing

Capturing: From the window down to the event target

Bubbling: From the event target up to the window (default phase)

```html
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
