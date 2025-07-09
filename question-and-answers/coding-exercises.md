# JavaScript: Coding Exercises

A collection of common JavaScript coding exercises often asked in interviews for junior developers.

---

### 1. Reverse a String

**Question:**
Write a function that reverses a given string.

```js
function reverseString(str) {
  return str.split("").reverse().join("");
}

console.log(reverseString("hello")); // "olleh"
```

---

### 2. Check for Palindrome

**Question:**
Write a function to check if a string is a palindrome (reads the same forwards and backwards).

```js
function isPalindrome(str) {
  const cleaned = str.toLowerCase().replace(/[^a-z0-9]/g, "");
  return cleaned === cleaned.split("").reverse().join("");
}

console.log(isPalindrome("Racecar")); // true
```

---

### 3. Find the Maximum Number in an Array

**Question:**
Write a function that returns the largest number in an array.

```js
function findMax(arr) {
  return Math.max(...arr);
}

console.log(findMax([10, 5, 20, 3])); // 20
```

---

### 4. Count Vowels in a String

**Question:**
Write a function that counts the number of vowels in a given string.

```js
function countVowels(str) {
  return (str.match(/[aeiou]/gi) || []).length;
}

console.log(countVowels("hello world")); // 3
```

---

### 5. FizzBuzz

**Question:**
Write a function that prints numbers from 1 to `n`. For multiples of 3, print "Fizz"; for multiples of 5, print "Buzz"; for multiples of both, print "FizzBuzz".

```js
function fizzBuzz(n) {
  for (let i = 1; i <= n; i++) {
    if (i % 3 === 0 && i % 5 === 0) console.log("FizzBuzz");
    else if (i % 3 === 0) console.log("Fizz");
    else if (i % 5 === 0) console.log("Buzz");
    else console.log(i);
  }
}

fizzBuzz(15);
```

---

### 6. Factorialize a Number

**Question:**
Write a function that returns the factorial of a number.

```js
function factorial(n) {
  if (n === 0) return 1;
  return n * factorial(n - 1);
}

console.log(factorial(5)); // 120
```

---

### 7. Find the Longest Word in a Sentence

**Question:**
Write a function that finds the longest word in a given sentence.

```js
function longestWord(sentence) {
  const words = sentence.split(" ");
  return words.reduce(
    (longest, word) => (word.length > longest.length ? word : longest),
    ""
  );
}

console.log(longestWord("The quick brown fox")); // "quick"
```

---

### 8. Title Case a Sentence

**Question:**
Write a function that capitalizes the first letter of each word in a sentence.

```js
function titleCase(sentence) {
  return sentence
    .toLowerCase()
    .split(" ")
    .map((word) => word.charAt(0).toUpperCase() + word.slice(1))
    .join(" ");
}

console.log(titleCase("hello world")); // "Hello World"
```

---

### 9. Return Largest Numbers in Arrays

**Question:**
Return an array consisting of the largest number from each sub-array.

```js
function largestOfEach(arr) {
  return arr.map((sub) => Math.max(...sub));
}

console.log(
  largestOfEach([
    [1, 5],
    [10, 3],
    [4, 7],
  ])
); // [5, 10, 7]
```

---

### 10. Confirm the Ending

**Question:**
Check if a string ends with a specific target string.

```js
function confirmEnding(str, target) {
  return str.endsWith(target);
}

console.log(confirmEnding("hello", "lo")); // true
```

---

### 11. Repeat a String

**Question:**
Repeat a string a given number of times.

```js
function repeatString(str, num) {
  return num > 0 ? str.repeat(num) : "";
}

console.log(repeatString("abc", 3)); // "abcabcabc"
```

---

### 12. Truncate a String

**Question:**
Truncate a string if it is longer than a given maximum string length.

```js
function truncateString(str, num) {
  return str.length > num ? str.slice(0, num) + "..." : str;
}

console.log(truncateString("A-tisket a-tasket A green and yellow basket", 8)); // "A-tisket..."
```

---

### 13. Chunk an Array

**Question:**
Split an array into groups of a specified size.

```js
function chunkArray(arr, size) {
  const result = [];
  for (let i = 0; i < arr.length; i += size) {
    result.push(arr.slice(i, i + size));
  }
  return result;
}

console.log(chunkArray([1, 2, 3, 4, 5], 2)); // [[1, 2], [3, 4], [5]]
```

---

### 14. Slugify a String

**Question:**
Convert a string into a URL-friendly slug.

```js
function slugify(str) {
  return str.toLowerCase().trim().replace(/\s+/g, "-");
}

console.log(slugify(" Hello World! ")); // "hello-world"
```

---

### 15. Remove Falsy Values from an Array

**Question:**
Remove all falsy values from an array (`false`, `null`, `0`, `""`, `undefined`, and `NaN`).

