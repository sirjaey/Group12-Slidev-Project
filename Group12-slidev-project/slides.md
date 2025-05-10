# <span style = "font-size: 36px">Functions in JavaScript</span>

<p style = "font-size: 16px">Functions are blocks of reusable code designed to perform a specific task</p>

```javascript
function sayHello() {
  console.log("Hello Everybody");
}
sayHello();
```
```text
output: Hello Everybody
```

---

# How to create a Function
<p>The three most common ways of creating functions are:</p> 
<ul>
<li>Function Declaration</li>
<li>Function Expression</li>
<li>Arrow Functions</li>
</ul>

<h2>Function Declaration</h2>
<p>
A Function declaration is a way to define a named function.
</p>

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
This is another way to create a function and unlike function declaration it can be anonymous
</p>

```javascript
let displayDetails = function (name, sex, age) {
  console.log(`${name} is ${sex} and is ${age} years old`)
}
displayDetails("John", "male", 25)
```
```text
Output: John is male and is 25 years old
```
<br>
<h2> Arrow Functions </h2>
<p>
Arrow functions provide a shorter way to write functions.
</p>

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

# Rest Parameters and Spread Syntax
The rest parameter allows you to represent an indefinite number of arguments as an array within a function and there can only be one rest parameter in a function's parameter list, and it must be the last parameter.

```javascript
function myFunc(a, b, ...restOfArgs) {
  console.log("First argument:", a);
  console.log("Second argument:", b);
  console.log("Rest of the arguments:", restOfArgs);
}
myFunc(1, 2, 3, 4, 5);// a = 1, b = 2, restOfArgs = 3,4,5
```
<br>
<h2>Spread Syntax</h2>
The spread syntax essentially unpacks an iterable (like a string or array).<br>
Spreads can be used to combine an array, clone an array and even spread a string into individual characters 

<div style = "display: grid; grid-template-columns: 1fr 1fr 1fr; gap: 20px;">

```javascript

//combine array
let num1 = [1,2,3]
let num2 = [4,5,6]
const join = [...num1, ...num2]
```
```javascript

//clone array
let first = [9,8,7]

let second = [...first]
```
```javascript
//spread a string into individual characters
let string = "hey"

alert([...string])
```
</div>
---

# Closure and Variable Scope

<p>A closure is the ability of a function to "remember" and access variables from its outer scope, even after that function has finished executing. There are primarily two types of scope we're concerned with in this context:</p>
<ul>
<li>Global Scope: Variables declared outside of any function have global scope. They can be accessed from anywhere in your code.</li>
<li>Local Scope: Variables declared inside a function have local scope, they are only accessible within that function and any functions nested inside it. Also variables declared in a block of code has local scope.</li>
</ul>

```javascript
let globalVariable = "Accessible anywhere in code"

let localFunction = function() {
  let localVariable= "accessible only inside the function"
}
console.log(localVariable) // Error, not defined

```


---

# Function Object
<p>Functions being an object have properties like name, length.</p>
Accessing the "name" property of functions

```javascript
  let alpha = function beta() {
    alert("hey")
  }
console.log(alpha.name) // Output: beta

let sayHi = () => {
  console.log("hi")}
alert(sayHi.name) // Output = "sayHi" which is the contextual name Js got from the variable name
```

Accessing the "length" Property

```javascript
function rest (n, ...arr) {}
console.log(rest.length) // output = 1 because rest parameters aren't counted

function defaultValue(m, n=2, o, p){}
console.log(defaultValue.length) // Output = 1 because only m is counted before the default value

function destructure ({m,n}, o) {}
console.log(destructure.length) // output = 2 because the destructuring pattern counts as 1 parameter
```

---

# Scheduling
<p>Scheduling in JavaScript refers to the execution of code at specific points in time or in response to certain events.</p>
SetTimeout Method

```javascript
// setTimeout(function, delay);
let timeoutId = setTimeout((name) => {
  console.log(`Hello, ${name}!`);
}, 3000, "Chinedu");// 3000 meaning 3 secs represents the delay so the function will run after 3 secomds

// if we want to cancel or stop the function from executing, we use clearTimeOut method
clearTimeout(timeoutId); // The function won't run
```

---

# Using "func.call"
<p>In JS, func.call is a built-in JavaScript method that allows you to invoke a function with a specific this value and individual arguments passed directly. It is similar to func.apply()</p>

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

// To get the property values of the object
alert(country.name)
alert(country.capital)

// We can also add boolean properties
country.hasStates = true
```

---

# Property names Limitations
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


