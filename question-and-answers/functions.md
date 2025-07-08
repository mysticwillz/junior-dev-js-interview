# JavaScript Functions

A collection of interview questions and answers about functions in JavaScript.

---

### 1. What is a function in JavaScript?

**Answer:**
A function is a block of reusable code that performs a specific task. Functions help keep code modular, organized, and reusable.

```js
function greet(name) {
  return `Hello, ${name}`;
}
```

---

### 2. What is the difference between function declarations and function expressions?

**Answer:**

- **Function Declaration** is hoisted, meaning it can be called before it's defined in the code.
- **Function Expression** is not hoisted and is assigned to a variable.

```js
// Declaration
function sayHi() {
  console.log("Hi");
}

// Expression
const sayHello = function () {
  console.log("Hello");
};
```

---

### 3. What are arrow functions?

**Answer:**
Arrow functions are a shorter syntax for writing function expressions. They do not have their own `this` or `arguments` binding.

```js
const add = (a, b) => a + b;
```

---

### 4. What is the `arguments` object in a function?

**Answer:**
The `arguments` object is an array-like object accessible inside regular functions that contains the arguments passed to the function.

```js
function logArgs() {
  console.log(arguments);
}
```

Note: Arrow functions do **not** have access to `arguments`.

---

### 5. What is a higher-order function?

**Answer:**
A higher-order function is a function that takes another function as an argument or returns a function.

```js
function repeat(fn, n) {
  for (let i = 0; i < n; i++) {
    fn();
  }
}

repeat(() => console.log("Hello"), 3);
```

---

### 6. What is the difference between `return` and `console.log()` in a function?

**Answer:**

- `return` sends a value back from a function to where it was called.
- `console.log()` prints a value to the browser's console for debugging purposes.

```js
function add(a, b) {
  return a + b; // use return to output result
}

function show(a, b) {
  console.log(a + b); // just logs result
}
```

---

### 7. What is the purpose of the `Function` constructor?

**Answer:**
The `Function` constructor creates a new function from a string. It’s rarely used and generally discouraged due to security and performance concerns.

```js
const sum = new Function("a", "b", "return a + b");
console.log(sum(2, 3)); // 5
```

---

### 8. What is the difference between `call`, `apply`, and `bind` again, but in terms of execution?

**Answer:**

- `call` and `apply` **immediately invoke** the function.
- `bind` **returns a new function** that can be called later.

```js
function greet() {
  console.log(this.name);
}

const user = { name: "Jane" };
greet.call(user); // Jane
greet.apply(user); // Jane
const bound = greet.bind(user);
bound(); // Jane
```

---

### 9. Can a function be both a constructor and a regular function?

**Answer:**
Yes. In JavaScript, any function can be used as a constructor with `new`, or called as a regular function.

```js
function Person(name) {
  this.name = name;
}

const person1 = new Person("Eze"); // Constructor usage
const person2 = Person("Tobi"); // Regular call — assigns to global `this`
```

---

### 10. What are arrow function limitations?

**Answer:**
Arrow functions:

- Don’t have their own `this`, `arguments`, or `super`
- Cannot be used as constructors (with `new`)
- Cannot use `yield`, so they can’t be generators

```js
const Arrow = () => {};
// new Arrow(); // TypeError
```

---

### 11. What is an IIFE (Immediately Invoked Function Expression)?

**Answer:**
An IIFE is a function that runs as soon as it is defined. It helps create a new scope to avoid polluting the global namespace.

```js
(function () {
  console.log("IIFE executed");
})();
```

---

### 12. What is function currying?

**Answer:**
Currying is the process of breaking down a function that takes multiple arguments into a series of functions that each take one argument.

```js
function multiply(a) {
  return function (b) {
    return a * b;
  };
}

const double = multiply(2);
console.log(double(5)); // 10
```

---

### 13. What is recursion in JavaScript?

**Answer:**
Recursion is when a function calls itself in order to solve a problem by breaking it down into smaller sub-problems.

```js
function factorial(n) {
  if (n === 0) return 1;
  return n * factorial(n - 1);
}
```

---

### 14. What is the rest parameter in JavaScript?

**Answer:**
The rest parameter allows a function to accept an indefinite number of arguments as an array.

```js
function sum(...numbers) {
  return numbers.reduce((acc, curr) => acc + curr, 0);
}

console.log(sum(1, 2, 3)); // 6
```

---

### 15. What is the difference between parameters and arguments?

**Answer:**

- **Parameters** are the names listed in the function definition.
- **Arguments** are the actual values passed to the function when it is called.

```js
function greet(name) {
  // name is a parameter
  console.log(`Hello, ${name}`);
}

greet("Alice"); // "Alice" is the argument
```

---

### 16. What is the difference between synchronous and asynchronous functions?

**Answer:**
Synchronous functions block execution until they finish. Asynchronous functions (like those using `async/await`) allow other code to run while waiting for a task to complete.

---

### 17. What is a named function expression?

**Answer:**
A named function expression assigns a function with a name to a variable. The name is only accessible within the function’s own scope.

```js
const factorial = function fact(n) {
  if (n <= 1) return 1;
  return n * fact(n - 1);
};
```

---

### 18. How do arrow functions handle the `this` keyword?

**Answer:**
Arrow functions do not have their own `this`. They inherit `this` from the surrounding lexical context.

```js
const obj = {
  value: 42,
  method: function () {
    const arrow = () => console.log(this.value);
    arrow();
  },
};

obj.method(); // 42
```

---

### 19. What is a generator function?

**Answer:**
A generator function is defined with an asterisk (`function*`) and can pause execution using `yield`. It returns an iterator.

```js
function* count() {
  yield 1;
  yield 2;
  yield 3;
}

const iterator = count();
console.log(iterator.next()); // { value: 1, done: false }
```

---

### 20. What are default parameters in functions?

**Answer:**
Default parameters allow you to set default values for function parameters.

```js
function greet(name = "Guest") {
  console.log(`Hello, ${name}`);
}

greet(); // Hello, Guest
```

---
