# JavaScript Basics

A collection of basic JavaScript interview questions and answers.

---

### 1. What is JavaScript and what is it used for?

**Answer:**
JavaScript is a high-level, interpreted programming language used to make web pages interactive. It runs in the browser and allows you to build dynamic features like image sliders, form validation, interactive maps, and more.

---

### 2. What are the different data types in JavaScript?

**Answer:**
JavaScript has the following data types:

* **Primitive Types:** `string`, `number`, `boolean`, `null`, `undefined`, `bigint`, `symbol`
* **Reference Types:** `object` (includes arrays, functions, etc.)

---

### 3. What is the difference between `let`, `const`, and `var`?

**Answer:**

* `var`: Function-scoped and can be re-declared.
* `let`: Block-scoped and can be reassigned, but not re-declared in the same scope.
* `const`: Block-scoped and **cannot** be reassigned.

```js
let name = "Eze Williams";
const age = 25;
var job = "developer";
```

---

### 4. How do you write a function in JavaScript?

**Answer:**
You can define a function using the `function` keyword or with arrow function syntax.

```js
// Function declaration
function greet(name) {
  return `Hello, ${name}`;
}

// Arrow function
const greet = (name) => `Hello, ${name}`;
```

---

### 5. What is the difference between `==` and `===`?

**Answer:**

* `==` compares values after type conversion (loose equality).
* `===` compares both value and type (strict equality).

```js
'5' == 5    // true
'5' === 5   // false
```

---

### 6. What is a callback function?

**Answer:**
A callback is a function passed as an argument to another function to be executed later.

```js
function fetchData(callback) {
  setTimeout(() => {
    callback("Data loaded");
  }, 1000);
}

fetchData((data) => console.log(data)); // Logs "Data loaded" after 1 second
```

---

### 7. What is hoisting in JavaScript?

**Answer:**
Hoisting is JavaScript's default behavior of moving declarations (not initializations) to the top of their scope.

```js
console.log(a); // undefined
var a = 5;
```

Only `var` declarations (and functions) are hoisted. `let` and `const` are not hoisted the same way.

---

### 8. What is the difference between `null` and `undefined`?

**Answer:**

* `undefined`: A variable is declared but not assigned.
* `null`: A variable is intentionally set to have no value.

```js
let x;
console.log(x); // undefined

let y = null;
console.log(y); // null
```

---

### 9. What is the use of `typeof` operator in JavaScript?

**Answer:**
The `typeof` operator is used to find the data type of a variable.

```js
typeof "Hello"; // "string"
typeof 42;      // "number"
typeof true;    // "boolean"
```

---

### 10. What is the difference between `function declaration` and `function expression`?

**Answer:**

* Function declarations are hoisted, so they can be used before they are defined.
* Function expressions are not hoisted.

```js
// Declaration
function sayHi() {
  return "Hi!";
}

// Expression
const sayHello = function () {
  return "Hello!";
};
```

---

### 11. How do you comment code in JavaScript?

**Answer:**
You can use `//` for single-line comments and `/* */` for multi-line comments.

```js
// This is a single-line comment

/*
 This is a
 multi-line comment
*/
```

---

### 12. What is the purpose of `return` in a function?

**Answer:**
The `return` statement ends function execution and specifies a value to be returned to the function caller.

```js
function add(a, b) {
  return a + b;
}

console.log(add(2, 3)); // 5
```

---

### 13. What are truthy and falsy values in JavaScript?

**Answer:**
Truthy values evaluate to `true` in a boolean context. Falsy values evaluate to `false`.

**Falsy values:** `false`, `0`, `''`, `null`, `undefined`, `NaN`

```js
if (0) console.log("No"); // Won't run
if (1) console.log("Yes"); // Will run
```

---

### 14. What is the difference between `let` and `var` in terms of scope?

**Answer:**
`let` is block-scoped, which means it is only accessible within the block it is defined. `var` is function-scoped, which means it is accessible within the entire function it is defined in.

```js
{
  let a = 10;
  var b = 20;
}

console.log(a); // ReferenceError
console.log(b); // 20
```

---