```js
function removeFalsy(arr) {
  return arr.filter(Boolean);
}

console.log(removeFalsy([0, "hello", false, "world", null])); // ["hello", "world"]
```

---

### 16. Find the Index of a Value

**Question:**
Return the index of a value in an array. If it does not exist, return -1.

```js
function findIndex(arr, val) {
  return arr.indexOf(val);
}

console.log(findIndex([1, 2, 3], 2)); // 1
```

---

### 17. Capitalize the First Letter

**Question:**
Capitalize the first letter of a given string.

```js
function capitalizeFirst(str) {
  return str.charAt(0).toUpperCase() + str.slice(1);
}

console.log(capitalizeFirst("hello")); // "Hello"
```

---

### 18. Merge Two Arrays Without Duplicates

**Question:**
Merge two arrays and remove duplicate values.

```js
function mergeUnique(arr1, arr2) {
  return [...new Set([...arr1, ...arr2])];
}

console.log(mergeUnique([1, 2], [2, 3])); // [1, 2, 3]
```

---

### 19. Count Occurrences of a Character

**Question:**
Count how many times a specific character appears in a string.

```js
function countChar(str, char) {
  return str.split("").filter((c) => c === char).length;
}

console.log(countChar("hello", "l")); // 2
```

---

### 20. Check if All Letters Are Present

**Question:**
Check if all the letters in the second string are present in the first string.

```js
function containsAllLetters(str1, str2) {
  const first = str1.toLowerCase();
  const second = str2.toLowerCase();
  return [...second].every((char) => first.includes(char));
}

console.log(containsAllLetters("hello", "he")); // true
```

---

### 21. Sum All Numbers in a Range

**Question:**
Return the sum of two numbers and all numbers between them.

```js
function sumAll(arr) {
  const [min, max] = [Math.min(...arr), Math.max(...arr)];
  let total = 0;
  for (let i = min; i <= max; i++) {
    total += i;
  }
  return total;
}

console.log(sumAll([1, 4])); // 10
```

---

### 22. Remove Specific Elements from Array

**Question:**
Remove all elements from an array that match any of the given values.

```js
function removeElements(arr, ...vals) {
  return arr.filter((el) => !vals.includes(el));
}

console.log(removeElements([1, 2, 3, 1, 2, 3], 2, 3)); // [1, 1]
```

---

### 23. Convert Celsius to Fahrenheit

**Question:**
Convert a given Celsius temperature to Fahrenheit.

```js
function convertToF(celsius) {
  return (celsius * 9) / 5 + 32;
}

console.log(convertToF(0)); // 32
```

---

### 24. Find the First Truthy Value

**Question:**
Return the first element in an array that passes a test.

```js
function findElement(arr, func) {
  return arr.find(func);
}

console.log(findElement([1, 3, 5, 8, 9, 10], (num) => num % 2 === 0)); // 8
```

---

### 25. Check Boolean Primitive

**Question:**
Check if a value is classified as a boolean primitive.

```js
function isBoolean(val) {
  return typeof val === "boolean";
}

console.log(isBoolean(false)); // true
```

---

### 26. Repeat a Number Until Condition Met

**Question:**
Return the smallest power of two greater than a given number.

```js
function nextPowerOfTwo(n) {
  let result = 1;
  while (result <= n) {
    result *= 2;
  }
  return result;
}

console.log(nextPowerOfTwo(5)); // 8
```

---

### 27. Remove Duplicate Characters from a String

**Question:**
Return a string with duplicate characters removed.

```js
function removeDuplicates(str) {
  return [...new Set(str)].join("");
}

console.log(removeDuplicates("hello")); // "helo"
```

---

### 28. Get the Sum of Digits

**Question:**
Calculate the sum of digits of a given number.

```js
function sumDigits(num) {
  return num
    .toString()
    .split("")
    .reduce((sum, d) => sum + +d, 0);
}

console.log(sumDigits(123)); // 6
```

---

### 29. Find Missing Number in Sequence

**Question:**
Find the missing number in a sequence of consecutive integers.

```js
function findMissing(arr) {
  const n = arr.length + 1;
  const expectedSum = (n * (n + 1)) / 2;
  const actualSum = arr.reduce((a, b) => a + b, 0);
  return expectedSum - actualSum;
}

console.log(findMissing([1, 2, 4, 5])); // 3
```

---

### 30. Convert a String to Spinal Case

**Question:**
Convert a string to spinal case (all-lowercase-words-joined-by-dashes).

```js
function spinalCase(str) {
  return str
    .split(/\s|_|(?=[A-Z])/)
    .join("-")
    .toLowerCase();
}

console.log(spinalCase("This Is Spinal Tap")); // "this-is-spinal-tap"
```

---
