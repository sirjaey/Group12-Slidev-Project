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



