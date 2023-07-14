# js-workshop

😎 JavaScript workshop for first-time JS programmers.

## Getting started

Welcome to the world of JavaScript! This workshop is designed to help you get started with programming in JavaScript. Today, we'll cover the basics of JavaScript syntax.

## Beginning of JavaScript

JavaScript, despite its widespread usage and popularity, had humble beginnings. In 1995, Brendan Eich developed the language in just a few days while working at Netscape Communications Corporation.

JavaScript was created to provide a scripting language for web pages on the Netscape Navigator browser. It was originally named Mocha but was renamed to LiveScript and then JavaScript. The name change was a marketing tactic to capitalize on the popularity of Java, a popular programming language at the time.

## JavaScript runtime and where to get one

JavaScript is an interpreted language, meaning that it is executed by a runtime, a program that executes code. Your web browser is a JavaScript runtime, and it executes JavaScript code that is included in web pages.

However, you can also run JavaScript code outside of a web browser for unlimited applications. There are many JavaScript runtimes available, but the most popular one is Node.js. Node.js is a JavaScript runtime that is built on top of the V8 JavaScript engine, which is the same engine that powers the Google Chrome web browser. Node.js and its successor, Deno are used to build web servers, command-line tools, and desktop applications.

Let's start by opening your browser of choice to any page and opening up the developer tools. In Chrome, you can do this by right-clicking anywhere on the page and selecting "Inspect". Then, click on the "Console" tab. This is where we can write JavaScript code and see the results.

### How to print to the console

Let's start by printing "Hello, world!" to the console. In the console, type the following expression.

```js
console.log("Hello, world!");
```

You should see the following output.

```txt
Hello, world!
```

### Simple expressions

Now, let's try some simple expressions. In the console, type `1 + 1`.

The console is a REPL (read-eval-print loop), which means that it reads your input, evaluates it, and prints the result. You may use the REPL as a calculator to perform simple arithmetic using JavaScript syntax.

The console exposes all of the global variables and functions that are held in the current JavaScript interpreter instance.

### How to run a JavaScript file in a browser

Now, let's try running a JavaScript file in a browser. Create a new file called `index.html` and add the following code.

```html
<!DOCTYPE html>
<html>
  <head>
    <title>JavaScript Workshop</title>
  </head>
  <body>
    <script src="/script.js"></script>
  </body>
</html>
```

Then, create a new file called `script.js` and add your "Hello, world" program.

```js
console.log("Hello, world!");
```

Now, spin up a local static HTTP file server.