### 15. What is an array in JavaScript?

**Answer:**
An array is a special type of object used to store multiple values in a single variable.

```js
let fruits = ["apple", "banana", "mango"];
console.log(fruits[1]); // "banana"
```

---

### 16. How can you check if a value is an array?

**Answer:**
Use `Array.isArray()` method to check if a value is an array.

```js
Array.isArray([1, 2, 3]); // true
Array.isArray("hello");  // false
```

---

### 17. How do you loop through an array in JavaScript?

**Answer:**
You can use a `for` loop, `forEach`, or `for...of` loop.

```js
let colors = ["red", "green", "blue"];

// for loop
for (let i = 0; i < colors.length; i++) {
  console.log(colors[i]);
}

// forEach
colors.forEach(color => console.log(color));

// for...of
for (let color of colors) {
  console.log(color);
}
```

---

### 18. What is a template literal in JavaScript?

**Answer:**
Template literals allow embedded expressions and multi-line strings using backticks (`` ` ``).

```js
let name = "Eze";
let greeting = `Hello, ${name}!`;
console.log(greeting); // Hello, Eze!
```

---

### 19. What is a JavaScript object?

**Answer:**
An object is a collection of key-value pairs used to store structured data.

```js
let person = {
  name: "Eze",
  age: 25,
  job: "developer"
};
console.log(person.name); // "Eze"
```

---

### 20. How do you add a property to an object?

**Answer:**
You can add a property using dot notation or bracket notation.

```js
let car = {};
car.brand = "Toyota";
car["model"] = "Corolla";
```

---

### 21. What is the difference between `for...in` and `for...of` loops?

**Answer:**

* `for...in` loops over **keys** in an object.
* `for...of` loops over **values** in an iterable (like an array).

```js
let arr = ["a", "b", "c"];

for (let index in arr) {
  console.log(index); // 0, 1, 2
}

for (let value of arr) {
  console.log(value); // "a", "b", "c"
}
```

---

### 22. What is a function parameter vs argument?

**Answer:**

* A **parameter** is a named variable in the function definition.
* An **argument** is the actual value passed to the function.

```js
function greet(name) { // name is a parameter
  console.log("Hello, " + name);
}

greet("Eze"); // "Eze" is the argument
```

---

### 23. What is the difference between `push()` and `pop()`?

**Answer:**

* `push()` adds an item to the end of an array.
* `pop()` removes the last item from an array.

```js
let nums = [1, 2];
nums.push(3); // [1, 2, 3]
nums.pop();   // [1, 2]
```

---

### 24. What does `NaN` mean in JavaScript?

**Answer:**
`NaN` stands for "Not-a-Number". It represents a value that is not a valid number.

```js
let x = "abc" / 2;
console.log(x); // NaN
```

---

### 25. How do you convert a string to a number in JavaScript?

**Answer:**
You can use `Number()`, `parseInt()`, or the unary `+` operator.

```js
Number("42");    // 42
parseInt("42");  // 42
+"42";           // 42
```

---

### 26. What does `typeof null` return?

**Answer:**
It returns `'object'`. This is a long-standing bug in JavaScript.

```js
typeof null; // "object"
```

---

### 27. What are arrow functions?

**Answer:**
Arrow functions are a shorter syntax for writing functions. They also do **not** bind their own `this`.

```js
const add = (a, b) => a + b;
```

---

### 28. What is the `this` keyword in JavaScript?

**Answer:**
`this` refers to the object that is executing the current function. In global scope, it refers to the global object.

```js
const user = {
  name: "Eze",
  greet() {
    console.log("Hello, " + this.name);
  }
};
user.greet(); // Hello, Eze
```

---

### 29. How do you handle errors in JavaScript?

**Answer:**
You use `try...catch` blocks to catch and handle errors.

```js
try {
  // code that might throw
  let result = riskyFunction();
} catch (error) {
  console.error("Error occurred:", error);
}
```

---

### 30. What is an Immediately Invoked Function Expression (IIFE)?

**Answer:**
An IIFE is a function that runs as soon as it is defined.

```js
(function() {
  console.log("IIFE executed");
})();
```

---
