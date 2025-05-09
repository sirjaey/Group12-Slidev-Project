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

---


# <span style = "font-size: 36px">Functions in JavaScript</span>

<p style = "font-size: 16px">Functions in JavaScript are blocks of reusable code designed to perform a specific task, there are one of the fundamental building blocks in Javascript. Functions can be seen as mini-programs within a larger program, you define a set of instructions inside a function, and then you can execute those instructions whenever you need to by "calling" the function.<br>
Some Examples of tasks that can be solved with functions</p>
```javascript
function sayHello() {
  console.log("Hello Everybody");
}
sayHello();
```
```text
output: Hello Everybody
```
```javascript
function getSum(){
        let numbers = [1, 2, 3, 4, 5];
        let sum = numbers.reduce((acc, num) => acc + num, 0);   
        console.log(sum); }
    
    getSum()
```
```text
Output: 15
```

---

# How to create a Function
<p>The three most common ways of creating functions are:</p> 
<ul>
<li>Function Declaration</li>
<li>Function Expression</li>
<li>Arrow Functions</li>
</ul>

---

# Function Declaration 
<p>
A Function declaration is a way to define a named function. It introduces a new function starting by writing the "Function" Keyword then its name with parameters (inputs) and then you finally write the block of code which is the function body (which is enclosed with curly braces {}) that will be executed when the function is called . As seen earlier, not all functions are given parameters.
</p>
```javascript
function //You start by writing the function keyword
name //Then you write the function name
(input1, input2, input3) //then you write the parameters in brackets. These are the values that you will pass to the function when you call it.
{
  //Then inside the curly braces, you write the body of code
}
// then you call the function name along with the inputs
```
<br>
```javascript
function displayDetails (name, sex, age) {    
        console.log(`${name} is ${sex} and is ${age} years old`)
}
displayDetails("John", "male", 25)
```
```text
Output: John is male and is 25 years old
```

---

# Function Expression

<p>
This is another way to create a function. Unlike a function declaration, a function expression does not necessarily have a name i.e it can be anonymous or named(The name can be used inside the function body for recursion or reference, while the function is called using variable name.). A function expression can only be called after it's definition unlike function declaration
</p>

```javascript
let name = function(input1, input2, input3){
  //body of the function
}
//Then you call the function after it's definition
```
<br>

```javascript
let displayDetails = function (name, sex, age) {
  console.log(`${name} is ${sex} and is ${age} years old`)
}
displayDetails("John", "male", 25)

//or you can name the function
let details = function displayDetails (name, sex, age) {
  console.log(`${name} is ${sex} and is ${age} years old`)
}
details("John", "male", 25)
```
```text
Output: John is male and is 25 years old
```

---

# Arrow Functions
<p>
Arrow functions provide a shorter way to write functions. Introduced in ECMAScript 2015 (ES6), arrow functions provide a more concise syntax for writing function expressions.
</p>
```javascript
let name = (input1, input2, input3) => {
  // body of the function
}
// call the function 
```
<br>
```javascript
  let displayDetails = () => {
   console.log(`${name} is ${sex} and is ${age} years old`)
}
details("John", "male", 25)
```
```text
Output = John is male and is 25 years old
```

---

# Recursion and Stack
<p>
Recursion is a programming technique where a function calls itself within its own definition to solve a problem by breaking it down into smaller, simpler and similar subproblems until you reach a simple case (the base case) that can be solved directly. The solutions to these subproblems are then combined to solve the original problem. A recursive function can receive two inputs: a base case (ends recursion) or a recursive case (resumes recursion).
</p>

```javascript
function fibonacci(n) {
  if (n <= 0) {
    return 0; // Base case for n = 0 and negative numbers
  } else if (n == 1) {
    return 1; // Base case for n = 1
  } else {//Fib(n) = Fib(n-1) + Fib(n-2) for n > 1 (Recursive step)
    return fibonacci(n - 1) + fibonacci(n - 2);
  }
}
console.log(fibonacci(0));  // Output: 0
console.log(fibonacci(1));  // Output: 1
console.log(fibonacci(2));  // Output: 1 (1 + 0)
console.log(fibonacci(3));  // Output: 2 (1 + 1)
console.log(fibonacci(4));  // Output: 3 (2 + 1)
console.log(fibonacci(6));  // Output: 8 (5 + 3)
```

---

