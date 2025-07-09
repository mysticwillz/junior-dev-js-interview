# JavaScript: Objects and Arrays

A collection of interview questions and answers focused on JavaScript objects and arrays.

---

### 1. What is the difference between an object and an array in JavaScript?

**Answer:**

- **Objects** store key-value pairs and are ideal for representing structured data.
- **Arrays** store ordered collections of values and are ideal for lists.

```js
const obj = { name: "Eze", age: 25 };
const arr = ["Eze", 25];
```

---

### 2. How do you loop through the properties of an object?

**Answer:**
You can use `for...in` or `Object.keys()`, `Object.values()`, or `Object.entries()` with `forEach()`.

```js
const user = { name: "Alice", age: 30 };

for (let key in user) {
  console.log(key, user[key]);
}

Object.entries(user).forEach(([key, value]) => {
  console.log(key, value);
});
```

---

### 3. What are some common array methods?

**Answer:**
Common array methods include:

- `push`, `pop` – Add/remove from end
- `shift`, `unshift` – Add/remove from beginning
- `map`, `filter`, `reduce` – Transform or process arrays
- `find`, `includes`, `indexOf` – Search

```js
const nums = [1, 2, 3];
const doubled = nums.map((n) => n * 2); // [2, 4, 6]
```

---

### 4. How do you clone an object or array?

**Answer:**

- Use the spread operator: `{ ...obj }`, `[...arr]`
- Use `Object.assign()` for objects
- Use `slice()` or `Array.from()` for arrays

```js
const obj = { name: "Eze" };
const clone = { ...obj };

const arr = [1, 2, 3];
const arrClone = [...arr];
```

---

### 5. What is destructuring in JavaScript?

**Answer:**
Destructuring lets you extract values from objects or arrays into variables.

```js
const person = { name: "Tobi", age: 22 };
const { name, age } = person;

const coords = [10, 20];
const [x, y] = coords;
```

---

### 6. How do you merge two objects or arrays?

**Answer:**

- For objects: Use the spread operator or `Object.assign()`.
- For arrays: Use the spread operator or `concat()`.

```js
const obj1 = { a: 1 };
const obj2 = { b: 2 };
const mergedObj = { ...obj1, ...obj2 };

const arr1 = [1, 2];
const arr2 = [3, 4];
const mergedArr = [...arr1, ...arr2];
```

---

### 7. What is the difference between `null` and `undefined` in object properties?

**Answer:**

- `undefined`: The property does not exist or hasn't been assigned a value.
- `null`: The property exists but was intentionally set to no value.

```js
const obj = { a: null, b: undefined };
```

---

### 8. How do you check if a key exists in an object?

**Answer:**
You can use:

- The `in` operator
- `hasOwnProperty()`
- `Object.keys(obj).includes("key")`

```js
"name" in obj;
obj.hasOwnProperty("name");
```

---

### 9. What is the difference between `map()` and `forEach()`?

**Answer:**

- `map()` returns a new array and is used for transformation.
- `forEach()` performs a function on each item but does not return a new array.

```js
const nums = [1, 2, 3];
const doubled = nums.map((n) => n * 2); // returns [2, 4, 6]
nums.forEach((n) => console.log(n)); // logs 1, 2, 3
```

---

### 10. How do you remove a property from an object?

**Answer:**
Use the `delete` operator.

```js
const user = { name: "Eze", age: 25 };
delete user.age;
console.log(user); // { name: "Eze" }
```

---

### 11. How do you convert an object into an array?

**Answer:**
You can use `Object.keys()`, `Object.values()`, or `Object.entries()` to convert an object into an array of keys, values, or key-value pairs.

```js
const obj = { a: 1, b: 2 };
const keys = Object.keys(obj); // ["a", "b"]
const values = Object.values(obj); // [1, 2]
const entries = Object.entries(obj); // [["a", 1], ["b", 2]]
```

---

### 12. How do you find the length of an object?

**Answer:**
Use `Object.keys(obj).length` to count the number of properties.

```js
const obj = { a: 1, b: 2 };
console.log(Object.keys(obj).length); // 2
```

---

### 13. What is a sparse array?

**Answer:**
A sparse array has empty or unassigned indices. It can affect iteration and length calculations.

```js
const arr = [1, , 3]; // Missing index 1
console.log(arr.length); // 3
```

---

