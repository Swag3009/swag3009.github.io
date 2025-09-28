---
title: "JavaScript Basics: Notes for Quick Revision"
description: A quick revision guide on JavaScript basics to help you review key concepts for coding, interviews, or quick reference.
date: 2024-11-10
categories: [Programming, JavaScript]
tags: [JavaScript, Notes, Revision, reference]
author: Swagatika
image:
  path: "https://res.cloudinary.com/dduot1vgo/image/upload/v1756474997/study_gyu9so.jpg"
  alt: JavaScript-Basics Notes
---

## Introduction

I began coding in 2021, starting with Java, where I learned only some basics. Soon after, I picked up JavaScript and created my first project—a ping pong game. Although fun, I was mostly just following along with YouTube tutorials, copying each step without truly understanding the language.

Now, in 2024, I’m committed to mastering JavaScript concepts and coding independently without constantly relying on others’ code or Google. This blog marks the beginning of my journey to grasp JavaScript fully.

I’ve attempted to learn JavaScript concepts many times but struggled to retain them. My notes would get lost, I’d rarely revise, and my consistency wavered. This time, I’m making a dedicated effort to keep organized notes on GitHub and document my learning here. My goal is to have quick-reference notes, interview-ready concepts, and a reliable resource for coding. These notes serve as a personal reference for quick revisions and as a guide for others on a similar path.

## Let and Const

### **let**

1. It is _Block scoped_.
2. Let can be updated but not re-declared.

   ```js
   // Updated
   let name = "Swagatika";
   name = "Swagatika Mohapatra";

   // Re-declaration will throw an error
   let name = "Swagatika";
   let name = "Swagatika Mohapatra";
   ```

3. The same variable can be declared in different blocks without throwing an error, because both instances are treated as different variables due to their different scope.
4. **let** declarations are hoisted to the top.
5. Unlike **var**, the **let** keyword is not initialized. If we try to use it before initialization, it will throw a **ReferenceError**.

### **const**

1. It is _Block scoped_.
2. **const** declarations are hoisted to the top but are not initialized.
3. It cannot be updated or re-declared. Therefore, it must be initialized at the time of declaration.
4. **const** objects cannot be reassigned, but the properties of the object can be updated.

   ```js
   const time = {
     min: 34,
     sec: 12,
   };

   // Can't reassign the whole object
   time = {
     minutes: "thirty four",
     seconds: "five",
   };

   // Can update properties of the object
   time.min = "thirty four";
   ```

## Datatype Conversion

- **String Conversion**: You can convert various data types to strings using the `String()` function.
- **Number Conversion**: To convert strings to numbers, use the `Number()` function. You can also use `parseInt()` and `parseFloat()` for specific conversions.
- **Boolean Conversion**: The `Boolean()` function is used to convert values to booleans. `0`, `null`, `undefined`, `NaN`, and `""` are considered `false`; all other values are `true`.

### Type Conversion Examples

| **Conversion**         | **Example**           | **Result** |
| ---------------------- | --------------------- | ---------- | --- |
| **String Conversion**  | `String(123)`         | `"123"`    |
|                        | `String(false)`       | `"false"`  |
| **Number Conversion**  | `Number("123")`       | `123`      |
|                        | `Number(" 10 ")`      | `10`       |
|                        | `Number("10.33")`     | `10.33`    |
|                        | `Number("10,33")`     | `NaN`      |
|                        | `Number("John")`      | `NaN`      |
| **parseInt()**         | `parseInt("10")`      | `10`       |
|                        | `parseInt("10.33")`   | `10`       |
| **parseFloat()**       | `parseFloat("10.33")` | `10.33`    |
| **Boolean Conversion** | `Boolean(0)`          | `false`    |
|                        | `Boolean(1)`          | `true`     |
|                        | `Boolean("")`         | `false`    |
|                        | `Boolean("Hello")`    | `true`     | --- |

## Date Conversion