# contd
<p>
When the recursive function above is called, the execution is split into two branches:<br>
<ul>
<li>Base Case: This recursive function has two base cases, if n <= 0 the function retrns 0 meaning numbers from 0 downward will return 0 and if n == 1 the functon returns 1 and these are the stopping conditions for the recursion so if n = 0 or -1, it returns 0 and if n = 1 it returns 1 </li>

#

<li>Recursive Case: if n > 1, the function returns fibonacci(n - 1) + fibonacci(n - 2)</li>
</ul> 
</p>
<br>
<h1>Why we use recursive functions</h1>
<p>
Recursive functions are employed when a problem can be naturally broken down into smaller, self-similar subproblems, leading to better performance, efficiency and readable code.
</p>

---

# Rest Parameters and Spread Syntax
The rest parameter allows you to represent an indefinite number of arguments as an array within a function and there can only be one rest parameter in a function's parameter list, and it must be the last parameter.

```javascript
function myFunc(a, b, ...restOfArgs) {
  console.log("First argument:", a);
  console.log("Second argument:", b);
  console.log("Rest of the arguments:", restOfArgs);
}
myFunc(1, 2, 3, 4, 5);
```

---

# Spread Syntax
The spread syntax allows an iterable (like an array or a string) to be expanded in places where zero or more arguments (for function calls) or elements (for arrays and objects) are expected. It essentially unpcks an iterable.<br>
Spreads can be used to combine an array, clone an array and even spread a string into individual characters  

```javascript
//combine array
let num1 = [1,2,3]
let num2 = [4,5,6]
const join = [...num1, ...num2] //output (1,2,3,4,5,6)

//clone array
let first = [9,8,7]
let second = [...first]

//spread a string into individual characters
let string = "hey"
alert([...string])
```

---

# Closure and Variable Scope

<p>A closure is the ability of a function to "remember" and access variables from its outer scope, even after that function has finished executing.<br>In JavaScript, scope determines the accessibility (visibility) of variables. There are primarily two types of scope we're concerned with in this context:</p>
<ul>
<li>Global Scope: Variables declared outside of any function have global scope. They can be accessed from anywhere in your code.</li>
<li>Local Scope: Variables declared inside a function have local scope, they are only accessible within that function and any functions nested inside it. Also variables declared in a block of code has local scope.</li>
</ul>

```javascript
let globalVariable = "Accessible anywhere in code"

let localFunction = function() {
  let localVariable= "accessible only inside the function"
  console.log(globalVariable)
  console.log(localVariable)}
localFunction();
//Output: 
//Accessible anywhere in code
//accessible only inside the function
alert(global) // output = Accessible anywhere in code
alert(local) // Output = Error (because local doesn't have global scope)
```


---

# Function Object
<p>In JavaScript, functions being objects is a key reason why they are considered first-class citizens meaning they are values. Like every other object functions can be assigned to variables, passed as argument to other functions, be returned from other functions and can also be stored in data structures. Functions also have properties like name, length, custom.</p>
Accessing the "name" property of functions

```javascript
// Function declaration
  function age(){
    console.log(30)}
  alert(age.name) // Output = age

// Function expression
  let alpha = function beta() {
    alert("hey")
  }
console.log(alpha.name) // Output: beta

/*For functions declared annoymously like the last example, JS engine can still assign a name
 (contextual name in this case "sayHi") based on context in which they are defined (assigned to a variable)*/
//An annoymous function assigned to a variable
let sayHi = () => {
  console.log("hi")}
alert(sayHi.name) // Output = "sayHi" which is the contextual name Js got from the variable name
``` 

---

# Accessing the "length" Property
<p>The length property of a function object returns the number of formal parameters declared in the function definition. Rest parameters are excluded, A destructuring pattern (e.g {a,b}) counts as asingle parameter and only parameters before the first one with default calues are counted</p>

```javascript
function rest (n, ...arr) {
  //Body of function
}
console.log(rest.length) // output = 1 brcause only n is counted

function defaultValue(m, n=2, o, p){
  //Body of function
}
console.log(defaultValue.length) // Output = 1 because only m is counted before the default value

function destructure ({m,n}, o) {
  // Body of Function
}
console.log(destructure.length) // output = 2 because the destructuring pattern counts as 1 parameter
```

---

