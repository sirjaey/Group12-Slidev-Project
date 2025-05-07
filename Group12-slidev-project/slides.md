---
transition: fade
class: lead
---

# Introduction to React.js
Learning Journey: Past 2 Months
---
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
layout: center
---

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
  textAlign: "center"
};

const styledHeading = <h1 style={headingStyle}>Styled Heading</h1>

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


# JavaScript Fundamentals
Learning Journey: Past 2 Months
---
layout: center
class: heading
---
# Overview

- Data Types
- Operationals
- Conditionals
- Interaction
- Loops

---

# Data Types

 **What are Data Types:**
 Data types represent the different kinds of values you can work with in JavaScript. They tell the interpreter what kind of data is being stored or manipulated.

**Primary data types in JavaScript**
- String: Used to represent text enclosed in quotes.
- Number: This is used for both integers and decimals.
- Boolean: true or false.
- Null: Represents an Empty or unknown value.
- Undefined: A declared variable with no value.
- Object:A collection of key-value pairs.
- Array: A list of values.


---
layout: center
---

# Data Types Examples
```js
let name = "Ugomma";        // String
let age = 25;               // Number
let isStudent = true;       // Boolean
let empty = null;           // Null
let notSet;                 // Undefined
let person = {name: "Ama", age: 22}; // Object
let colors = ["red", "blue"];        // Array
```

---

# Operators

**What are Operators**
  Operators are symbols used to perform operations on values and variables, like arithmetic, comparison, and logical evaluations.

**Types of Operators**
- **Arithmetic Operators**:Used for mathematical operations (+, -, *, /, %).
- **Assignment Operators**:Used to assign values (=, +=, -=).
- **Comparison Operators**:Used to compare values (==, ===, !=, <, >).
- **Logical Operators**:Used to combine boolean expressions ( &&, ||, !).

---

# How to use operators

```js
//Arithmetic operators
let a = 10, b = 3;
a + b // 13
a - b // 7
a * b // 30
a / b // 3.33
a % b // 1 (remainder)
```


```js 
// Assignment Operators
 let x = 5; //basic assignment
 x += 2; //x = x + 2
 a -= 3; //a = a - 3
```

---


```js
//Comparison Operators
a == "10";   // true (equality)
a === "10";  // false (strict equality)
a != b;      // true
a > b;       // true
a < b;       // true
a >= b;      // true
a <= b;      // true

```


```js 
// Logical Operators
 true && false // false
true || false // true
!true         // false
```

---

# Conditionals
**What are conditionals**
Conditionals are used to execute different blocks of code based on certain conditions. This allows your program to make decisions.

**Types of conditionals**
- if else
- else if
- Ternary Operator(shorthand if..else)
---

**Types of conditionals**

**if...else**
```js
let score = 80;
if (score >= 70) {
  console.log("You passed!");
} else {
  console.log("Try again.");
}
```

**else if**
```js
let score = 80;
if (score >= 70) {
  console.log("You passed!");
} else {
  console.log("Try again.");
}
```