- **Date()**: Converts a date to a string or creates a new Date object.
- **getTime()**: Returns the number of milliseconds since January 1, 1970.
- **getDate()**: Returns the day of the month (1-31) for a specified date.
- **getDay()**: Returns the day of the week (0-6) for a specified date.
- **getFullYear()**: Returns the full year (4 digits) of a specified date.
- **getHours()**: Returns the hour (0-23) for a specified date.
- **getMilliseconds()**: Returns the milliseconds (0-999) for a specified date.
- **getMinutes()**: Returns the minutes (0-59) for a specified date.
- **getMonth()**: Returns the month (0-11) for a specified date.
- **getSeconds()**: Returns the seconds (0-59) for a specified date.
- **toDateString()**: Converts the date portion of a Date object to a readable string.
- **toTimeString()**: Converts the time portion of a Date object to a readable string.
- **toLocaleDateString()**: Returns a date as a string, formatted according to local conventions.
- **toLocaleTimeString()**: Returns the time as a string, formatted according to local conventions.
- **toISOString()**: Returns a date as a string in simplified extended ISO format (UTC time).

### Date Conversion Examples

| **Syntax**                        | **Example**                       | **Result**                                   |
| --------------------------------- | --------------------------------- | -------------------------------------------- |
| `Date()`                          | `Date("2024-11-06")`              | `"Wed Nov 06 2024 00:00:00 GMT+0000 (UTC)"`  |
| `new Date().getTime()`            | `new Date().getTime()`            | `1699190400000`                              |
| `new Date().getDate()`            | `new Date().getDate()`            | `6` (if today is the 6th)                    |
| `new Date().getDay()`             | `new Date().getDay()`             | `3` (if today is Wednesday)                  |
| `new Date().getFullYear()`        | `new Date().getFullYear()`        | `2024`                                       |
| `new Date().getHours()`           | `new Date().getHours()`           | `14` (if current time is 2:00 PM)            |
| `new Date().getMilliseconds()`    | `new Date().getMilliseconds()`    | `250` (if current millisecond is 250)        |
| `new Date().getMinutes()`         | `new Date().getMinutes()`         | `30` (if current minute is 30)               |
| `new Date().getMonth()`           | `new Date().getMonth()`           | `10` (November, since months are zero-based) |
| `new Date().getSeconds()`         | `new Date().getSeconds()`         | `45` (if current second is 45)               |
| `new Date().toDateString()`       | `new Date().toDateString()`       | `"Wed Nov 06 2024"`                          |
| `new Date().toTimeString()`       | `new Date().toTimeString()`       | `"14:30:00 GMT+0000 (UTC)"`                  |
| `new Date().toLocaleDateString()` | `new Date().toLocaleDateString()` | `"11/6/2024"` (format varies by locale)      |
| `new Date().toLocaleTimeString()` | `new Date().toLocaleTimeString()` | `"2:30:00 PM"` (format varies by locale)     |
| `new Date().toISOString()`        | `new Date().toISOString()`        | `"2024-11-06T14:30:00.000Z"`                 |

## String

In JavaScript, strings are sequences of characters used to represent text. You can work with strings using various built-in methods that allow you to manipulate and transform text efficiently.

### String Methods

- **String.length**: Returns the length of a string (i.e., the number of characters in it).
- **String.charAt()**: Returns the character at a specified index in a string.
- **String.charCodeAt()**: Returns the Unicode value (UTF-16) of the character at a specified index.
- **String.at()**: Returns the character at the specified position in a string, handling negative indices as well.
- **String[]**: Allows accessing characters in a string using bracket notation (similar to arrays).
- **String.slice()**: Extracts a section of a string and returns it as a new string.
- **String.substring()**: Returns a part of the string between two specified indices (but does not include the character at the second index).
- **String.substr()**: Returns a portion of the string starting from a specified index and extending a given number of characters.
- **String.toUpperCase()**: Converts all characters of a string to uppercase.
- **String.toLowerCase()**: Converts all characters of a string to lowercase.
- **String.concat()**: Concatenates one or more strings to the original string.
- **String.trim()**: Removes whitespace from both ends of a string.
- **String.trimStart()**: Removes whitespace from the beginning of a string.
- **String.trimEnd()**: Removes whitespace from the end of a string.
- **String.padStart()**: Pads the start of a string with another string until the string reaches a certain length.
- **String.padEnd()**: Pads the end of a string with another string until the string reaches a certain length.
- **String.repeat()**: Repeats the string a specified number of times.
- **String.replace()**: Replaces the first occurrence of a specified substring with another string.
- **String.replaceAll()**: Replaces all occurrences of a specified substring with another string.
- **String.split()**: Splits a string into an array of substrings based on a specified delimiter.