# Accessing the "Custom Property"
Functions being objects means custom properties can be added to them allowing us to attach additional data which is done using either the dot notation or bracket notation

```javascript
function greet(name) {
  console.log(`Hello, ${name}!`);
}

greet.description = "This is a custom property telling us that the function greets a person by name.";
greet.version = "1.0";

console.log(greet.description); // Output: This is a custom property telling us that the function greets a person by name.

greet("Chioma"); // The function still works as expected when you call it
```

---

# new Function
<p>
 The new Function() constructor is another way to dynamically create functions in JavaScript. It is commonly used due to security risks and performance implication. The primary use is when you need to create functions dynamically at runtime based on strings received from user input, a configuration file, or some other external source and unlike other functions that have access to the local variable, functions created with the new Function() syntax only has access to variables in the global scope.
</p>

```javascript
const addTwo = new Function('a', 'b', 'return a + b;');
console.log(addTwo(10, 20)); //output: 30

```

<p>With the new Function() constructor in JavaScript
the earlier string arguments provided are treated as the names of the parameters for the function you are creating and the very last string argument provided is treated as the body of the function, containing the JavaScript code that will be executed when the function is called. This body typically uses the parameter names defined in the preceding arguments to perform its task and potentially return a result.</p>


---

# Scheduling
<p>Scheduling in JavaScript refers to the execution of code at specific points in time or in response to certain events. It involves using built-in mechanisms to delay the execution of functions (setTimeout), repeatedly execute functions at intervals (setInterval), synchronize animations with the browser's rendering cycle (requestAnimationFrame).</p>
SetTimeout Method

```javascript
// setTimeout(function, delay);
let timeoutId = setTimeout((name) => {
  console.log(`Hello, ${name}!`);
}, 3000, "Chinedu");// 3000 meaning 3 secs represents the delay so the function will run after 3 secomds

// if we want to cancel or stop the function from executing, we use clearTimeOut method
clearTimeout(timeoutId); // The function won't run
```
Zero delay setTimeout
<p>This schedules the function to be executed as soon as possible after the current JavaScript task has been completed and is written as setTimeout(function, 0).</p>

```javascript
setTimeout(() => {
  console.log("joseph")}, 0)
console.log("hey"); // output = "hey joseph" as "hey" will come first before "joseph"
```

---

# SetInterval Method
<p>This function repeatedly schedules the execution of a callback function at a fixed delay interval (in milliseconds).</p>

```javascript
//setInterval(function, interval);
let intervals = setInterval(() => {
  console.log("This will run every 1 second.");
}, 1000);

// using clearInterval(intervals) we can stop the setInterval 
setTimeout(() => clearInterval(intervals), 5000);// Output = This will stop the interval after 5 secs
```

---

# requestAnimationFrame(callback)
<p>This function is specifically designed and optimized for smooth animations that go beyond CSS. It schedules the callback function to run before the next time the browser visually updates the screen.
The browser will try to execute the callback at a rate that matches the display's refresh rate</p>

```javascript
//Example
function animate(timestamp) {
  // Perform animation tasks here based on the timestamp
  console.log("Animating...", timestamp);
  requestAnimationFrame(animate); // Schedule the next frame
}
requestAnimationFrame(animate);


//To cancel the animation we can use
cancelAnimationFrame(animateId)
```

---

# Decorators and Forwarding, call/apply, bind
<p>Function decorators in JavaScript, implemented using Higher-Order Functions (a function that takes another function as input), enhance the behavior of other functions by wrapping them with additional logic like logging or memoization (used to speed up the execution of functions by caching the results of function calls and returning the cached result when the same inputs occur again), promoting reusability and separation of concerns; function forwarding involves one function calling another, potentially modifying arguments or processing results, enabling code reuse, extensibility (allows for the addition of new capabilities without requiring much changes to its existing structure), and the composition of more complex operations from simpler ones.</p>

Transparent caching
<p>When dealing with functions that produce the same output for identical inputs and are expected to be called often, storing their results in a cache can lead to substantial time savings by eliminating the need for repeated computations</p>

---

#