- You have [Deno installed](https://deno.land/manual/getting_started/installation): `deno run --reload --allow-net --allow-read https://deno.land/std/http/file_server.ts .`
- You have [Node.js installed](https://nodejs.org/en/download/): `npx http-server .`
- You have [Python installed](https://www.python.org/downloads/): `python -m http.server`

Open `index.html` in your browser via the local static HTTP file server, then open the developer tools and click on the "Console" tab. You should see `Hello, world!` printed to the console.

Your JavaScript code loads and executes as soon as the browser loads the page. From here, we can write JavaScript code in `script.js` and see the results on the `index.html` page.

## How to declare a variable

In `script.js`, let's declare a variable called `name` and assign it. Then, let's print the value of `name` to the console.

```js
let name = "Ethan";
console.log("Hello, " + name);
```

Only use `let` for variables that are reassigned. Otherwise, use `const` for variables that are not reassigned. The JavaScript runtime will throw an error if you try to reassign a variable that is declared with `const`, which is useful for preventing accidental reassignments.

### Variable naming conventions

For local variables, use camelCase (e.g., `firstName`, `lastName`).

For variables that represent an array, use the plural form of the variable name (e.g., `names`, `numbers`).

For variables that represent a boolean value, use `is` as a prefix (e.g., `isReady`, `isComplete`).

Constant variables shared throughout the program should be written in `CONSTANT_CASE`.

Classes are written in `PascalCase`.

## Understand data types

All variables in JavaScript are "objects" with their own properties and methods. Some of these are considered primitive data types, which (because everything is an object) are also treated as objects but are the most basic data types in the language.

> **Note**: A literal is a notation for representing a fixed value in source code. For example, `1` is a number literal, and `"Hello, world!"` is a string literal.

### Common data types

These are data types that are featured in almost every JavaScript program.

- `undefined` is a primitive value automatically assigned to variables that have just been declared or to function arguments for which there are no passed values.
- `boolean` is a primitive value that represents a logical entity and can have two values: `true` or `false`.
- `number` is a primitive value that represents a number. JavaScript uses the 64-bit floating-point format defined by the IEEE 754 standard. You may use `_` as a separator for large numbers (e.g., `1_000_000`).
- `string` is a primitive value that represents a sequence of characters. Strings are immutable, meaning that they cannot be changed once they are created. You may use single quotes (`'`) or double quotes (`"`) to create a string literal.
- `function` is a primitive value that represents a function.
- `object` is a primitive value that represents a collection of properties. Arrays are considered objects.

```js
let name;
console.log(typeof name);

name = "Ethan";
console.log(typeof name);

const balance = 1_000_000;
console.log(typeof balance);

const isStudent = true;
console.log(typeof isStudent);
```

### Uncommon data types

These are data types that are not always featured in JavaScript programs.

- `null` is a primitive value that represents the intentional absence of any object value. `null` is used when you want to explicitly assign a variable to nothing.
- `bigint` is a primitive value that represents an integer with arbitrary precision. A `bigint` is created by appending `n` to the end of an integer literal (e.g., `1n`).
- `symbol` is a primitive value that represents a unique identifier. You may use `Symbol()` to create a symbol.

### Plain JavaScript objects

A plain old JavaScript object (POJO) is a record of unordered key-value pairs. Objects allow you to organize groups of related data. POJOs are comparable to Python dictionaries.

```js
const person = {
  name: "Ethan",
  balance: 1_000_000,
  isStudent: true,
};

console.table(person);
console.log(typeof person);
```

### Arrays

An array is a list of items. Arrays are considered objects. You may use square brackets (`[]`) to create an array literal.

```js
const catEmoji = "🐱";
const isSummer = true;
const person = { name: "Ethan", balance: 1_000_000, isStudent: true };

const values = [catEmoji, isSummer, person];
console.log(values);
```

Append an item to the end of an array using the `push` method.

```js
values.push("Hello, world!");
console.log(values);
```

Arrays are considered "object" by the `typeof` operator.

```js
console.log(typeof values);
```

Learn more about the [JavaScript data types](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures). See [`typeof` unary operator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/typeof).

> **Note**: JSDoc is a way to add type hints to JavaScript code. JSDoc is not a language but a convention for adding type hints to JavaScript code. JSDoc lives next to your JavaScript source code. TypeScript is simply a language on top of JavaScript that adds static typing by explicitly setting "type hints" to variables to satisfy the TypeScript compiler. TypeScript is a superset of JavaScript, meaning that any valid JavaScript code is also valid TypeScript code. TypeScript is compiled to JavaScript.

## Flow control

Control the flow of your program using conditional statements and loops. Let's start with conditional statements.

### Conditional statements

Conditional statements allow you to control the flow of your program based on a condition. A condition is an expression that evaluates to a `boolean` value.

#### `if` statement

```js
const age = 18;
if (age < 18) {
  console.log("You are a minor.");
} else if (age >= 18 && age < 65) {
  console.log("You are an adult.");
} else {
  console.log("You are a senior.");
}
```

#### `switch` statement

```js
const day = "Monday";
switch (day) {
  case "Monday":
  case "Tuesday":
  case "Wednesday":
  case "Thursday":
  case "Friday": {
    console.log("It's a weekday.");
    break;
  }

  case "Saturday":
  case "Sunday": {
    console.log("It's a weekend.");
    break;
  }
}
```

Learn more about [control flow](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Control_flow_and_error_handling).

### Loops

Loops allow you to execute a block of code repeatedly until a condition is met. You have three options for loops in JavaScript: `for`, `while`, and `do...while`.

#### `for` loop

In JavaScript, there are a few flavors of for-loops. The most common is the 3-part `for` loop.

```js
for (initialization; stopping condition; iteration) {
  // code to be executed
}
```

For example, let's print the numbers 0 through 9 to the console. In this example, `i` starts at 0, increments by 1, and stops when `i` is no longer less than 10. `i` is the most popular variable name for a `for` loop counter; `i` stands for "index".

```js
for (let i = 0; i < 10; i++) {
  console.log(i);
}
```

JavaScipt supports a `for...of` loop, which iterates over the values of an iterable object. This is useful for iterating over the values of an array.

```js
for (const value of iterable) {
  // code to be executed
}
```

For example, let's iterate over the values of an array.

```js
const snacks = ["🍕", "🍫", "🍬", "🍩", "🍟"];
for (const snack of snacks) {
  console.log(snack);
}
```

JavaScript also supports a `for...in` loop, which iterates over the properties of an object. This is useful for iterating over the properties of a plain JavaScript object.

```js
for (const key in object) {
  // code to be executed
}
```

For example, let's iterate over the properties of a plain JavaScript object.

```js
const person = { name: "Ethan", balance: 1_000_000, isStudent: true };
for (const key in person) {
  console.log(key, person[key]);
}
```

#### `while` loop

The `while` loop executes a block of code while a condition is true.

```js
while (condition) {
  // code to be executed
}
```

For example, let's print the numbers 0 through 9 to the console. In this example, `i` starts at 0 and increments by 1 until `i` is no longer less than 10. This is the same thing as the `for` loop example above, just in an alternate syntax.

```js
let i = 0;
while (i < 10) {
  console.log(i);
  i++;
}
```

Also, you can use a `do...while` loop, which executes a block of code at least once and then repeatedly executes the block of code while a condition is true.

```js
do {
  // code to be executed
} while (condition);
```

For example, let's print the numbers 0 through 9 to the console again. This time, the value of `i` is printed before the condition is checked (change `10` to `0` to see the difference).

```js
let i = 0;
do {
  console.log(i);
  i++;
} while (i < 10);
```

Choose the syntax that makes the most sense for the problem you're trying to solve.

## Understand variable scoping

Wrapping variables in curly braces creates a new scope. This is useful for creating blocks of code that are independent of each other.

Variables created in child scopes are not accessible in parent scopes.

```js
const name = "Ethan";
if (name === "Ethan") {
  const balance = 1_000_000;
}
console.log(balance); // ReferenceError: balance is not defined
```

## How to declare a function

Let's create a function that prints a message to the console. Functions are useful for calling the same code multiple times without duplicate code.

```js
function printGreeting() {
  console.log("Hello, world!");
}

printGreeting();
```

Let's call the function many times in a loop.

```js
for (let i = 0; i < 10; i++) {
  printGreeting();
}
```

## Understand native JavaScript APIs

JavaScript in your browser supports many APIs out of the box. It is truly mind-blowing how much you can do in JavaScript, so here is a short list to get the idea.

- [Web Storage](https://developer.mozilla.org/en-US/docs/Web/API/Web_Storage_API): Store data in your user's browser.
- [Fetch API](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API): Make network requests.
- [File System Access API](https://developer.mozilla.org/en-US/docs/Web/API/File_System_Access_API): Read and write files on your user's computer.

### Understand the DOM

The most important native JavaScript API is known as the DOM (Document Object Model). The DOM is a tree-like structure that represents the HTML of a webpage. The DOM is accessible via the `document` global variable.

```js
const paragraph = document.createElement("p");
paragraph.textContent = "Hello, world!";
document.body.appendChild(paragraph);
```

### Find all APIs on MDN

Mostly everything you need to know about JavaScript is on [MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript), a website maintained by Mozilla. This website provides comprehensive documentation for all of the APIs available in JavaScript, HTML, CSS, and more. Each API includes a supportability matrix that shows which browsers support the API.

To use MDN, Google any JavaScript API and add "mdn" to the end of your search query. For example, if you want to learn about the `Array.prototype.map()` method, Google "array map mdn". Or maybe you want to learn about the `fetch()` function, Google "fetch mdn".

## Understand how to share code between files

Let's say we want to expose `printGreeting` to other files. In order for other files to access `printGreeting`, we need to export it. The syntax for exporting any function or identifier is a prefix of `export` before the declaration.

```diff
- function printGreeting() {
+ export function printGreeting() {
  console.log("Hello, world!");
}
```

Let's add another file to our project. Create a new file called `main.js` and add the following code.

```js
import { printGreeting } from "/script.js";

printGreeting();
```

Update our `index.html` file to include the new `main.js` file.

```diff
- <script src="/script.js"></script>
+ <script type="module" src="/script.js"></script>
+ <script type="module" src="/main.js"></script>
```

## Understand ES6 syntax

ES6 is a prolific update to the JavaScript language. Introduced in 2015, ES6 added many new features to the language including arrow functions, `let` and `const`, promises, array methods, classes, import/export, `Map` and `Set`, and more.

This workshop is using the latest best practices as of Summer 2023, which is heavily influenced by ES6. Think of variable declarations and `import`/`export`.

## Understand import maps

We can use import maps to be more intentional with our import strategy. Import maps are a way to map a module specifier to a URL. This is useful for mapping a module specifier to a local file or external library via CDN.

```html
<script type="importmap">
  {
    "imports": {
      "#/": "./"
    }
  }
</script>
```

### Deno bonus

Now, since Deno is a JavaScript runtime that strives for cross-compatibility with web browsers, we can use import maps in Deno as well.

We can copy our import map into a separate `import_map.json` file and include it in the `deno run` command. Let's run the code we have written for the browser but in Deno.

```sh
deno run --import-map=import_map.json main.js
```

## Understand external JavaScript libraries

JavaScript libraries are JavaScript files written by other developers that you can use in your own projects. JavaScript libraries are useful for saving time and not reinventing the wheel.

```json
{
  "imports": {
    "canvas-confetti": "https://cdn.jsdelivr.net/npm/canvas-confetti@1.2.0/dist/confetti.module.mjs"
  }
}
```

## Exercises

Ingrain the skills you learned in today's workshop by practicing on your own. With there being so much to JavaScript, it is important to practice, encounter problems on your own, and learn how to solve them. Here are some exercise ideas you can do to practice JavaScript.

- Create a JavaScript function that calculates the quadratic formula.
- Create a JavaScript function that calculates the factorial of a number.
- Create a JavaScript function that calculates the Fibonacci sequence.
- Create a JavaScript function that calculates the sum of all numbers in an array.
- Create a JavaScript function that visualizes data by updating the DOM, such as creating a nested list of items or a table of data.

## Use cases of JavaScript

JavaScript's main use case is to make webpages interactive. JavaScript is used client-side (in browser extensions, web apps, mobile apps) and server-side (in web servers, cloud functions, etc.).

Use JavaScript to build full-stack applications more quickly by sharing code between the client and server. A common observation is that using the same language on the client and server requires less context switching and makes it easier to reason about the codebase.

## Resources

- [JavaScript on MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript)
- [JavaScript on Khan Academy](https://www.khanacademy.org/computing/computer-programming/programming)
- [Google JavaScript Style Guide](https://google.github.io/styleguide/jsguide.html)

---

5th weekly workshop (July 14th, 2023) of [Hot Open Source Software Summer hackathon](https://acmcsuf.com/hot) series hosted by [**ACM CSUF Student Chapter**](https://acmcsuf.com)'s [**Open Source Software**](https://oss.acmcsuf.com) team.