### Example

| **Syntax**                              | **Example**                    | **Result**              |
| --------------------------------------- | ------------------------------ | ----------------------- |
| `string.length`                         | `"Hello".length`               | `5`                     |
| `string.charAt(index)`                  | `"Hello".charAt(1)`            | `"e"`                   |
| `string.charCodeAt(index)`              | `"Hello".charCodeAt(1)`        | `101` (Unicode for `e`) |
| `string.at(index)`                      | `"Hello".at(1)`                | `"e"`                   |
| `string[index]`                         | `"Hello"[1]`                   | `"e"`                   |
| `string.slice(start, end)`              | `"Hello".slice(1, 4)`          | `"ell"`                 |
| `string.substring(start, end)`          | `"Hello".substring(1, 4)`      | `"ell"`                 |
| `string.substr(start, length)`          | `"Hello".substr(1, 3)`         | `"ell"`                 |
| `string.toUpperCase()`                  | `"Hello".toUpperCase()`        | `"HELLO"`               |
| `string.toLowerCase()`                  | `"Hello".toLowerCase()`        | `"hello"`               |
| `string.concat(str1, str2)`             | `"Hello".concat(" ", "World")` | `"Hello World"`         |
| `string.trim()`                         | `"  Hello  ".trim()`           | `"Hello"`               |
| `string.trimStart()`                    | `"  Hello".trimStart()`        | `"Hello"`               |
| `string.trimEnd()`                      | `"Hello  ".trimEnd()`          | `"Hello"`               |
| `string.padStart(targetLength, pad)`    | `"5".padStart(3, "0")`         | `"005"`                 |
| `string.padEnd(targetLength, pad)`      | `"5".padEnd(3, "0")`           | `"500"`                 |
| `string.repeat(count)`                  | `"Hi ".repeat(3)`              | `"Hi Hi Hi "`           |
| `string.replace(oldValue, newValue)`    | `"Hello".replace("l", "r")`    | `"Hero"`                |
| `string.replaceAll(oldValue, newValue)` | `"Hello".replaceAll("l", "r")` | `"Heroo"`               |
| `string.split(separator)`               | `"Hello World".split(" ")`     | `["Hello", "World"]`    |

## Template Literal