### 14. What is the difference between `Array.isArray()` and `typeof`?

**Answer:**

- `typeof` an array returns `'object'`
- `Array.isArray()` correctly detects if a value is an array

```js
const arr = [1, 2, 3];
console.log(typeof arr); // 'object'
console.log(Array.isArray(arr)); // true
```

---

### 15. How do you remove duplicates from an array?

**Answer:**
Use a `Set` or `filter()` with `indexOf()`.

```js
const nums = [1, 2, 2, 3];
const unique = [...new Set(nums)];
console.log(unique); // [1, 2, 3]
```

---

### 16. What does the `find()` method do in arrays?

**Answer:**
The `find()` method returns the first element that satisfies the provided testing function.

```js
const nums = [1, 2, 3, 4];
const found = nums.find((n) => n > 2);
console.log(found); // 3
```

---

### 17. How do you reverse an array?

**Answer:**
Use the `reverse()` method. It modifies the original array.

```js
const arr = [1, 2, 3];
arr.reverse();
console.log(arr); // [3, 2, 1]
```

---

### 18. How do you convert an array to a string?

**Answer:**
Use the `join()` method.

```js
const arr = ["a", "b", "c"];
console.log(arr.join("-")); // "a-b-c"
```

---

### 19. What is the difference between shallow and deep copy?

**Answer:**

- A **shallow copy** copies only the first level.
- A **deep copy** recursively copies all nested levels.

```js
const obj = { a: { b: 1 } };
const shallow = { ...obj };
const deep = JSON.parse(JSON.stringify(obj));
```

---

### 20. How do you sort an array of numbers?

**Answer:**
Use `sort()` with a compare function to avoid lexicographic sorting.

```js
const nums = [10, 1, 5];
nums.sort((a, b) => a - b);
console.log(nums); // [1, 5, 10]
```

---

### 21. How do you add or update a property in an object?

**Answer:**
You can assign a new value using dot or bracket notation.

```js
const obj = { name: "Eze" };
obj.age = 25; // Add
obj["country"] = "Nigeria"; // Add or update
```

---

### 22. What is object shorthand in JavaScript?

**Answer:**
When variable names match property names, you can use shorthand.

```js
const name = "Eze";
const age = 25;
const user = { name, age }; // same as { name: name, age: age }
```

---

### 23. How do you freeze an object in JavaScript?

**Answer:**
Use `Object.freeze()` to prevent properties from being added, removed, or modified.

```js
const obj = { name: "Eze" };
Object.freeze(obj);
obj.name = "Tobi";
console.log(obj.name); // "Eze"
```

---

### 24. How do you check if an array includes a specific value?

**Answer:**
Use the `includes()` method.

```js
const fruits = ["apple", "banana"];
console.log(fruits.includes("banana")); // true
```

---

### 25. How do you flatten a nested array?

**Answer:**
Use `flat()` to flatten one level, or pass a depth value for deeper flattening.

```js
const arr = [1, [2, [3]]];
console.log(arr.flat(2)); // [1, 2, 3]
```

---

### 26. How do you get all keys from an object?

**Answer:**
Use `Object.keys()` to get an array of the object’s keys.

```js
const obj = { a: 1, b: 2 };
console.log(Object.keys(obj)); // ["a", "b"]
```

---

### 27. How do you get all values from an object?

**Answer:**
Use `Object.values()` to retrieve all values as an array.

```js
const obj = { a: 1, b: 2 };
console.log(Object.values(obj)); // [1, 2]
```

---

### 28. What does the `some()` method do in arrays?

**Answer:**
`some()` checks if at least one element satisfies a condition and returns a boolean.

```js
const nums = [1, 2, 3];
const hasEven = nums.some((n) => n % 2 === 0);
console.log(hasEven); // true
```

---

### 29. What does the `every()` method do in arrays?

**Answer:**
`every()` checks if all elements meet a condition and returns a boolean.

```js
const nums = [2, 4, 6];
const allEven = nums.every((n) => n % 2 === 0);
console.log(allEven); // true
```

---

### 30. How do you convert an array to an object?

**Answer:**
Use `reduce()` or `Object.fromEntries()` with `map()` or `entries()`.

```js
const entries = [
  ["a", 1],
  ["b", 2],
];
const obj = Object.fromEntries(entries);
console.log(obj); // { a: 1, b: 2 }
```

---
