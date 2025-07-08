# Document Object Model (DOM)

A collection of JavaScript interview questions and answers focused on the DOM (Document Object Model).

---

### 1. What is the DOM?

**Answer:**
The Document Object Model (DOM) is a programming interface for web documents. It represents the page structure as a tree of objects that can be manipulated using JavaScript to dynamically change the content, structure, and style.

---

### 2. How do you select an HTML element using JavaScript?

**Answer:**
JavaScript provides several methods to select elements:

```js
document.getElementById("id");
document.querySelector(".class");
document.querySelectorAll("tag");
document.getElementsByClassName("className");
document.getElementsByTagName("tagName");
```

---

### 3. How can you change the style of an element using JavaScript?

**Answer:**
You can access and modify an element's `style` property.

```js
document.getElementById("box").style.backgroundColor = "blue";
document.querySelector("p").style.fontSize = "20px";
```

---

### 4. What are DOM events and how do you handle them?

**Answer:**
DOM events are actions that occur in the browser (like clicks, key presses, etc.). You handle them using `addEventListener()`.

```js
document.getElementById("btn").addEventListener("click", function () {
  alert("Button clicked!");
});
```

---

### 5. What is event bubbling and how does it work?

**Answer:**
Event bubbling is the process where an event starts from the target element and bubbles up to its ancestors. You can use event delegation to catch these events on a parent element.

```js
document.getElementById("list").addEventListener("click", function (event) {
  if (event.target.tagName === "LI") {
    console.log("Item clicked:", event.target.textContent);
  }
});
```

---

### 6. How do you remove an element from the DOM?

**Answer:**
You can use the `remove()` method on the element or `removeChild()` on its parent.

```js
document.getElementById("item").remove();

// or
let parent = document.getElementById("list");
let child = document.getElementById("item");
parent.removeChild(child);
```

---

### 7. What is the difference between `innerText`, `textContent`, and `innerHTML`?

**Answer:**

- `innerText`: returns the visible text, respects styles like `display: none`.
- `textContent`: returns all text within the node.
- `innerHTML`: returns the HTML content inside the element.

```js
element.innerText;
element.textContent;
element.innerHTML;
```

---

### 8. How do you create and insert a new element before another element?

**Answer:**
Use `insertBefore()` on the parent node.

```js
let newItem = document.createElement("li");
newItem.textContent = "New Item";
let list = document.getElementById("list");
let referenceItem = document.getElementById("item2");
list.insertBefore(newItem, referenceItem);
```

---

### 9. What is the difference between `append()` and `appendChild()`?

**Answer:**

- `appendChild()` only accepts a Node and returns it.
- `append()` can accept a Node or string and has no return value.

```js
let div = document.createElement("div");
div.appendChild(document.createTextNode("Hello"));
div.append(" World");
```

---

### 10. How can you detect when the DOM is fully loaded?

**Answer:**
Use the `DOMContentLoaded` event to run code after the DOM has fully loaded.

```js
document.addEventListener("DOMContentLoaded", function () {
  console.log("DOM fully loaded and parsed");
});
```

---

### 11. How can you clone a DOM element?

**Answer:**
You can use the `cloneNode()` method to duplicate a DOM element.

```js
let original = document.getElementById("item");
let clone = original.cloneNode(true); // true for deep clone
original.parentNode.appendChild(clone);
```

---

### 12. How do you get and set attributes in the DOM?

**Answer:**
Use `getAttribute()` to read and `setAttribute()` to modify attributes.

```js
let img = document.querySelector("img");
let src = img.getAttribute("src");
img.setAttribute("alt", "New description");
```

---

### 13. What is the difference between `node`, `element`, and `text` in the DOM?

**Answer:**

- `Node`: The most general type (includes elements, text, comments, etc.)
- `Element`: A specific kind of node representing an HTML element.
- `Text`: A node containing only text.

---

### 14. How do you prevent the default behavior of an event?

**Answer:**
Call `event.preventDefault()` inside the event handler.

```js
document.querySelector("form").addEventListener("submit", function (e) {
  e.preventDefault();
  console.log("Form submission blocked");
});
```

---

### 15. How can you check if an element contains a specific class?

**Answer:**
Use the `classList.contains()` method.

```js
let box = document.getElementById("box");
if (box.classList.contains("active")) {
  console.log("Box is active");
}
```

---

### 16. How do you toggle a class on an element?

**Answer:**
You can use the `classList.toggle()` method to add or remove a class.

```js
let element = document.getElementById("menu");
element.classList.toggle("open");
```

---

### 17. How can you find the parent node of an element?

**Answer:**
Use the `parentNode` or `parentElement` property.

```js
let child = document.getElementById("item");
let parent = child.parentNode;
```

---

### 18. What is the difference between `children` and `childNodes`?

**Answer:**

- `children`: Returns only element nodes.
- `childNodes`: Returns all node types, including text and comment nodes.

```js
let list = document.getElementById("list");
console.log(list.children); // HTMLCollection
console.log(list.childNodes); // NodeList
```

---

### 19. How do you find the value of an input element?

**Answer:**
Use the `.value` property to get or set the value of form inputs.

```js
let input = document.querySelector("input");
console.log(input.value);
```

---

### 20. How do you focus an input field with JavaScript?

**Answer:**
Use the `.focus()` method on the input element.

```js
document.getElementById("name").focus();
```

---