- Denoted with backticks (\`\`)
- Allows multi-line strings.

  ```js
  let text = `The quick
  brown fox 
  jumps over
  the lazy dog.`;
  ```

- Allows interpolation of variables and expressions into the string. The **${}** syntax is used to embed variables and expressions inside the string. Within the placeholder, it must be an expression; if a non-expression like a function declaration is provided, it will be stringified.
  ```js
  let name = `Swagatika`;
  let fullName = `${name} Mohapatra`;
  ```

### Usage

- **Generating HTML Markup**  
  It allows embedding JavaScript expressions directly into HTML strings, making it easier to create dynamic content.

- **Creating Dynamic SQL Queries**  
  You can embed variables or expressions directly into query strings to create queries based on runtime values.

- **Tagged Template Literals**  
  A tagged template literal is a function call with arguments that come from the template literal.
  - When the tag function is called, the first argument it receives is an array of strings, which result from splitting the template literal at the interpolated parts.
  - Each interpolated value is passed to the function as additional arguments, which can be accessed using the rest parameter.

  ```js
  function tagfunc(string, ...substitution) {
    console.log(string);
    console.log(substitution);
  }

  let name = `Swagatika`;
  let beverage = `Coffee`;
  tagfunc`Hello ${name}! Would you like to have ${beverage}`;

  // Output
  /*
  ['Hello', '! Would you like to have', '']
  ['Swagatika', 'C']
  ```

## Array

In JavaScript, an array is a special type of object used to group, store, and organize multiple values under a single variable name. This allows for efficient management and manipulation of data collections. JavaScript arrays can hold elements of any type, and their length is dynamic, meaning it can grow or shrink as elements are added or removed.

### Destructive Array Methods

Destructive array methods alter the original arrays, modifying their contents directly.

- **pop()**: Removes the last element of an array.
  - Syntax: `array.pop();`

- **push()**: Adds a new element to the end of the array.
  - Syntax: `array.push(element);`

- **shift()**: Removes the first element of an array and returns the shifted element.
  - Syntax: `array.shift();`

- **unshift()**: Adds a new element to the beginning of the array.
  - Syntax: `array.unshift(element);`

- **splice()**: Adds or removes elements at a specific index in an array. When removing elements, it returns the removed elements.
  - Syntax: `array.splice(index, howMany, element1, element2, ..., elementN);`
    - **index**: Specifies where to add or remove elements.
    - **howMany** (optional): Number of elements to remove.
    - **elements**: Elements to insert.

### Non-Destructive Array Methods

Non-destructive array methods in JavaScript return a new array or value without modifying the original array. These methods are useful when you want to preserve the original array while storing the modified data in a new one.

- **concat()** : Joins two or more arrays and returns the result as a new array.
  - Syntax: `array.concat(array2, array3, ...);`

- **slice()** : Creates a new array with selected elements from the original array, using optional start and end positions. By default, start is the 0th element and end is the last element.
  - Syntax: `array.slice(start, end);`

- **filter()** : Creates a new array with all elements that pass a specified test implemented by a function.
  - Syntax: `array.filter(callback(element, index, array));`

- **join()** : Returns a string with all array elements joined together. An optional separator specifies the preferred separator.
  - Syntax: `array.join(separator);`

### Iterating Over Array Elements

- **includes()** : Checks if a specific element is present in the array, returning true if found or false otherwise.
  - Syntax: `array.includes(value, start);`

- **every()** : Executes a function as a test for each element. Returns true if all elements pass, false if at least one fails. Skips empty elements.
  - Syntax: `array.every(callback(element, index, array));`

- **some()** : Tests if at least one array element passes a specified function. Returns true and stops execution if any element passes; returns false if all elements fail.
  - Syntax: `array.some(callback(element, index, array));`

- **forEach** : Executes a specified function once for each array element.
  - Syntax: `array.forEach(callback(element, index, array));`
- **for...of** : The `for...of` loop is used to iterate over each element in the array without needing to reference the index.
  - Syntax:
    ```js
    for (let element of array) {
      // process element
    }
    ```

#### map()

- Takes an array of values and applies a transformation to each value in the array.
- Does not mutate the original array.
- Creates a new array with the transformed values.
- Syntax: `array.map(callback(element, index, array));`
- Example:
  ```js
  const arr = [1, 2, 3, 4, 5];
  const output = arr.map((num) => (num += 10));
  console.log(arr); // [1, 2, 3, 4, 5]
  console.log(output); // [11, 12, 13, 14, 15]
  ```

#### filter()

- Takes an array and returns a new array with only the values that meet certain criteria.
- Does not mutate the original array.
- Selects a subset of data from an array based on specific conditions.
- Syntax: `array.filter(callback(element, index, array));`
- Example:

```js
const arr = [1, 2, 3, 4, 5];
const output = arr.filter((num) => num % 2); // filter out odd numbers
console.log(arr); // [1, 2, 3, 4, 5]
console.log(output); // [1, 3, 5]
```

#### reduce()

- Iterates over an array and reduces the array's values into a single value.
- The accumulator parameter is the single value that will be returned by the method.
- The currentValue parameter is the item from the array, which changes in each iteration.
- After iterating over each element, it returns the final accumulator value.
- If an initial accumulator value isn't provided, the first item in the array is used as the initial accumulator.
- Used for:
  - Summarizing values into a single value.
  - Grouping similar items together.
  - Removing duplicates from an array.
- Syntax:
  ```js
  array.reduce((accumulator, item, index, array) => {
    // Define the process for each iteration
  }, initialAccumulatorValue);
  ```
- Example:

```js
const array1 = [1, 2, 3, 4];

// 0 + 1 + 2 + 3 + 4
const initialValue = 0;
const sumWithInitial = array1.reduce(
  (accumulator, currentValue) => accumulator + currentValue,
  initialValue,
);

console.log(sumWithInitial);
// Expected output: 10
```

## Objects

- In JavaScript, objects help to group values with similar characteristics together, making the code more readable, organized, and manageable.
- An object is a data type that stores collections of key-value pairs.
- Objects can store different types of data as their values.
- The key of an object is a string. If any other datatype is used as the key, it is automatically converted into a string.
- There are two ways to access properties of an object:
  - **Dot notation (`.`)**
  - **Bracket notation (`[]`)**
- If you want to use the value of a variable as the property name of an object, you must use bracket notation, not dot notation.
- For multi-word property names, dot notation cannot be used.

### for..in loop

The `for...in` loop iterates over the enumerable properties (keys) of an object. It allows you to access each key in an object, which can then be used to retrieve the corresponding value.

### Copying Objects

Assigning an object to another variable doesn't copy the object. Instead, it creates a reference to the same memory location. This means that both the original object and the object created by assignment are referencing the same item in memory.

- Example: If you modify the copied object, the original object is also modified.

```js
let user1 = {
  name: "Swagatika",
  age: 21,
};
let user2 = user1;
console.log(user1 === user2); //true
user2.age = 23;
console.log(user1.age); //23
```

To properly copy an object, you can use either the **spread operator** or **`Object.assign()`** to create a shallow copy of an object.

- **Spread Operator:** Creates a shallow copy of an object.
- **`Object.assign()`**: Copies properties from one or more source objects to a target object.
  - `target_object`: The object that receives the copied properties.
  - `source_object`: The object whose properties are copied to the target.
- Example:

```js
// spread operator
let obj1 = { ...obj2 };
// object.assign()
let obj = Object.assign(target_object, sourc_Object);
/*
target_object -> which takes the properties copied
source_object -> properties you want to copy
*/
```

## Destructuring

Destructuring assignment is a JavaScript expression that allows you to unpack values from arrays or properties from objects into distinct variables.

### Object Destructuring

Object destructuring is the syntax for extracting values from object properties and assigning them to variables.

- Example:

```js
const user = {
  first_name: "Swagatika",
  last_name: "Mohapatra",
};
const {
  first_name,
  last_name,
  full_name = `${first_name} ${last_name}`,
} = user;
```

### Add Aliases

An alias name can be given to destructured variables. This is useful when you want to rename the variable.

- Example:

```js
const user = {
  name: "Swagatika",
  address: "Forest Colony",
  age: 21,
};
const { address: permanentAddress } = user;
console.log(permanentAddress); // Output -> Forest Colony
```

Attempting to access the variable `address` directly will result in an error.

### Nested Object Destructuring

To destructure nested objects, start with the top level and go down the hierarchy until you reach the desired property.

- Example:

```js
const user = {
  name: "Alex",
  address: "15th Park Avenue",
  age: 43,
  department: {
    name: "Sales",
    Shift: "Morning",
    address: {
      city: "Bangalore",
      street: "7th Residency Rd",
      zip: 560001,
    },
  },
};
const {
  department: {
    address: { city },
  },
} = user;
console.log(city); // Output -> Bangalore
```

### Dynamic Property Names

You can use dynamic property names when destructuring, which is helpful when the key is stored in a variable.

- Example:

```js
const user = {
  name: "Swagatika",
  address: "Forest Colony",
  age: 21,
};
getValue = (key) => {
  const { [key]: returnValue } = user;
  return returnValue;
};
console.log(getValue("name")); // Output -> Swagatika
```

### Destructuring in Function Parameters

Destructuring can be used in function parameters to extract only the necessary properties from an object, without needing to pass the entire object and then access its properties.

- Example:

```js
const user = {
  name: "Alex",
  address: "15th Park Avenue",
  age: 43,
};
function logDetails({ name, age }) {
  console.log(`${name} is ${age} year(s) old!`);
}
logDetails(user);
```

### Destructuring Function Return Values

When a function returns an object and you only need specific properties, you can use destructuring.

- Example:

```js
const getUser = () => {
  return {
    name: "Alex",
    address: "15th Park Avenue",
    age: 43,
  };
};
const { name, age } = getUser();
console.log(name, age);
```

### Destructuring in Loops

You can use destructuring within a `for-of` loop to extract specific values from each object in an array.

- Example:

```js
const users = [
  {
    name: "Alex",
    address: "15th Park Avenue",
    age: 43,
  },
  {
    name: "Bob",
    address: "Canada",
    age: 53,
  },
  {
    name: "Carl",
    address: "Bangalore",
    age: 26,
  },
];
for (let { name, age } of users) {
  console.log(`${name} is ${age} years old!`);
}
```

### Console Object Destructuring

You can destructure properties of the console object, which is a built-in object in JavaScript, to make logging more concise.

- Example:

```js
const { log, warn, error } = console;

log("I log into the browser console");
warn("I am a warning");
error("I am an error");
```

## Spread Operator

The spread operator allows you to expand elements of an iterable (like an array or object) into individual elements. It can also be used to clone objects, add properties to them, and merge multiple objects.

### Create Clone of an Object

The spread operator performs a shallow copy of an object, meaning nested objects are not cloned, and they still reference the same memory.

- Example:

```js
const user = {
  name: "Alex",
  address: "15th Park Avenue",
  age: 43,
};

const clone = { ...user };
console.log(clone); // Output -> {name: "Alex", address: "15th Park Avenue", age: 43}

clone === user; // Output -> false
```

### Add Properties to Objects

You can use the spread syntax to add new properties to a cloned object, ensuring the original object remains unchanged.

- Example:

```js
const user = {
  name: "Alex",
  address: "15th Park Avenue",
  age: 43,
};

const updatedUser = { ...user, salary: 12345 };
console.log(updatedUser); // Output -> {name: "Alex", address: "15th Park Avenue", age: 43, salary: 12345}

console.log(user); // Output -> {name: "Alex", address: "15th Park Avenue", age: 43}
```

### Update Nested Objects

You can also update properties of nested objects using the spread operator. This creates a shallow copy of the object, while updating the necessary nested properties.

- Example:

```js
const user = {
  name: "Alex",
  address: "15th Park Avenue",
  age: 43,
  department: {
    name: "Sales",
    shift: "Morning",
    address: {
      city: "Bangalore",
      street: "7th Residency Rd",
      zip: 560001,
    },
  },
};

const updated = {
  ...user,
  department: {
    ...user.department,
    number: 7,
  },
};

console.log(updated);
```

### Combine Two Objects

You can merge two objects using the spread operator. This performs a shallow merge, where properties of the second object will overwrite those of the first object if they have the same key.

- Syntax:

```js
const merged = { ...obj1, ...obj2 };
```

## Rest Operator

The rest operator gathers elements into an object, usually used in destructuring to collect the remaining properties that are not explicitly extracted.

- Example:

```js
const user = {
  name: "Alex",
  address: "15th Park Avenue",
  age: 43,
};

const { age, ...rest } = user;
console.log(age); // Output -> 43
console.log(rest); // Output -> {name: "Alex", address: "15th Park Avenue"}
```

## Function

A function is a block of code designed to perform a specific task. Functions are used to promote reusability, improve readability, simplify testing, provide abstraction, enable collaboration, and support modularization.

- In JavaScript, functions are **first-class citizens**, meaning they can be treated as values and passed around like any other variable.

### Parameters vs Arguments

- **Parameters**: These are the references to values that will be used in a function.
- **Arguments**: These are the actual values passed to the function when it is called.

```js
function add(num1, num2) {
  return num1 + num2;
}
// Here, num1 and num2 are parameters.
add(2, 3);
// Here, 2 and 3 are arguments.
```

### Anonymous Function

An **anonymous function** is a function that does not have a name. It is typically used for specific tasks, and it is often assigned to variables or passed as arguments to other functions. It is particularly useful when you do not need to reuse the function outside its immediate context.

- Anonymous functions are not accessible after their initial creation, unless assigned to a variable.
- The parentheses `()` around the function body are required to treat the function as an expression, which returns a function object.
- Syntax:

```js
// Anonymous function with the function keyword
(function () {
  // Statements
})();

// Anonymous arrow function
() => {
  // Statements
};
```

### Immediately Invoked Function Expression (IIFE)

An **IIFE** (Immediately Invoked Function Expression) is a function that is invoked immediately after it is defined. It is commonly used to create a local scope for variables, preventing them from polluting the global scope.

- Syntax:

```js
(function () {
  // Statement
})();

(() => {
  // Statement
})();
```

### Arrow Function

Arrow functions provide a shorter syntax for defining functions. However, they have some important differences from traditional functions:

- Arrow functions do **not** have their own `this`, `arguments`, or `super`. Therefore, they should **not** be used as methods.
- Arrow functions **cannot** be used as constructors, and calling them with `new` throws a `TypeError`.
- Arrow functions cannot use `yield` and cannot be defined as generator functions.
- Syntax:

```js
() => expression
param => expression
(param) => expression
(param1, paramN) => expression
(param1, paramN) => (expression) // Parentheses around the expression

// Returning an object
(param1, paramN) => ({ obj: 'obj' })

() => {
  // Statements
}

param => {
  // Statements
}

(param1, paramN) => {
  // Statements
}

```

- **Rest parameters**, **default parameters**, and **destructuring** can be used in arrow functions and always require parentheses.
  - Example:

```js
(a, b, ...r) => expression
(a = 400, b = 20, c) => expression
([a, b] = [10, 20]) => expression
({ a, b } = { a: 10, b: 20 }) => expression

```

- Arrow functions can be `async` by prefixing the function with the `async` keyword.
  - Syntax:

```js
async (param) => expression;
async (param1, param2, ...paramN) => {
  statements;
};
```

### 'this' in Arrow Functions

- Arrow functions **do not** bind their own `this`. Instead, they inherit `this` from the **parent scope**. This behavior is known as "lexical scoping."

### Higher Order Function

A **higher-order function** is a function that:

- Takes one or more functions as arguments, or
- Returns a function as its result.
- Example:

```js
function greeting(message) {
  return function (name) {
    console.log(`${message}, ${name}!`);
  };
}

const greet = greeting("Hello");
greet("John"); // Outputs: "Hello, John!"
```

## Closure

A **closure** is the combination of a function bundled together (enclosed) with references to its surrounding state (the lexical environment). In other words, a closure gives you access to an outer function's scope from an inner function.

### How Closures Work

1. When a function is created inside another function, it has access to the variables in the outer function's scope due to **lexical scoping**.
2. **Scope Chain**: In closures, JavaScript looks through the nested scope for variable values:
   - The inner function first checks its own scope.
   - If the variable is not found, it looks in the outer scope, continuing outward until it either finds the variable or throws a reference error.
3. **Lexical Scope** means variables are accessed based on where functions are declared, not where they are called.

### Example

```js
function outer() {
  const outerVar = "I am from outer function";

  function inner() {
    console.log(outerVar); // Inner function has access to outer function's variable
  }

  return inner;
}

const closureFunc = outer(); // outer function returns inner function
closureFunc(); // Outputs: 'I am from outer function'
```

## Conclusion

These are the JavaScript basics I’ve learned so far. As I continue solving new problems, I’ll pick up additional concepts and update my notes accordingly. This blog will grow as my knowledge does. After covering the basics, I’ll dive into advanced JavaScript concepts, with another blog post coming soon to document that journey. Stay tuned for more updates as I progress!

Happy coding, and enjoy the journey!