**Ternary Operator(shorthand if..else)**
```js
let result = score >= 70 ? "Passed" : "Failed";
console.log(result);
````
---

# Interaction

**What is interaction in Js?**
Interaction allows JavaScript to communicate with the user or developer through pop-ups or the console.

**Types of Interactions**

- alert(): Displays a simple message.
```js
alert("Welcome to my website!");
```

- console.log(): Outputs information to the browser's developer console.
```js
console.log("This is group 12's presentation");
```

- prompt(): Asks the user for input and returns it as a string.
```js
let name = prompt("What is your name?");
console.log("Hello, " + name);
```
---

# Loops
**What are Loops**
Loops are used to run the same block of code repeatedly, as long as a condition is true. They're useful for tasks like iterating through arrays or repeating actions.

**Types of Loops in JS**
- For Loop: This works best when you know how many times to loop.
```js
for (let i = 1; i <= 3; i++) {
  console.log("Count: " + i);
}
```
- While Loop:This is used when the number of iterations is unknown, but depends on a condition.
```js
let i = 1;
while (i <= 3) {
  console.log("While Count: " + i);
  i++;
}
```
- Do...While Loop: This is similar to while loop, but runs atleast once even if the condition is false.
```js
let j = 1;
do {
  console.log("Do Count: " + j);
  j++;
} while (j <= 3);
```

# Overview

- Basics

- Custom Elements

- Shadow DOM

---

# Basics

Web Components represent a significant leap forward in web development, offering
developers the ability to create reusable, encapsulated components that work
seamlessly across different frameworks and libraries. This introduction will
help you understand what Web Components are, why they matter, and how they can
transform your approach to building web applications.

# What are web components?

At their core, Web Components are a set of standardized web platform APIs that
allow you to create new, custom, reusable HTML elements. Imagine being able to
create your own custom-datepicker or advanced-carousel that works just like
native HTML elements such as select or video. That’s exactly what Web Components
enable!

# Why Web Components Matters

- Reusability: Can be reused or shared across different projects.
- Framework Independence: Works in any JavaScript framework.
- Encapsulation: Components are self-contained, hence improving security.

---

# What are The Three Pillars of Web Components?

1. Custom Elements
   - Define new HTML tags
   - Create custom elements behaviour
   - Extend existing HTML elements
2. Shadow DOM
   - Encapsulate styles and markup
   - Create a seperate DOM tree
   - Isolate components internals
3. HTML Templates
   - Define resuable markup
   - Create insert HTML fragments
   - Stamp out components instances

---

# Custom Elements

## What are custom elements?

Custom Elements allow us to create our own HTML tags with custom functionality,
making our code more semantic and reusable.

---

## Creating Custom Elements

<div class="overflow-y-auto" style="max-height: 600px;">


  ``` javascript {1|2|3|4-6|all}
  class MyElement extends HTMLElement {
      constructor() {
          super();
          // Initialize your element
      }
      // Lifecycle Methods
      connectedCallback() {
          // Element added to DOM
      }
      disconnectedCallback() {
          // Element removed from DOM
      }
      attributeChangedCallback(name, oldValue, newValue) {
          // Attribute changed
      }
      static get observedAttributes() {
          return ['my-attribute'];
      }
  }
  // Register the element
  customElements.define('my-element', MyElement);
  ```
</div>
---


# Shadow DOM

Shadow DOM is a web standard that provides encapsulation for HTML, CSS, and JavaScript. Think of it as creating a "private" DOM tree inside your element that’s isolated from the main document.

``` javascript
customElements.define(
  'custom-card',
  class extends HTMLElement {
    constructor() {
      super()
      const shadow = this.attachShadow({ mode: 'open' })
      shadow.innerHTML = `
      <style>
        .card {
          padding: 20px;
          border: 1px solid #ccc;
          border-radius: 4px;
        }
      </style>
      <div class="card">
        <slot></slot>
      </div>
    `
    }
  },
)
```
---
layout: center
---

# Modules and Dynamic Imports

---
layout: center
---

# Modules
- Module basics
- Export and Import
- Dynamic Imports
---

# What is a module?
A module is just a file. Modules can load each other and use special directives export and import to share functionality. Modularity is a key aspect of large-scale software development. It is the process of breaking a program into separate, interchangeable components that can be used in different parts of the program.

```html
<script src="" type="module"> </script>
```

Export keyword labels variables and functions that should be accessible from outside the current module then import allows the usage in other modules. Modules have come to JavaScript relatively recently. Before, there were no modules in JavaScript, and every script included in the HTML had access to all other scripts. Which could be a problem for global variables and functions and the order is important. So, modules are a way to solve these problems.

For instance, if we have a file menu.js exporting a function:
<div class="grid grid-cols-3 gap-5 pt-4 -mb-6">
```javascript
// 📁 menu.js
export function menu(user) {
  alert(`Hello, ${user}!`)
}
```
```javascript
// 📁 menu.js
export function menu(user) {
  alert(`Hello, ${user}!`)
}
export {menu}
```
```javascript
// 📁 script.js - named import
// because of a valid named export
import { menu } from './menu.js'
```
</div>
---

# What is Importing?
- Importing is the method by which you make exported code available in another JavaScript file. This is essential for assembling various components and libraries to build complex applications.
- Import * as "var name": This syntax allows you to import all exported code from a module and assign it to a single object. This is useful when you want to import multiple modules into a single file.
- Usually, we put a list of what to import in curly braces import.
- But if there’s a lot to import, we can import everything as an object using import * as "var name", for instance:
  
<div class="grid grid-cols-2 gap-5 pt-4 -mb-6">

```javascript
// 📁 script.js
import { name as name, age as age } from './bio.js'
function(name){
  console.log(`My name is ${name}, I am ${age} years old`);
}
```
```javascript
// 📁 script.js
import * as bio from './bio.js'

bio.name // SirJaey
bio.track // Frontend Engineering
```
</div>
---

# Dynamic Imports
- Dynamic imports revolutionize how modules are handled, offering a more flexible approach compared to static imports. Static imports require all modules to be loaded at the beginning of a script, increasing initial load times and potentially impacting performance. In contrast, dynamic imports load modules on demand, which can significantly reduce initial load times and enhance user experience.

<div class="grid grid-cols-2 gap-5 pt-4 -mb-6">

```javascript
// Static import (traditional method)
import { module } from './path/to/module.js'
```
```javascript
// Dynamic import
const module = await import('./path/to/module.js')
```
</div>
- 


- Explanation: The above example contrasts the traditional static import with a dynamic import. Notice that dynamic imports use a promise-based syntax, which means they can be used within asynchronous functions or handled with .then() and .catch() for greater control over timing and error handling.
- Dynamic imports are particularly beneficial in scenarios where parts of your application are conditionally used or not immediately necessary.
---