```javascript
function memoize(func) {
  const cache = {}; // create an empty object to store the results
  return function(...args) {
    if (cache[args]) // if this is truthy meaning if results exist for the inputed args
    {
      console.log(`returning stored results`);
      return cache[args];
    }

    const result = func(...args);
    cache[args] = result;
    console.log(`No record for ${func.name} with args:`, args, "storing:", result);
    return result;
  };
}
function expensiveOperation(n) {
  return n * n;
}

const memoizedExpensive = memoize(expensiveOperation);
console.log(memoizedExpensive(5)); // output = No record for expensiveOperation with args: [5] storing: 25
console.log(memoizedExpensive(5)); // output = returning stored results 25
console.log(memoizedExpensive(10)); // output = No record for expensiveOperation with args: [10] storing: 100
```

---

# Using "func.call" for the context
<p>In JS, func.call is a built-in JavaScript method that allows you to invoke a function with a specific this value and individual arguments passed directly.</p>

```javascript
const person = {
  name: "Chinedu",
  greet: function(greeting) {
    console.log(`${greeting}, my name is ${this.name}.`);
  }
};

const anotherPerson = {
  name: "Ifeoma"
};

person.greet.call(anotherPerson, "Hello"); // 'this' inside greet will refer to anotherPerson
// Output: Hello, my name is Ifeoma.
```

---

#
<p>The object "person" has two properties which is the name with value chinedu and the fuction "greet".
The func takes one argument (greeting) and uses console.log to print a message that includes the greeting and the name property of the object it's currently associated with (using this.name).
Another object "anotherPerson" also has a name property, but its value is "Ifeoma". Importantly, anotherPerson does not have a greet function of its own.

person.greet.call(anotherPerson, "Hello"), this is the key line where call() is used. We are calling the call() method on the greet function.
anotherPerson is the first argument passed to call(). It specifies the value that the "this" keyword will refer to inside the greet function when it is executed. In this case, we are telling JavaScript that when greet runs, this should point to the anotherPerson object.
"Hello" is the second argument passed to call(). It represents the first argument that will be passed to the greet function itself responding to the greeting parameter
</p>

---

# func.apply
<p>func.apply(thisArg, [argsArray]) is another built-in JavaScript method that allows you to invoke a function with a specific this value, similar to func.call(). However, the key difference lies in how you pass the arguments to the function. apply() expects the arguments to be provided as a single array (or an array-like object).</p>

```javascript
// Just like func.call, func.apply allows you to control the this context of a setting
const person = {
  name: "Ngozi",
  greet: function(greeting) {
    console.log(`${greeting}, my name is ${this.name}.`);
  }
};

const anotherPerson = {
  name: "Emeka"
};

person.greet.apply(anotherPerson, ["Good morning"]);
// Output: Good morning, my name is Emeka.
```

---

# Objects in Javascript
<p>An object is a collection of key-value pairs, where each key (a string or Symbol) uniquely identifies a value (any JavaScript data type). Objects are fundamental for organizing and structuring data, representing entities, and building complex data structures in JavaScript. <br>
Object properties can be accessed using dot or square bracket notation.
</p>
An object can be created using the following Syntaxes:

```javascript
//object literal
let person = {}

//object constructor
let person = new Object()

//Above are two empty objects
```

---

# Object Properties
An example of an object with properties

```javascript
let country = {
  //key   value
  name: "Nigeria",
  capital: "Abuja"
}

// We can use multiple words as names of properties and to do so we need to wrap in quotes
 country = {
  name: "Nigeria",
  capital: "Abuja",
  'reject immigrants': false
}

// To get the property values of the object
alert(country.name)
alert(country.capital)

// We can also add boolean properties
country.hasStates = true

// We can delete a property using delete operator
delete country.capital
```

---

# Square Brackets

Names of objects that have special characters or multispaced can't use the dot notation as it doesn't work on those properties. That is where the Square bracket notation comes in.

```javascript
let country = {
  name: "Nigeria",
  capital: "Abuja",
}

// you can also add to objects using square brackets
country["flag colour"] = "Green-White-Green";

//you can access property names dynamically
let country = {
  name: "Nigeria",
  capital: "Abuja",
}
let key = prompt("What do you want to know about the country?", "name");
alert([country[key]]); // output = Nigeria
// A property name for an object can be gotten from an expression put in square bracket
let state = "largest city" ;
let country = {
  name: "Nigeria",
  capital: "Abuja",
  [state]: "Lagos",}
console.log(country[state]) // Output = lagos

```

---

# Property value shorthand
When we use existing values for property name, we can use the shorthand property 

