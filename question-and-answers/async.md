# Asynchronous JavaScript

A collection of interview questions and answers focused on asynchronous behavior in JavaScript.

---

### 1. What is asynchronous JavaScript?

**Answer:**
Asynchronous JavaScript allows code to run without blocking the main thread. It enables functions to run in the background while the rest of the code continues to execute.

---

### 2. What are callbacks?

**Answer:**
A callback is a function passed into another function as an argument to be executed later, often after an asynchronous operation.

```js
function fetchData(callback) {
  setTimeout(() => {
    callback("Data loaded");
  }, 1000);
}

fetchData((data) => console.log(data));
```

---

### 3. What is a Promise in JavaScript?

**Answer:**
A Promise is an object that represents the eventual completion or failure of an asynchronous operation. It has three states: `pending`, `fulfilled`, and `rejected`.

```js
let promise = new Promise((resolve, reject) => {
  setTimeout(() => resolve("Success"), 1000);
});

promise.then((result) => console.log(result));
```

---

### 4. What is `async/await` in JavaScript?

**Answer:**
`async/await` is a syntax that allows you to write asynchronous code in a synchronous-looking manner. You use `await` inside an `async` function to wait for a Promise.

```js
async function loadData() {
  const response = await fetch("/api/data");
  const data = await response.json();
  console.log(data);
}
```

---

### 5. What is the difference between synchronous and asynchronous code?

**Answer:**
Synchronous code executes line by line, blocking the execution of the next line until the current one finishes. Asynchronous code allows the program to continue running while it waits for an operation to complete.

```js
// Synchronous
console.log("1");
console.log("2");

// Asynchronous
console.log("1");
setTimeout(() => console.log("2"), 1000);
console.log("3");
```

---

### 6. What does `.then()` do in a Promise?

**Answer:**
The `.then()` method is used to handle the result of a fulfilled Promise. It allows you to chain additional logic after the Promise resolves.

```js
fetch("/api/data")
  .then((response) => response.json())
  .then((data) => console.log(data));
```

---

### 7. What is `.catch()` used for in Promises?

**Answer:**
`.catch()` handles errors or rejections in a Promise chain. It provides a way to gracefully catch and deal with exceptions.

```js
fetch("/invalid-url")
  .then((res) => res.json())
  .catch((err) => console.error("Error:", err));
```

---

### 8. How does `finally()` work in Promises?

**Answer:**
The `finally()` method is executed after a Promise is settled, regardless of whether it was resolved or rejected. It's useful for cleanup operations.

```js
fetch("/api/data")
  .then((data) => console.log(data))
  .catch((err) => console.error(err))
  .finally(() => console.log("Request finished"));
```

---

### 9. How can you convert a callback-based function into a Promise-based one?

**Answer:**
You can wrap the callback function inside a Promise constructor.

```js
function getData(callback) {
  setTimeout(() => callback("done"), 1000);
}

function getDataPromise() {
  return new Promise((resolve) => {
    getData(resolve);
  });
}

getDataPromise().then((data) => console.log(data));
```

---

### 10. What are some common issues with callback-based asynchronous code?

**Answer:**

- Callback hell (deep nesting and hard-to-read code)
- Difficult error handling
- Reduced readability and maintainability

Using Promises and async/await helps address these issues by flattening the control flow and improving clarity.

---

### 11. What is `Promise.all()` and when would you use it?

**Answer:**
`Promise.all()` takes an array of Promises and returns a new Promise that resolves when all input Promises resolve, or rejects if any of them reject. It's useful when you need multiple asynchronous operations to complete before proceeding.

```js
Promise.all([fetch("/api/user"), fetch("/api/posts")])
  .then((responses) => Promise.all(responses.map((res) => res.json())))
  .then((data) => console.log(data));
```

---

### 12. What is `Promise.race()`?

**Answer:**
`Promise.race()` returns a Promise that settles as soon as any of the input Promises settle (resolve or reject). It’s useful when you want to act on the first completed Promise.

```js
Promise.race([fetch("/api/slow"), fetch("/api/fast")]).then((result) =>
  console.log("First to finish:", result)
);
```

---

### 13. How do you handle errors with `async/await`?

**Answer:**
You use `try...catch` blocks around `await` statements to catch errors from Promises.

```js
async function getData() {
  try {
    let response = await fetch("/api/data");
    let data = await response.json();
    console.log(data);
  } catch (error) {
    console.error("Error:", error);
  }
}
```

---

### 14. What is a microtask in JavaScript?

**Answer:**
A microtask is a task scheduled to run after the current execution context, but before the next rendering or macro task. Promises use the microtask queue to execute `.then()` callbacks.

```js
Promise.resolve().then(() => console.log("microtask"));
console.log("sync");
// Output: sync, microtask
```

---

### 15. What is a callback queue and how does it relate to the event loop?

**Answer:**
The callback queue stores messages (events) to be processed by the event loop. When the call stack is empty, the event loop pushes the first message from the queue to the stack for execution.

---

### 16. What is the difference between macro tasks and microtasks?

**Answer:**
Macro tasks include operations like `setTimeout`, `setInterval`, and I/O tasks, while microtasks include Promises and `queueMicrotask`. Microtasks are executed before any macro task in the event loop.

---

### 17. What is `Promise.allSettled()`?

**Answer:**
`Promise.allSettled()` returns a Promise that resolves after all of the input Promises have settled (either fulfilled or rejected), and provides an array of outcome objects.

```js
Promise.allSettled([Promise.resolve("A"), Promise.reject("B")]).then(
  (results) => console.log(results)
);
```

---

### 18. What is `Promise.any()`?

**Answer:**
`Promise.any()` returns a Promise that resolves as soon as one of the input Promises resolves. If all fail, it rejects with an `AggregateError`.

```js
Promise.any([
  Promise.reject("Error 1"),
  Promise.resolve("Success"),
  Promise.reject("Error 2"),
]).then((result) => console.log(result));
```

---

### 19. Can you use `await` outside of an `async` function?

**Answer:**
No, `await` can only be used inside `async` functions. Using it outside will result in a syntax error, unless supported in a top-level environment (e.g., top-level await in modern ES modules).

---

### 20. How can you cancel a fetch request in JavaScript?

**Answer:**
You can cancel a fetch request using an `AbortController`.

```js
const controller = new AbortController();
fetch("/api/data", { signal: controller.signal });
controller.abort(); // cancels the request
```

---
