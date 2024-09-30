# ES6 Cheat Sheet and Tutorial

Welcome to the ES6 tutorial and cheat sheet! This guide will help you understand the key features introduced in ECMAScript 6 (ES6), as well as their practical applications with Node.js.

## Table of Contents

1. [What is ES6?](#what-is-es6)
2. [New Features in ES6](#new-features-in-es6)
   - [Constants vs Variables](#constants-vs-variables)
   - [Block-Scoped Variables](#block-scoped-variables)
   - [Arrow Functions](#arrow-functions)
   - [Default Parameters](#default-parameters)
   - [Rest and Spread Parameters](#rest-and-spread-parameters)
   - [String Templating](#string-templating)
   - [Object Creation and Properties](#object-creation-and-properties)
   - [Iterators and For-of Loops](#iterators-and-for-of-loops)
3. [Testing with Jest](#testing-with-jest)
4. [Linting with ESLint](#linting-with-eslint)
5. [Resources](#resources)

## What is ES6?

ES6, or ECMAScript 6, also known as ECMAScript 2015, is the sixth major release of the ECMAScript language specification. It brought significant improvements to JavaScript, providing developers with new syntax and functionalities that make the language more powerful and easier to write.

## New Features in ES6

### Constants vs Variables

In ES6, variables are declared using `var`, `let`, or `const`. The major difference between them is their scope and mutability.

- `var`: Function-scoped and can be re-assigned.
- `let`: Block-scoped and can be re-assigned.
- `const`: Block-scoped and **cannot** be re-assigned.

#### Example

```javascript
var x = 10;
x = 20; // OK

let y = 10;
y = 20; // OK

const z = 10;
z = 20; // Error: Assignment to constant variable
```

### Block-Scoped Variables

Variables declared with `let` and `const` are block-scoped, meaning they are only available within the nearest enclosing block.

#### Example

```javascript
if (true) {
  let a = 10;
  const b = 20;
  console.log(a); // 10
  console.log(b); // 20
}
console.log(a); // Error: a is not defined
console.log(b); // Error: b is not defined
```

### Arrow Functions

Arrow functions provide a shorter syntax for writing functions and automatically bind the value of `this` from the surrounding context.

#### Example

```javascript
// Traditional function
function greet(name) {
  return `Hello, ${name}`;
}

// Arrow function
const greet = (name) => `Hello, ${name}`;

console.log(greet("World")); // Hello, World
```

### Default Parameters

ES6 allows you to assign default values to function parameters if they are not provided.

#### Example

```javascript
function greet(name = "Guest") {
  return `Hello, ${name}`;
}

console.log(greet()); // Hello, Guest
console.log(greet("John")); // Hello, John
```

### Rest and Spread Parameters

- **Rest Parameter**: Gathers remaining arguments into an array.
- **Spread Operator**: Expands an array into individual elements.

#### Example (Rest Parameter)

```javascript
function sum(...numbers) {
  return numbers.reduce((total, num) => total + num, 0);
}

console.log(sum(1, 2, 3)); // 6
```

#### Example (Spread Operator)

```javascript
const arr1 = [1, 2, 3];
const arr2 = [...arr1, 4, 5, 6];

console.log(arr2); // [1, 2, 3, 4, 5, 6]
```

### String Templating

Template literals in ES6 allow embedding expressions inside strings using `${}`.

#### Example

```javascript
const name = "John";
const greeting = `Hello, ${name}! Welcome to ES6.`;

console.log(greeting); // Hello, John! Welcome to ES6.
```

### Object Creation and Properties

ES6 simplifies object creation and provides shorthand syntax for defining properties and methods.

#### Example

```javascript
const name = "Alice";
const age = 25;

// Shorthand property
const person = { name, age };

// Method shorthand
const obj = {
  sayHello() {
    return "Hello!";
  }
};

console.log(person); // { name: 'Alice', age: 25 }
console.log(obj.sayHello()); // Hello!
```

### Iterators and For-of Loops

The `for-of` loop allows you to iterate over iterable objects like arrays, strings, and more.

#### Example

```javascript
const arr = [10, 20, 30];

for (let value of arr) {
  console.log(value);
}
// Output: 10 20 30
```

## Testing with Jest

In this project, your code will be tested using the Jest framework. Make sure to write testable functions and export them properly.

### Example Test

```javascript
const sum = require('./sum');

test('adds 1 + 2 to equal 3', () => {
  expect(sum(1, 2)).toBe(3);
});
```

### Exporting Functions

```javascript
function sum(a, b) {
  return a + b;
}

module.exports = sum;
```

## Linting with ESLint

Make sure your code is linted using ESLint to ensure it follows the coding standards.

To configure ESLint, you can create a `.eslintrc` file in your project with specific rules.

### Example `.eslintrc`

```json
{
  "env": {
    "es6": true,
    "node": true
  },
  "extends": "eslint:recommended",
  "rules": {
    "no-console": "off",
    "quotes": ["error", "single"],
    "semi": ["error", "always"]
  }
}
```

### Running ESLint

```bash
eslint yourfile.js
```

## Resources

Here are some helpful resources to further your understanding of ES6:

- [ECMAScript 6 - ECMAScript 2015](https://www.w3schools.com/js/js_es6.asp)

- [Statements and Declarations](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements)
- [Arrow Functions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions)
- [Default Parameters](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Default_parameters)
- [Rest Parameter](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/rest_parameters)
- [Javascript ES6 — Iterables and Iterators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Iterators_and_Generators)

---
