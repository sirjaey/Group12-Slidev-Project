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