```javascript
const getCountry = (name, capital) => {
  return {
    name,
    capital
  }
}

let country = getCountry("Nigeria", "Abuja");
alert(country.name)
alert(country.capital)
```
Property names Limitations <br>
An object property has no limitations on names to be used as property names like how variables have limitation on for, let, const etc

```javascript
let noRestrict = {
  return: 5,
  let: 8,
  for: 2,
  const: 3,
}
console.log(noRestrict)

```

---

# Property existence test, "in" operator

<p>To find out if a property exist in in an object and if it doesn't exist, it will return undefined instead of an error</p>

```javascript
let country = {name: "Nigeria", capital: "Abuja"}
alert( country.noSuchProperty === undefined );

// We can also make use of a Special operator "in"
let country = {name: "Nigeria", capital: "Abuja"}
alert( "name" in country );
alert( "state" in country ); 
```
When using the "in" keyword, the property name must be on the left andin a quoted string

---

# For...in Loop
<p>We can use the for...in loop to iterate over all enumerable string properties of an object. <br>
How the for...in loop is written</p>

```javascript
for (let key in objects) {
  // executes the body for each key among object properties
}

```
Using the for...in loop to loop over all the country properties

```javascript
let country = {
  name: "Nigeria",
  capital: "Abuja",
  state: "Lagos"}

for (let key in country) {
  console.log(key)
  //output: name, capital, state
}
```

---

# Refrencing and copying

<p>With strings and numbers in JavaScript, assigning one variable to another creates a completely independent duplicate of the value. However, when you assign an object to a new variable, you're not making a copy of the object itself. Instead, both variables become different ways of accessing the same object in the computer's memory. Modifying it through one variable will be reflected when you access it through the other.</p>
Comparison By refrence

```javascript
// if two objects can access the same object i.e if the refrence the same object they are said to be equal
let country1 = {}
let country2 = country1;
alert(country1 == country2); //Output = true
alert(country1 === country2); // Output = true

// if the two objects refrence different object they are said to not be equal even if their contents are identical 

let country1 = {}
let country2 = {};
alert(country1 == country2); //Output = false

```

---

# Cloning and merging
<p>One way of duplicating an object is to copy over the properties from the original object into a manually created object. This process creates a shallow copy by iterating over each property and copying them individually</p>

```javascript
let country = {
  name: "Nigeria",
  capital: "Abuja",
  state: "Lagos"
  }
  // Create an empty object
  let copyCountry = {}

  // iterate over the properties
  for (let key in country) {
    copyCountry[key] = country[key]
  }
  copyCountry.name = "Ghana"
  console.log(country.name); //Nigeria
```

---

# Object.assign
<p>
The Object.assign(target, ...sources) is a built-in JavaScript method that's used to copy the values of all enumerable properties from one or more source objects to a target object. It will return the modified target object.
</p>

```javascript
const obj1 = { a: 1 };
const obj2 = { b: 2 };
const obj3 = { c: 3 };

const merged = Object.assign({}, obj1, obj2, obj3);
console.log(merged); // Output: { a: 1, b: 2, c: 3 }
```

---

# Deep Cloning
<p>To extract and duplicate a property from a nested object within a larger object, a cloning loop can be used. This enables targeted access and replication of the desired value without altering the surrounding structure.</p>

```javascript
let country = {
  name: "Nigeria",
  capital: "Abuja",
  state: "Lagos"
  }

  let clone = Object.assign({}, country);
  alert(country.capital === clone.capital) /// Output = true
```

---

# StructuredClone()
<p>"The structuredClone() function in JavaScript performs a deep copy of an object, ensuring that all nested objects are also duplicated. Consequently, the original object and its clone become entirely independent entities in memory."</p>

```javascript
const originalLeader = {
  name: "Obi",
  age: 45,
  address: {
    street: "Awka Road",
    city: "Onitsha"
  }
};

const clonedLeader = structuredClone(originalLeader);

// Modify the clone
clonedLeader.name = "Ngozi";
clonedLeader.address.city = "Asaba";

console.log("Original Leader:", originalLeader);
// Output: Original Leader: { name: 'Obi', age: 45, address: { street: 'Awka Road', city: 'Onitsha' } }

console.log("Cloned Leader:", clonedLeader);
// Output: Cloned Leader: { name: 'Ngozi', age: 45, address: { street: 'Awka Road', city: 'Asaba' } }
```