# What is JavaScript?

JavaScript is a versatile, high-level programming language primarily used for creating interactive and dynamic content on the web. It is an essential technology of the World Wide Web, alongside HTML and CSS, and is supported by all modern web browsers. JavaScript allows developers to implement complex features on web pages, such as interactive forms, animations, and real-time updates.

# Key Features of JavaScript

- **Interpreted Language**: JavaScript is executed directly by the browser without the need for prior compilation.
- **Dynamic Typing**: Variables in JavaScript are not bound to a specific data type, allowing for flexibility in coding.
- **Event-Driven**: JavaScript can respond to user actions such as clicks, form submissions, and keyboard input.
- **Prototype-Based**: JavaScript uses prototypes for inheritance, enabling objects to inherit properties and methods from other objects.
- **Asynchronous Programming**: JavaScript supports asynchronous operations through callbacks, promises, and async/await, making it suitable for handling tasks like API calls and file reading.
- **Cross-Platform**: JavaScript runs on any device with a compatible web browser, making it highly portable.
- **Rich Standard Library**: JavaScript provides a wide range of built-in functions and objects for tasks such as manipulating the DOM, handling events, and performing mathematical operations.

# History of JavaScript

JavaScript was created by Brendan Eich in 1995 while he was working at Netscape Communications Corporation. Initially developed under the name Mocha, it was later renamed to LiveScript and finally to JavaScript. The language was designed to enable interactive web pages and has since evolved into a powerful, versatile language used both on the client-side and server-side of web development. JavaScript has undergone several standardizations, with ECMAScript being the official specification that guides its development and features.

# What problems does JavaScript solve?

JavaScript addresses several key challenges in web development:

- **Interactivity**: JavaScript enables dynamic content and interactive features on web pages, such as form validation, animations, and real-time updates.
- **Client-Side Processing**: By executing code in the browser, JavaScript reduces the need for server-side processing, leading to faster user experiences.
- **Cross-Browser Compatibility**: JavaScript provides a consistent way to implement functionality across different web browsers.
- **Asynchronous Operations**: JavaScript allows for non-blocking operations, such as fetching data from APIs without freezing the user interface.
- **Rich User Interfaces**: JavaScript frameworks and libraries, like React and Vue, help developers build complex and responsive user interfaces efficiently.
- **Server-Side Development**: With the advent of Node.js, JavaScript can also be used for server-side development, allowing developers to use a single language for both client-side and server-side code.
- **Full-Stack Development**: JavaScript enables full-stack development, where developers can build both the front-end and back-end of web applications using the same language, streamlining the development process and improving code maintainability.
- **Community and Ecosystem**: JavaScript has a large and active community, providing a wealth of libraries, frameworks, and tools that accelerate development and problem-solving.

# Before JavaScript how web interactivity was handled

Before the advent of JavaScript, web pages were largely static, and interactivity was limited. Developers relied on server-side scripting to generate dynamic content, which meant that every user action requiring a change in the web page had to involve a round trip to the server. This approach led to slower user experiences and increased server load. Some early attempts at client-side interactivity included using browser-specific technologies like Java applets, ActiveX controls, and VBScript, but these solutions were often platform-dependent and lacked the flexibility and ease of use that JavaScript eventually provided.

# Evolution of JavaScript

JavaScript has evolved significantly since its creation in 1995. Initially designed for simple client-side interactivity, it has grown into a versatile language used for both front-end and back-end development. Key milestones in its evolution include:

- **1995**: Brendan Eich creates Mocha, which is later renamed to LiveScript and finally to JavaScript.
- **1996**: JavaScript is officially supported by Netscape Navigator 2.0.
- **1997**: ECMAScript 1 is released, providing the first standardized specification for JavaScript.
- **1999**: ECMAScript 3 is released, introducing regular expressions, better string handling, and new control statements.
- **2009**: ECMAScript 5 is released, adding features like strict mode, JSON support, and improved object handling.
- **2015**: ECMAScript 6 (ES6/ES2015) is released, bringing major enhancements such as classes, modules, arrow functions, and promises.
- **2016-Present**: Annual updates to ECMAScript continue to introduce new features and improvements, keeping JavaScript modern and relevant for contemporary web development.

# What is the difference between JavaScript and ECMAScript

JavaScript and ECMAScript are closely related but not identical. JavaScript is a programming language used primarily for web development, while ECMAScript is the standardized specification that defines the core features and syntax of the language. In essence, JavaScript is an implementation of the ECMAScript standard, along with additional features provided by web browsers and other environments.

# What is JavaScript runtime environment

A JavaScript runtime environment is an environment in which JavaScript code can be executed. It provides the necessary infrastructure, including the JavaScript engine, APIs, and event loop, to run JavaScript outside of a web browser. The most common JavaScript runtime environment is Node.js, which allows developers to run JavaScript on the server side. In a web browser, the runtime environment is provided by the browser itself, which includes the JavaScript engine (like V8 in Chrome) and various Web APIs for interacting with the DOM, making network requests, and more.

# Key Components of a JavaScript Runtime Environment

- **JavaScript Engine**: The core component that executes JavaScript code. Popular engines include V8 (used in Chrome and Node.js) and SpiderMonkey (used in Firefox).
- **APIs**: Built-in functions and objects provided by the runtime environment, such as `setTimeout`, `fetch`, and `console`.
- **Event Loop**: A mechanism that handles asynchronous operations, allowing non-blocking execution of code.
- **Call Stack**: A data structure that keeps track of function calls and their execution context.
- **Callback Queue**: A queue that holds asynchronous callbacks waiting to be executed by the event loop.

- **Microtask Queue**: A queue that holds microtasks, such as promises, which are executed after the current operation completes and before the event loop continues to the next task.

## Diagram of JavaScript Runtime Environment

![JavaScript Runtime Environment Diagram](./images/javascript%20runtime%20enviroment.png)


# What is call stack

The call stack is a data structure that keeps track of function calls and their execution context in a JavaScript program. It operates on a "last in, first out" (LIFO) principle, meaning the most recently called function is executed first. When a function is called, it is pushed onto the stack, and when the function completes, it is popped off the stack. The call stack is essential for managing the execution flow of synchronous code and for handling function invocations.

# How the Call Stack Works

When a function is invoked, it is added to the top of the call stack. The JavaScript engine then executes the function's code. If the function calls another function, that new function is also added to the top of the stack. This process continues until the engine encounters a function that does not call any other functions. Once a function completes its execution, it is removed from the stack, and the engine resumes execution of the previous function on the stack. This mechanism ensures that functions are executed in the correct order and that the execution context is properly managed.

# How The call stack handle synchronous and asynchronous code

The call stack handles synchronous code directly, executing functions in the order they are called. Asynchronous code, such as `setTimeout` or `fetch` requests, is handled differently. When an asynchronous operation is encountered, its callback is registered with the appropriate API (like the Web API in browsers) and the function is removed from the call stack. Once the asynchronous operation completes, its callback is placed in the callback queue or microtask queue. The event loop then monitors the call stack and moves callbacks from the queues to the call stack when it is empty, ensuring asynchronous code is executed without blocking the main thread.

# What is callback queue and microtask queue and how they work

The callback queue is a queue that holds asynchronous callbacks waiting to be executed by the event loop. When the call stack is empty, the event loop picks the next callback from the callback queue and pushes it onto the call stack for execution.

The microtask queue is a queue that holds microtasks, such as promises, which are executed after the current operation completes and before the event loop continues to the next task. Microtasks have higher priority than callbacks in the callback queue, ensuring that promise resolutions and other microtasks are handled promptly.

## Diagram of Call Stack, Callback Queue, and Microtask Queue

![Call Stack](./images/javascript%20call%20stack.png)


# Adding JavaScript to HTML

To add JavaScript to an HTML file, you can use the `<script>` tag. There are two main ways to include JavaScript:

1. **Internal JavaScript**: You can include JavaScript directly within an HTML file using the `<script>` tag. For example:

```html
<!DOCTYPE html>
<html>
    <head>
        <title>Page Title</title>
        <script>
            // Your JavaScript code here
        </script>
    </head>
    <body>
        <h1>Hello, World!</h1>
    </body>
</html>
```

2. **External JavaScript**: You can include JavaScript from an external file using the `<script>` tag with the `src` attribute. For example:

```html
<!DOCTYPE html>
<html>
    <head>
        <title>Page Title</title>
        <script src="script.js"></script>
    </head>
    <body>
        <h1>Hello, World!</h1>
    </body>
</html>
```

# defer and async attributes for script tag

The `defer` and `async` attributes are used to control the loading and execution of external JavaScript files.

- **defer**: The `defer` attribute tells the browser to download the script in the background and execute it after the HTML document has been completely parsed. Deferred scripts are executed in the order they appear in the document.

```html
<script src="script.js" defer></script>
```

- **async**: The `async` attribute tells the browser to download the script in the background and execute it as soon as it is available, without waiting for the HTML document to be completely parsed. Asynchronous scripts are executed as soon as they are ready, which may not be in the order they appear in the document.

```html
<script src="script.js" async></script>
```

# What is `use strict`

The `"use strict"` directive was introduced in ECMAScript 5 and is used to enable strict mode in JavaScript. Strict mode helps catch common coding mistakes and "unsafe" actions such as defining global variables unintentionally.

To enable strict mode for an entire script, you can place `"use strict";` at the top of your JavaScript file:

```javascript
"use strict";
// Your JavaScript code here
```

You can also enable strict mode for individual functions:

```javascript
function myFunction() {
    "use strict";
    // Your JavaScript code here
}
```

# Variables in JavaScript

In JavaScript, variables are used to store data values. You can declare variables using `var`, `let`, or `const`.

- **var**: Var is used to declare a variable, and it has function scope. Variables declared with `var` are hoisted to the top of their containing function and can be re-declared and updated within the same scope.

- **Let**: Let is also used to declare a variable, but it has block scope. Variables declared with `let` are not hoisted to the top of their containing block because of the temporal dead zone. They can be updated within the same block but cannot be re-declared.

- **Const**: Const is used to declare a constant variable, which means its value cannot be changed once assigned. Like `let`, `const` has block scope and is not hoisted to the top of its containing block because of the temporal dead zone.

```javascript
console.log(a); // undefined due to hoisting

var a = 10;
console.log(a);

let b = 20;
b = 40;
let b = 50; // This will cause an error because `b` has already been declared in the same block
console.log(b);

const c = 50;
c = 60; // This will cause an error because `c` is a constant
console.log(c);
```

# Variable naming

In JavaScript, variable names must follow certain rules:

- Variable names can include letters, digits, underscores, and dollar signs.
- Variable names must begin with a letter, underscore, or dollar sign.
- Variable names are case-sensitive.
- Reserved words (like `let`, `const`, `var`, `function`, etc.) cannot be used as variable names.

Examples:

```javascript
let myVariable = 10;
const $myConstant = 20;
var _myVar = 30;
```

# Data Types in JavaScript

JavaScript has several data types, which can be categorized into two main types: primitive and non-primitive (reference) types.

| **Primitive Types** | **non-primitive (Reference) Types** |
|-------------------|------------------------------------|
| `string`          | `object`                           |
| `number`          | `array`                            |
| `boolean`         | `function`                         |
| `null`            |                                    |
| `undefined`       |                                    |
| `symbol`          |                                    |

# How to see type of a variable

In JavaScript, you can use the `typeof` operator to check the type of a variable.

Example:

```javascript
let myVar = 42;
console.log(typeof myVar); // Output: "number"

let myString = "Hello";
console.log(typeof myString); // Output: "string"

let myObj = { name: "Alice" };
console.log(typeof myObj); // Output: "object"
```

# What is the difference between reference type and value type

In JavaScript, the difference between reference type and value type lies in how they are stored and accessed in memory.

- **Value Type**: Primitive types (`string`, `number`, `boolean`, `null`, `undefined`, `symbol`) are value types. When you assign a value type to a variable, the actual value is stored in the variable. When you copy the variable to another variable, a new copy of the value is created.

- **Reference Type**: Non-primitive types (`object`, `array`, `function`) are reference types. When you assign a reference type to a variable, the variable stores a reference (or memory address) to the actual object. When you copy the variable to another variable, both variables refer to the same object in memory.

Example:

```javascript
let obj1 = { name: "Alice" };
let obj2 = obj1;
obj2.name = "Bob";
console.log(obj1.name); // Output: "Bob" because both obj1 and obj2 refer to the same object
```

# What is Dynamic typing

JavaScript is a dynamically typed language, which means that the type of a variable is determined at runtime and can change as the program executes.

Example:

```javascript
let myVar = 42; // myVar is a number
console.log(typeof myVar); // Output: "number"

myVar = "Hello"; // myVar is now a string
console.log(typeof myVar); // Output: "string"
```

# What is Type Coercion

Type coercion in JavaScript refers to the automatic or implicit conversion of values from one data type to another. JavaScript often performs type coercion when it encounters operations involving different data types.

Example:

```javascript
let result = "5" - 2; // The string "5" is coerced to a number
console.log(result); // Output: 3

let strResult = "5" + 2; // The number 2 is coerced to a string
console.log(strResult); // Output: "52"
```

# Which all operators in JavaScript involve type coercion

In JavaScript, type coercion can occur with various operators, especially when dealing with different data types. Common operators that involve type coercion include:

- Arithmetic operators (`+`, `-`, `*`, `/`, `%`)
- Comparison operators (`==`, `!=`, `<`, `>`, `<=`, `>=`)
- Logical operators (`&&`, `||`, `!`)
- Conditional (ternary) operator (`condition ? expr1 : expr2`)
- Bitwise operators (`&`, `|`, `^`, `~`, `<<`, `>>`, `>>>`)
- Assignment operators (`=`, `+=`, `-=`, `*=`, `/=`, `%=`)
- Unary operators (`+`, `-`, `!`, `typeof`, `void`)

```javascript
// 2 examples of Arithmetic operators involving type coercion
let a = "5";
let b = 2;
let result = a - b; // The string "5" is coerced to a number
console.log(result); // Output: 3

let strResult = a + b; // The number 2 is coerced to a string
console.log(strResult); // Output: "52"


// 2 examples of Comparison operators involving type coercion
let x = "10";
let y = 5;
console.log(x > y); // The string "10" is coerced to a number, Output: true
console.log(x == y); // The string "10" is coerced to a number, Output: false

// 2 examples of Logical operators involving type coercion
let p = "true";
let q = false;
console.log(p && q); // The string "true" is coerced to a boolean, Output: false
console.log(p || q); // The string "true" is coerced to a boolean, Output: true

// 2 examples of Bitwise operators involving type coercion
let m = "5";
let n = 3;
console.log(m & n); // The string "5" is coerced to a number, Output: 1
console.log(m | n); // The string "5" is coerced to a number, Output: 7

// 2 examples of Assignment operators involving type coercion
let c = "5";
c += 2; // The number 2 is coerced to a string
console.log(c); // Output: "52"

let d = "10";
d -= 3; // The string "10" is coerced to a number
console.log(d); // Output: 7

// 2 examples of Unary operators involving type coercion
let e = "5";
console.log(+e); // The string "5" is coerced to a number, Output: 5
console.log(!e); // The string "5" is coerced to a boolean, Output: false

```

# How to Avoid Type Coercion in JavaScript

To avoid type coercion in JavaScript, you can use strict equality operators, explicit type conversion, and be mindful of the types of values you are working with.

## Use Strict Equality Operators
Use `===` and `!==` instead of `==` and `!=` to avoid implicit type conversion.

```javascript
let a = "5";
let b = 5;
console.log(a === b); // Output: false
console.log(a !== b); // Output: true
```

## Explicit Type Conversion
Convert values to the desired type explicitly using functions like `Number()`, `String()`, or `Boolean()`.

```javascript
let a = "5";
let b = 2;
let result = Number(a) - b; // Explicitly convert "5" to a number
console.log(result); // Output: 3

let strResult = String(b) + a; // Explicitly convert 2 to a string
console.log(strResult); // Output: "25"
```


# Truthy and Falsy Values in JavaScript

In JavaScript, values can be either "truthy" or "falsy" when evaluated in a boolean context.

| **Truthy Values** | **Falsy Values** |
|-----------------|----------------|
| `true`          | `false`        |
| Non-zero numbers| `0`            |
| Non-empty strings| `""`          |
| `{}`         | `null`         |
| `[]`       | `undefined`    |
| Functions       | `NaN`          |


# How to Check for Truthy and Falsy Values in JavaScript

You can check if a value is truthy or falsy by using it in a conditional statement or by explicitly converting it to a boolean using the `Boolean()` function.

```javascript
let value1 = "Hello";
if (value1) {
    console.log("value1 is truthy"); // Output: value1 is truthy
}

let value2 = 0;
if (!value2) {
    console.log("value2 is falsy"); // Output: value2 is falsy
}

console.log(Boolean("Hello")); // Output: true
console.log(Boolean(0));       // Output: false
```

# Operators in JavaScript
JavaScript provides various types of operators to perform operations on values and variables. These include arithmetic, comparison, logical, assignment, and more.

## Arithmetic Operators
Arithmetic operators are used to perform mathematical operations on numbers.

| **Operator** | **Description**           | **Example**       |
|----------|---------------------|---------------|
| `+`      | Addition             | `5 + 2`       |
| `-`      | Subtraction          | `5 - 2`       |
| `*`      | Multiplication       | `5 * 2`       |
| `/`      | Division             | `5 / 2`       |
| `%`      | Modulus (Remainder)  | `5 % 2`       |
| `**`     | Exponentiation       | `5 ** 2`      |

## Assignment Operators
Assignment operators are used to assign values to variables.

| **Operator** | **Description**           | **Example**       |
|----------|---------------------|---------------|
| `=`      | Assignment           | `x = 5`       |
| `+=`     | Addition assignment  | `x += 2`      |
| `-=`     | Subtraction assignment | `x -= 2`    |
| `*=`     | Multiplication assignment | `x *= 2` |
| `/=`     | Division assignment  | `x /= 2`      |
| `%=`     | Modulus assignment   | `x %= 2`      |
| `**=`    | Exponentiation assignment | `x **= 2` |

## Comparison Operators

Comparison operators are used to compare values and return a boolean result.

| **Operator** | **Description**           | **Example**       |
|----------|---------------------|---------------|
| `==`     | Equal to             | `5 == 5`       |
| `===`    | Strict equal to      | `5 === 5`      |
| `!=`     | Not equal to         | `5 != 2`       |
| `!==`    | Strict not equal to  | `5 !== 2`      |
| `>`      | Greater than         | `5 > 2`        |
| `<`      | Less than            | `5 < 2`        |
| `>=`     | Greater than or equal to | `5 >= 2`  |
| `<=`     | Less than or equal to    | `5 <= 2`  |

## Logical Operators

Logical operators are used to combine or invert boolean values.

| **Operator** | **Description**           | **Example**       |
|----------|---------------------|---------------|
| `&&`     | Logical AND           | `true && false`       |
| `||`     | Logical OR            | `true || false`       |
| `!`      | Logical NOT           | `!true`        |

## Conditional (Ternary) Operator

The conditional (ternary) operator is used to evaluate a condition and return one of two values based on the result.

```syntax
condition ? if condition is true : if condition is false
```

```javascript
let result = true ? 'Yes' : 'No';
console.log(result); // Output: Yes
```

## Unary Operators

Unary operators are used to perform operations on a single operand.

| **Operator** | **Description**           | **Example**       |
|----------|---------------------|---------------|
| `+`      | Unary plus (converts to number) | `+ '5'`       |
| `-`      | Unary minus (negates the value) | `-5`       |
| `++`     | Increment (adds 1)    | `x++`       |
| `--`     | Decrement (subtracts 1) | `x--`       |
| `!`      | Logical NOT           | `!true`        |

## Increment and Decrement Operators

Increment and decrement operators are used to increase or decrease the value of a variable by 1.

| **Operator** | **Description**           | **Example**       |
|----------|---------------------|---------------|
| `++`     | Increment (adds 1)    | `x++`       |
| `--`     | Decrement (subtracts 1) | `x--`       |

## Operator Precedence

Operator precedence determines the order in which operators are evaluated in an expression. Operators with higher precedence are evaluated before operators with lower precedence.

| **Operator** | **Description**           | **Example**       |
|----------|---------------------|---------------|
| `()`     | Parentheses (highest precedence) | `(2 + 3) * 4`       |
| `**`     | Exponentiation         | `2 ** 3`       |
| `*` `/` `%` | Multiplication, Division, Modulus | `2 * 3 / 4 % 5` |
| `+` `-` | Addition, Subtraction  | `2 + 3 - 4`   |
| `=` `+=` `-=` `*=` `/=` `%=` `**=` | Assignment operators | `x = 5`       |
| `&&` `||` `!` | Logical operators | `true && false` |
| `? :` | Conditional (ternary) operator | `true ? 'Yes' : 'No'` |

```javascript
// Example demonstrating operator precedence
let result = 2 + 3 * 4; // Multiplication has higher precedence than addition
console.log(result); // Output: 14

result = (2 + 3) * 4; // Parentheses have the highest precedence
console.log(result); // Output: 20
```

# What is Nullish Coalescing 
The nullish coalescing operator (`??`) is used to provide a default value when dealing with `null` or `undefined`.

```javascript
let value = null;
let result = value ?? 'Default';
console.log(result); // Output: Default
```

# What is Optional Chaining

The optional chaining operator (`?.`) is used to safely access deeply nested properties of an object without having to check if each reference in the chain is valid.

```javascript
let user = {
  name: 'John',
  address: {
    city: 'New York'
  }
};

console.log(user?.address?.city); // Output: New York
console.log(user?.contact?.phone); // Output: undefined
```

# Control Flow

Control flow in JavaScript refers to the order in which the code is executed. JavaScript provides several control flow statements to manage the execution of code, including conditional statements and loops.

## if else statements

The `if` statement is used to execute a block of code if a specified condition is true. The `else` statement can be used to execute a block of code if the condition is false.

```syntax
if (condition) {
  // code to be executed if condition is true
} else {
  // code to be executed if condition is false
}
```

```javascript
// simple if else example
let number = 10;
if (number > 5) {
  console.log('Number is greater than 5');
} else {
  console.log('Number is 5 or less');
}

// nested if else example
let number2 = 15;
if (number2 > 10) {
  if (number2 > 20) {
    console.log('Number is greater than 20');
  } else {
    console.log('Number is greater than 10 but 20 or less');
  }
} else {
  console.log('Number is 10 or less');
}

// multiple conditions example
let number3 = 25;
if (number3 > 20) {
  console.log('Number is greater than 20');
} else if (number3 > 10) {
  console.log('Number is greater than 10 but 20 or less');
} else {
  console.log('Number is 10 or less');
}
```

## switch case statements

The `switch` statement is used to perform different actions based on different conditions. It is often used as an alternative to multiple `if else` statements.

```syntax
switch (expression) {
  case value1:
    // code to be executed if expression === value1
    break;
  case value2:
    // code to be executed if expression === value2
    break;
  // you can have any number of case statements
  default:
    // code to be executed if expression doesn't match any case
}
```

```javascript
let day = 3;
switch (day) {
  case 1:
    console.log('Monday');
    break;
  case 2:
    console.log('Tuesday');
    break;
  case 3:
    console.log('Wednesday');
    break;
  case 4:
    console.log('Thursday');
    break;
  case 5:
    console.log('Friday');
    break;
  case 6:
    console.log('Saturday');
    break;
  case 7:
    console.log('Sunday');
    break;
  default:
    console.log('Invalid day');
}
```

## for loop

The `for` loop is used to execute a block of code a specific number of times. It consists of three parts: the initialization, the condition, and the increment/decrement.

```syntax
for (initialization; condition; increment/decrement) {
  // code to be executed in each iteration
}
```

```javascript
// simple for loop example
for (let i = 0; i < 5; i++) {
  console.log('Iteration number: ' + i);
}
```

## while loop

The `while` loop is used to execute a block of code as long as a specified condition is true.

```syntax
while (condition) {
  // code to be executed in each iteration
}
```

```javascript
// simple while loop example
let i = 0;
while (i < 5) {
  console.log('Iteration number: ' + i);
  i++;
}
```

## do...while loop

The `do...while` loop is similar to the `while` loop, but it guarantees that the block of code will be executed at least once, even if the condition is false.

```syntax
do {
  // code to be executed in each iteration
} while (condition);
```

```javascript
// simple do...while loop example
let i = 0;
do {
  console.log('Iteration number: ' + i);
  i++;
} while (i < 5);
```

## break and continue statements

The `break` statement is used to exit a loop prematurely, while the `continue` statement is used to skip the current iteration and move to the next one.

```javascript
// break example
for (let i = 0; i < 5; i++) {
  if (i === 3) {
    break; // exit the loop when i is 3
  }
  console.log('Iteration number: ' + i);
}

// continue example
for (let i = 0; i < 5; i++) {
  if (i === 3) {
    continue; // skip the iteration when i is 3
  }
  console.log('Iteration number: ' + i);
}
```

# Functions

Functions are blocks of code designed to perform a particular task. They are executed when called.

## What problem do functions solve?

Functions help in breaking down complex problems into smaller, manageable pieces. They allow code reuse, improve readability, and make maintenance easier. Instead of writing the same code multiple times, you can define a function once and call it whenever needed.

## Function declaration

A function declaration defines a named function. It consists of the `function` keyword, followed by the function name, a list of parameters enclosed in parentheses, and a block of code enclosed in curly braces.

```syntax
function functionName(parameters) {
  // code to be executed when the function is called
}
```

```javascript
// function declaration example
function greet(name) {
  console.log('Hello, ' + name + '!');
}

greet('Alice');
```

## Function expression

A function expression defines a function as part of an expression. It can be anonymous (without a name) and is often assigned to a variable.

```syntax
const functionName = function(parameters) {
  // code to be executed when the function is called
}
```

```javascript
// function expression example
const greet = function(name) {
  console.log('Hello, ' + name + '!');
};

greet('Alice');
```

## Anonymous function

An anonymous function is a function without a name. It is often used in function expressions or as an argument to other functions.

```syntax
const functionName = function(parameters) {
  // code to be executed when the function is called
}
```

```javascript
// anonymous function example
const greet = function(name) {
  console.log('Hello, ' + name + '!');
};

greet('Alice');
```

## Arrow function

An arrow function is a concise way to write functions using the `=>` syntax. It is often used for shorter functions and callbacks.

```syntax
const functionName = (parameters) => {
  // code to be executed when the function is called
}
```

```javascript
// arrow function example
const greet = (name) => {
  console.log('Hello, ' + name + '!');
};

greet('Alice');
```

## Callback function

A callback function is a function passed as an argument to another function. It is executed after the completion of the outer function, allowing asynchronous operations and event handling.

```syntax
function outerFunction(callback) {
  // code to be executed
  callback();
}
```

```javascript
// callback function example
function greet(name, callback) {
  console.log('Hello, ' + name + '!');
  callback();
}

function sayGoodbye() {
  console.log('Goodbye!');
}

greet('Alice', sayGoodbye);
```

## Higher-order function

A higher-order function is a function that takes one or more functions as arguments or returns a function as its result. It allows for more flexible and reusable code.

```syntax
function higherOrderFunction(callback) {
  // code to be executed
  return function() {
    // code to be executed
    callback();
  };
}
```

```javascript
// higher-order function example
function greet(name) {
  console.log('Hello, ' + name + '!');
}

function higherOrderFunction(callback) {
  return function(name) {
    console.log('Before callback');
    callback(name);
    console.log('After callback');
  };
}

const enhancedGreet = higherOrderFunction(greet);
enhancedGreet('Alice');
```

## First-class function

A first-class function is a function that can be treated like any other value. It can be assigned to a variable, passed as an argument to other functions, and returned from functions.

```syntax
const functionName = function(parameters) {
  // code to be executed when the function is called
}
```

```javascript
// first-class function example
const greet = function(name) {
  console.log('Hello, ' + name + '!');
};

function executeFunction(fn, value) {
  fn(value);
}

executeFunction(greet, 'Alice');
```

## Immediately Invoked Function Expression (IIFE)

An Immediately Invoked Function Expression (IIFE) is a function that is defined and executed immediately after its creation. It is commonly used to create a local scope and avoid polluting the global namespace.

```syntax
(function() {
  // code to be executed immediately
})();
```

```javascript
// IIFE example
(function() {
  console.log('This function is executed immediately!');
})();
```

## Pure function

A pure function is a function that always produces the same output for the same input and has no side effects. It does not modify any external state and relies solely on its input parameters.

```syntax
function pureFunction(parameters) {
  // code that does not modify external state
  return result;
}
```

```javascript
// pure function example
function add(a, b) {
  return a + b;
}

console.log(add(2, 3)); // 5
console.log(add(2, 3)); // 5 (same output for same input)
```

## Function parameters, default parameters, and rest parameters

Function parameters allow you to pass values into a function. Default parameters provide default values for function parameters if no value is passed. Rest parameters allow you to represent an indefinite number of arguments as an array.

```syntax
// default parameters
function greet(name = 'Guest') {
  console.log('Hello, ' + name + '!');
}

// rest parameters
function sum(...numbers) {
  return numbers.reduce((total, num) => total + num, 0);
}
```

```javascript
// function parameters example
function greet(name) {
  console.log('Hello, ' + name + '!');
}

greet('Alice'); // Hello, Alice!

// default parameters example
function greetWithDefault(name = 'Guest') {
  console.log('Hello, ' + name + '!');
}

greetWithDefault(); // Hello, Guest!

// rest parameters example
function sumAll(...numbers) {
  return numbers.reduce((total, num) => total + num, 0);
}

console.log(sumAll(1, 2, 3, 4)); // 10
```

## Function arguments

Function arguments are the values passed to a function when it is called. They are assigned to the corresponding function parameters.

```syntax
function functionName(parameter1, parameter2) {
  // code to be executed
}

functionName(argument1, argument2);
```

```javascript
// function arguments example
function greet(name) {
  console.log('Hello, ' + name + '!');
}

greet('Alice'); // Hello, Alice!
```

## Function Return Values

A function return value is the value that a function produces and returns to the caller using the `return` statement. If a function does not have a `return` statement, it returns `undefined` by default.

```syntax
function functionName(parameters) {
  // code to be executed
  return result;
}
```

```javascript
// function return value example
function add(a, b) {
  return a + b;
}

const sum = add(2, 3);
console.log(sum); // 5
```

## Why there are so many ways to define functions

JavaScript provides multiple ways to define functions, including function declarations, function expressions, and arrow functions. Each has its own use cases and advantages.

| **Function Type** | **Use Case** | **Advantages** |
|------------------|--------------|----------------|
| Function Declaration | When you want to define a function with a name that can be called before its definition (hoisting) | Easy to read and understand, hoisted |
| Function Expression | When you want to define a function as part of an expression, often assigned to a variable | Can be anonymous, not hoisted |
| Arrow Function | When you want a concise syntax and lexical `this` binding | Shorter syntax, does not have its own `this` |


## What are the side effects of functions

A side effect is any observable change that occurs outside the function's scope as a result of executing the function. Common side effects include modifying global variables, changing the state of objects, performing I/O operations, and interacting with the DOM.

```javascript
// side effect example
let counter = 0;

function incrementCounter() {
  counter++; // modifies a global variable, causing a side effect
}

incrementCounter();
console.log(counter); // 1
```

## Function composition

Function composition is the process of combining two or more functions to create a new function. The output of one function becomes the input of the next function.

```javascript
// function composition example
function add(a, b) {
  return a + b;
}

function square(x) {
  return x * x;
}

const result = square(add(2, 3)); // square(add(2, 3)) => square(5) => 25
console.log(result); // 25
```

# Scopes in JavaScript

In JavaScript, scope refers to the accessibility of variables, functions, and objects in different parts of the code. There are many types of scope, including global scope, function scope, and block scope.

## Global Scope

Global scope refers to variables that are accessible from anywhere in the code. Variables declared outside of any function or block are in the global scope.

```javascript
// global scope example
let globalVariable = 'I am global';

function printGlobalVariable() {
  console.log(globalVariable); // accessible here
}

printGlobalVariable();
console.log(globalVariable); // accessible here as well
```

## Function Scope

Function scope refers to variables that are accessible only within the function in which they are declared. Variables declared inside a function are not accessible from outside the function.

```javascript
// function scope example
function printLocalVariable() {
  let localVariable = 'I am local';
  console.log(localVariable); // accessible here
}

printLocalVariable();
console.log(localVariable); // ReferenceError: localVariable is not defined
```

## Block Scope

Block scope refers to variables that are accessible only within the block in which they are declared. Variables declared with `let` or `const` inside a block are not accessible from outside the block.

```javascript
// block scope example
{
  let blockVariable = 'I am block scoped';
  console.log(blockVariable); // accessible here
}

console.log(blockVariable); // ReferenceError: blockVariable is not defined
```

## Lexical Scope

Lexical scope refers to the fact that in JavaScript, the scope of a variable is determined by its position in the source code. Inner functions have access to variables declared in their outer functions.

```javascript
// lexical scope example
function outerFunction() {
  let outerVariable = 'I am from outer function';

  function innerFunction() {
    console.log(outerVariable); // accessible here
  }

  innerFunction();
}

outerFunction();
console.log(outerVariable); // ReferenceError: outerVariable is not defined
```

## Scope chain

Scope chain refers to the hierarchy of scopes that determines the accessibility of variables. When a variable is referenced, JavaScript looks for it in the current scope, then in the outer scope, and so on, until it reaches the global scope.

```javascript
// scope chain example
let globalVar = 'I am global';

function outerFunction() {
  let outerVar = 'I am from outer function';

  function innerFunction() {
    let innerVar = 'I am from inner function';
    console.log(innerVar); // accessible here
    console.log(outerVar); // accessible here
    console.log(globalVar); // accessible here
  }

  innerFunction();
  console.log(outerVar); // accessible here
  console.log(globalVar); // accessible here
}

outerFunction();
console.log(globalVar); // accessible here
console.log(outerVar); // ReferenceError: outerVar is not defined
console.log(innerVar); // ReferenceError: innerVar is not defined
```

## Closures

A closure is a function that has access to its own scope, the scope of the outer function, and the global scope. Closures are created whenever a function is defined inside another function.

```javascript
// closure example
function outerFunction() {
  let outerVariable = 'I am from outer function';

  function innerFunction() {
    console.log(outerVariable); // accessible here due to closure
  }

  return innerFunction;
}

const closureFunction = outerFunction();
closureFunction(); // logs 'I am from outer function'
```

## What is Variable shadowing

Variable shadowing occurs when a variable declared within a certain scope (e.g., a function) has the same name as a variable declared in an outer scope. The inner variable "shadows" the outer variable, making the outer variable inaccessible within the inner scope.

```javascript
// variable shadowing example
let shadowedVar = 'I am global';

function exampleFunction() {
  let shadowedVar = 'I am local';
  console.log(shadowedVar); // logs 'I am local'
}

exampleFunction();
console.log(shadowedVar); // logs 'I am global'
```

# Arrays

Arrays are used to store multiple values in a single variable. They are ordered collections of elements, and each element can be accessed using its index.

## What problem do arrays solve?

Before arrays, if you wanted to store multiple values, you would have to create separate variables for each value. This becomes cumbersome and inefficient as the number of values increases. Arrays solve this problem by allowing you to store multiple values in a single variable and access them using an index.

## How to create arrays

You can create arrays using square brackets `[]` and separate the elements with commas.

```javascript
// creating an array
let fruits = ['apple', 'banana', 'cherry'];
console.log(fruits); // logs ['apple', 'banana', 'cherry']
```

## How to access array elements

You can access array elements using their index, which starts from 0.

```javascript
let fruits = ['apple', 'banana', 'cherry'];
console.log(fruits[0]); // logs 'apple'
console.log(fruits[1]); // logs 'banana'
console.log(fruits[2]); // logs 'cherry'
```

## How to modify array elements

You can modify array elements by accessing them using their index and assigning a new value.

```javascript
let fruits = ['apple', 'banana', 'cherry'];
fruits[1] = 'blueberry';
console.log(fruits); // logs ['apple', 'blueberry', 'cherry']
```

## How to check the length of an array

You can check the number of elements in an array using the `length` property.

```javascript
let fruits = ['apple', 'banana', 'cherry'];
console.log(fruits.length); // logs 3
```

## How to create nested arrays

You can create nested arrays (arrays within arrays) to represent more complex data structures.

```javascript
let matrix = [
  [1, 2, 3],
  [4, 5, 6],
  [7, 8, 9]
];
console.log(matrix);
console.log(matrix[0][0]); // logs 1
console.log(matrix[1][1]); // logs 5
console.log(matrix[2][2]); // logs 9
```

## How to iterate over arrays

You can iterate over arrays using loops, such as the `for` loop or the `for...of` loop.

```javascript
let fruits = ['apple', 'banana', 'cherry'];

// using a for loop
for (let i = 0; i < fruits.length; i++) {
  console.log(fruits[i]);
}

// using a for...of loop
for (let fruit of fruits) {
  console.log(fruit);
}
```

## Array Methods
|**Array Method**|**Its Work**|
|---|---|
|`push()`|Adds one or more elements to the end of an array.|
|`pop()`|Removes the last element from an array.|
|`shift()`|Removes the first element from an array.|
|`unshift()`|Adds one or more elements to the beginning of an array.|
|`indexOf()`|Returns the first index at which a given element can be found, or -1 if it is not present.|
|`includes()`|Checks if an array contains a certain element, returns `true` or `false`.|
|`splice()`|Adds or removes elements from an array at a specified index.|
|`slice()`|Returns a shallow copy of a portion of an array into a new array.|
|`forEach()`|Executes a provided function once for each array element.|
|`map()`|Creates a new array with the results of calling a provided function on every element.|
|`filter()`|Creates a new array with all elements that pass the test implemented by the provided function.|
|`reduce()`|Applies a function against an accumulator and each element in the array to reduce it to a single value.|
|`find()`|Returns the first element in the array that satisfies the provided testing function, or `undefined` if no such element is found.|
|`findIndex()`|Returns the index of the first element in the array that satisfies the provided testing function, or -1 if no such element is found.|
|`every()`|Checks if all elements in the array pass the test implemented by the provided function, returns `true` or `false`.|
|`some()`|Checks if at least one element in the array passes the test implemented by the provided function, returns `true` or `false`.|
|`concat()`|Merges two or more arrays into a new array.|
|`join()`|Joins all elements of an array into a string.|
|`reverse()`|Reverses the order of the elements in an array.|
|`sort()`|Sorts the elements of an array in place and returns the sorted array.|
|`flat()`|Creates a new array with all sub-array elements concatenated into it recursively up to the specified depth.|
|`flatMap()`|First maps each element using a mapping function, then flattens the result into a new array.|
|`findLast()`|Returns the last element in the array that satisfies the provided testing function, or `undefined` if no such element is found.|
|`findLastIndex()`|Returns the index of the last element in the array that satisfies the provided testing function, or -1 if no such element is found.|
|`at()`|Returns the element at the specified index, allowing for negative integers to count back from the last item in the array.|

## What is the use of Array.from()?

`Array.from()` is used to create a new array instance from an array-like or iterable object. It allows you to convert objects such as NodeLists, Sets, or strings into arrays.

```javascript
// Example with a string
let str = 'hello';
let arr = Array.from(str);
console.log(arr); // Output: ['h', 'e', 'l', 'l', 'o']

// Example with a Set
let set = new Set([1, 2, 3]);
let arrFromSet = Array.from(set);
console.log(arrFromSet); // Output: [1, 2, 3]
```

## What is the use of Array.isArray()?

`Array.isArray()` is used to determine whether a given value is an array. It returns `true` if the value is an array, and `false` otherwise.

```javascript
let arr = [1, 2, 3];
console.log(Array.isArray(arr)); // Output: true

let notArr = { a: 1 };
console.log(Array.isArray(notArr)); // Output: false
```

## What is the use of Array.of()?

`Array.of()` is used to create a new array instance with a variable number of arguments, regardless of the number or type of the arguments.

```javascript
let arr = Array.of(1, 2, 3);
console.log(arr); // Output: [1, 2, 3]

let singleElementArray = Array.of(5);
console.log(singleElementArray); // Output: [5]
```

# Objects

Objects in JavaScript are collections of key-value pairs. They are used to store and manage data in a structured way. Each key (also called a property) is a string, and each value can be of any data type, including other objects or functions.

## What problem do objects solve?

Objects solve the problem of organizing and managing related data in a structured way. Instead of having multiple separate variables, you can group related data together using key-value pairs within an object. This makes it easier to access, modify, and manage the data as a single entity.

## How to create an object?

You can create an object in JavaScript using object literal syntax or the `Object` constructor.

### Using object literal syntax
```javascript
let person = {
  name: 'John',
  age: 30,
  greet: function() {
    console.log('Hello!');
  }
};
console.log(person.name); // Output: John
person.greet(); // Output: Hello!
```

### Using the `Object` constructor
```javascript
let person = new Object();
person.name = 'John';
person.age = 30;
person.greet = function() {
  console.log('Hello!');
};
console.log(person.name); // Output: John
person.greet(); // Output: Hello!
```

## How to access object properties?

You can access object properties using dot notation or bracket notation.

### Using dot notation
```javascript
let person = {
  name: 'John',
  age: 30
};
console.log(person.name); // Output: John
console.log(person.age); // Output: 30
```

### Using bracket notation
```javascript
let person = {
  name: 'John',
  age: 30
};
console.log(person['name']); // Output: John
console.log(person['age']); // Output: 30
```

## How to modify object properties?

You can modify object properties using dot notation or bracket notation.

### Using dot notation
```javascript
let person = {
  name: 'John',
  age: 30
};
person.name = 'Jane';
person.age = 25;
console.log(person.name); // Output: Jane
console.log(person.age); // Output: 25
```

### Using bracket notation
```javascript
let person = {
  name: 'John',
  age: 30
};
person['name'] = 'Jane';
person['age'] = 25;
console.log(person['name']); // Output: Jane
console.log(person['age']); // Output: 25
```

## How to delete object properties?

You can delete object properties using the `delete` operator.

### Using dot notation
```javascript
let person = {
  name: 'John',
  age: 30
};
delete person.name;
console.log(person.name); // Output: undefined
```

### Using bracket notation
```javascript
let person = {
  name: 'John',
  age: 30
};
delete person['age'];
console.log(person['age']); // Output: undefined
```

## How to check if an object has a property?

You can check if an object has a property using the `in` operator or the `hasOwnProperty` method.

### Using the `in` operator
```javascript
let person = {
  name: 'John',
  age: 30
};
console.log('name' in person); // Output: true
console.log('gender' in person); // Output: false
```

### Using the `hasOwnProperty` method
```javascript
let person = {
  name: 'John',
  age: 30
};
console.log(person.hasOwnProperty('name')); // Output: true
console.log(person.hasOwnProperty('gender')); // Output: false
```

## How to iterate over object properties?

You can iterate over object properties using the `for...in` loop.

### Using the `for...in` loop
```javascript
let person = {
  name: 'John',
  age: 30
};
for (let key in person) {
  console.log(key + ': ' + person[key]);
}
// Output:
// name: John
// age: 30
```

## How to merge objects?

You can merge objects using the `Object.assign` method or the spread operator.

### Using the `Object.assign` method
```javascript
let person = {
  name: 'John',
  age: 30
};
let address = {
  city: 'New York',
  country: 'USA'
};
let merged = Object.assign({}, person, address);
console.log(merged);
// Output:
// { name: 'John', age: 30, city: 'New York', country: 'USA' }
```

### Using the spread operator
```javascript
let person = {
  name: 'John',
  age: 30
};
let address = {
  city: 'New York',
  country: 'USA'
};
let merged = { ...person, ...address };
console.log(merged);
// Output:
// { name: 'John', age: 30, city: 'New York', country: 'USA' }
```

## How to get object keys and values?

You can get object keys and values using the `Object.keys` and `Object.values` methods.

### Using the `Object.keys` method
```javascript
let person = {
  name: 'John',
  age: 30
};
console.log(Object.keys(person));
// Output:
// ['name', 'age']
```

### Using the `Object.values` method
```javascript
let person = {
  name: 'John',
  age: 30
};
console.log(Object.values(person));
// Output:
// ['John', 30]
```

## How to get object entries?

You can get object entries using the `Object.entries` method.

### Using the `Object.entries` method
```javascript
let person = {
  name: 'John',
  age: 30
};
console.log(Object.entries(person));
// Output:
// [['name', 'John'], ['age', 30]]
```

## How to create nested objects?

You can create nested objects by defining an object within another object.

### Example of nested objects
```javascript
let person = {
  name: 'John',
  age: 30,
  address: {
    city: 'New York',
    country: 'USA'
  }
};
console.log(person);
// Output:
// {
//   name: 'John',
//   age: 30,
//   address: {
//     city: 'New York',
//     country: 'USA'
//   }
// }
```

## How to access nested object properties?

You can access nested object properties using the dot notation or the bracket notation.

### Using the dot notation
```javascript
let person = {
  name: 'John',
  age: 30,
  address: {
    city: 'New York',
    country: 'USA'
  }
};
console.log(person.address.city);
// Output:
// 'New York'
```

### Using the bracket notation
```javascript
let person = {
  name: 'John',
  age: 30,
  address: {
    city: 'New York',
    country: 'USA'
  }
};
console.log(person['address']['city']);
// Output:
// 'New York'
```

## How to update nested object properties?

You can update nested object properties using the dot notation or the bracket notation.

### Using the dot notation
```javascript
let person = {
  name: 'John',
  age: 30,
  address: {
    city: 'New York',
    country: 'USA'
  }
};
person.address.city = 'Los Angeles';
console.log(person.address.city);
// Output:
// 'Los Angeles'
```

### Using the bracket notation
```javascript
let person = {
  name: 'John',
  age: 30,
  address: {
    city: 'New York',
    country: 'USA'
  }
};
person['address']['city'] = 'Los Angeles';
console.log(person['address']['city']);
// Output:
// 'Los Angeles'
```

## How to delete nested object properties?

You can delete nested object properties using the `delete` operator.

### Example of deleting nested object properties
```javascript
let person = {
  name: 'John',
  age: 30,
  address: {
    city: 'New York',
    country: 'USA'
  }
};
delete person.address.city;
console.log(person);
// Output:
// {
//   name: 'John',
//   age: 30,
//   address: {
//     country: 'USA'
//   }
// }
```

### Using the bracket notation
```javascript
let person = {
  name: 'John',
  age: 30,
  address: {
    city: 'New York',
    country: 'USA'
  }
};
delete person['address']['city'];
console.log(person);
// Output:
// {
//   name: 'John',
//   age: 30,
//   address: {
//     country: 'USA'
//   }
// }
```

## What is Property shorthand?

Property shorthand is a feature in JavaScript that allows you to create object properties using variables with the same name as the property key.

### Example of property shorthand
```javascript
let name = 'John';
let age = 30;

// Using property shorthand
let person = {
  name,
  age
};
console.log(person);
// Output:
// {
//   name: 'John',
//   age: 30
// }
```

## What is Computed properties?

Computed properties is a feature in JavaScript that allows you to create object properties with dynamic keys.

### Example of computed properties
```javascript
let key = 'name';
let person = {
  [key]: 'John'
};
console.log(person);
// Output:
// {
//   name: 'John'
// }
```

## What is Method shorthand?

Method shorthand is a feature in JavaScript that allows you to define methods in an object without using the `function` keyword.

### Example of method shorthand
```javascript
let person = {
  name: 'John',
  age: 30,
  greet() {
    console.log(`Hello, my name is ${this.name}`);
  }
};
person.greet();
// Output:
// 'Hello, my name is John'
```

## What is Object immutability concepts?

Object immutability is a concept in JavaScript that ensures an object's state cannot be changed after it is created. This can be achieved using methods like `Object.freeze()`, `Object.seal()`, and `Object.preventExtensions()`.

### Example of object immutability using `Object.freeze()`
```javascript
let person = {
  name: 'John',
  age: 30
};
Object.freeze(person);
person.age = 31; // This will not change the age
console.log(person);
// Output:
// {
//   name: 'John',
//   age: 30
// }
```
### Example of object immutability using `Object.seal()`
```javascript
let person = {
  name: 'John',
  age: 30
};
Object.seal(person);
person.age = 31; // This will change the age
person.name = 'Doe'; // This will change the name
person.gender = 'male'; // This will not add a new property
console.log(person);
// Output:
// {
//   name: 'Doe',
//   age: 31
// }
```

### Example of object immutability using `Object.preventExtensions()`
```javascript
let person = {
  name: 'John',
  age: 30
};
Object.preventExtensions(person);
person.age = 31; // This will change the age
person.name = 'Doe'; // This will change the name
person.gender = 'male'; // This will not add a new property
console.log(person);
// Output:
// {
//   name: 'Doe',
//   age: 31
// }
```

## Object Methods

| **Method** | **Description** |
|------------|-----------------|
| `Object.freeze(obj)` | Freezes an object, preventing any changes to its properties. |
| `Object.seal(obj)` | Seals an object, allowing modification of existing properties but preventing addition of new properties. |
| `Object.preventExtensions(obj)` | Prevents new properties from being added to an object. |
| `Object.keys(obj)` | Returns an array of a given object's own enumerable property names. |
| `Object.values(obj)` | Returns an array of a given object's own enumerable property values. |
| `Object.entries(obj)` | Returns an array of a given object's own enumerable `[key, value]` pairs. |
| `Object.hasOwn(obj, prop)` | Returns a boolean indicating whether the object has the specified property as its own property. |
| `Object.create(proto, [propertiesObject])` | Creates a new object with the specified prototype object and properties. |
| `Object.assign(target, ...sources)` | Copies the values of all enumerable own properties from one or more source objects to a target object. |
| `Object.getPrototypeOf(obj)` | Returns the prototype of the specified object. |
| `Object.setPrototypeOf(obj, prototype)` | Sets the prototype of the specified object. |
| `Object.isFrozen(obj)` | Determines if an object is frozen. |
| `Object.isSealed(obj)` | Determines if an object is sealed. |
| `Object.isExtensible(obj)` | Determines if an object is extensible. |
| `Object.getOwnPropertyDescriptor(obj, prop)` | Returns the descriptor for a property of an object. |
| `Object.getOwnPropertyNames(obj)` | Returns an array of all properties (enumerable or not) found directly in a given object. |
| `Object.getOwnPropertySymbols(obj)` | Returns an array of all symbol properties found directly in a given object. |
| `Object.defineProperty(obj, prop, descriptor)` | Defines a new property directly on an object, or modifies an existing property on an object, and returns the object. |
| `Object.defineProperties(obj, descriptors)` | Defines new or modifies existing properties directly on an object, returning the object. |
| `Object.preventExtensions(obj)` | Prevents new properties from being added to an object. |
| `Object.is(obj1, obj2)` | Determines whether two values are the same value. |
| `Object.isPrototypeOf(obj)` | Determines whether an object exists in another object's prototype chain. |



# Strings

Strings in JavaScript are used to represent textual data. They are immutable, meaning once a string is created, it cannot be changed. You can create strings using single quotes, double quotes, or backticks (for template literals).

## How to Create Strings

You can create strings in JavaScript using single quotes, double quotes, or backticks. Here are some examples:

```javascript
let singleQuoteString = 'Hello';
let doubleQuoteString = "World";
let templateLiteralString = `Hello, ${doubleQuoteString}!`;
console.log(singleQuoteString); // Output: Hello
console.log(doubleQuoteString); // Output: World
console.log(templateLiteralString); // Output: Hello, World!
```

## What is Escape Characters

Escape characters in JavaScript are used to represent special characters within strings. They are preceded by a backslash (`\`). Here are some common escape characters:

| Escape Character | Description |
|-----------------|-------------|
| `\'` | Single quote |
| `\"` | Double quote |
| `\\` | Backslash |
| `\n` | New line |
| `\r` | Carriage return |
| `\t` | Tab |
| `\b` | Backspace |
| `\f` | Form feed |

Example:
```javascript
let stringWithEscapeCharacters = 'Hello\nWorld';
console.log(stringWithEscapeCharacters);
// Output:
// Hello
// World
```

## What is String immutability

String immutability in JavaScript means that once a string is created, it cannot be changed. Any operation that appears to modify a string actually creates a new string. Here is an example:

```javascript
let originalString = 'Hello';
let modifiedString = originalString.toUpperCase();
console.log(originalString); // Output: Hello
console.log(modifiedString); // Output: HELLO
```

## String Methods

JavaScript provides a variety of methods to work with strings. Here are some commonly used string methods:

| Method | Description |
|--------|-------------|
| `charAt(index)` | Returns the character at the specified index. |
| `concat(str1, str2, ...)` | Combines the text of two or more strings and returns a new string. |
| `includes(substring)` | Determines whether a string contains the characters of a specified string. |
| `indexOf(substring)` | Returns the index of the first occurrence of a specified value in a string. |
| `slice(start, end)` | Extracts a section of a string and returns it as a new string. |
| `split(separator)` | Splits a string into an array of substrings. |
| `toLowerCase()` | Converts a string to lowercase letters. |
| `toUpperCase()` | Converts a string to uppercase letters. |
| `trim()` | Removes whitespace from both ends of a string. |
| `replace(searchValue, newValue)` | Replaces occurrences of a specified value with a new value. |
| `startsWith(substring)` | Determines whether a string starts with the characters of a specified string. |
| `endsWith(substring)` | Determines whether a string ends with the characters of a specified string. |
| `repeat(count)` | Returns a new string with a specified number of copies of the original string. |
| `substring(start, end)` | Returns the part of the string between the start and end indexes. |
| `valueOf()` | Returns the primitive value of a string. |
| `padStart(targetLength, padString)` | Pads the current string with another string (repeated, if needed) so that the resulting string reaches the given length. |
| `padEnd(targetLength, padString)` | Pads the current string with another string (repeated, if needed) so that the resulting string reaches the given length. |
| `match(regexp)` | Retrieves the result of matching a string against a regular expression. |
| `search(regexp)` | Executes a search for a match between a regular expression and this string. |
| `replaceAll(searchValue, newValue)` | Replaces all occurrences of a specified value with a new value. |
| `localeCompare(compareString)` | Compares two strings in the current locale. |
| `normalize(form)` | Returns the Unicode Normalization Form of the string. |
| `charCodeAt(index)` | Returns the Unicode of the character at the specified index. |
| `fromCharCode(code)` | Returns a string created from the specified sequence of UTF-16 code units. |
| `codePointAt(index)` | Returns a non-negative integer that is the Unicode code point value at the given position. |
| `fromCodePoint(codePoint)` | Returns a string created by using the specified sequence of code points. |
| `toString()` | Returns a string representing the specified object. |

## What is String interpolation?

String interpolation in JavaScript allows you to embed expressions within string literals. This is typically done using template literals, which are enclosed by backticks (`` ` ``) instead of single or double quotes. Expressions inside template literals are indicated by `${expression}`.

Example:
```javascript
const name = "John";
const age = 30;
const message = `My name is ${name} and I am ${age} years old.`;
console.log(message); // Output: My name is John and I am 30 years old.
```

# Numbers & Math

Numbers in JavaScript can be represented as integers or floating-point values. JavaScript provides various methods and properties to work with numbers, as well as the built-in `Math` object for mathematical operations.

## Number type

In JavaScript, the `Number` type is used to represent both integer and floating-point numbers. There is no separate type for integers.

Example:
```javascript
const integer = 42;
const floatingPoint = 3.14;
console.log(typeof integer); // Output: "number"
console.log(typeof floatingPoint); // Output: "number"
```

## Math object

The `Math` object in JavaScript provides properties and methods for mathematical constants and functions. It is not a constructor, so all properties and methods are static and can be accessed directly from the `Math` object.

Example:
```javascript
console.log(Math.PI); // Output: 3.141592653589793
console.log(Math.sqrt(16)); // Output: 4
console.log(Math.abs(-7)); // Output: 7
console.log(Math.floor(4.7)); // Output: 4
console.log(Math.ceil(4.3)); // Output: 5
console.log(Math.random()); // Output: A random number between 0 and 1
```

## Common Math Methods

Here are some commonly used methods from the `Math` object:

| Method | Description |
|--------|-------------|
| `Math.max(...numbers)` | Returns the largest of the given numbers. |
| `Math.min(...numbers)` | Returns the smallest of the given numbers. |
| `Math.pow(base, exponent)` | Returns the base raised to the power of the exponent. |
| `Math.round(number)` | Returns the value of a number rounded to the nearest integer. |
| `Math.trunc(number)` | Returns the integer part of a number by removing any fractional digits. |
| `Math.sin(angle)` | Returns the sine of an angle (in radians). |
| `Math.cos(angle)` | Returns the cosine of an angle (in radians). |
| `Math.tan(angle)` | Returns the tangent of an angle (in radians). |
| `Math.log(number)` | Returns the natural logarithm (base `e`) of a number. |
| `Math.exp(number)` | Returns `e` raised to the power of the given number. |
| `Math.sqrt(number)` | Returns the square root of a number. |
| `Math.abs(number)` | Returns the absolute value of a number. |
| `Math.floor(number)` | Returns the largest integer less than or equal to a given number. |
| `Math.ceil(number)` | Returns the smallest integer greater than or equal to a given number. |
| `Math.random()` | Returns a random number between 0 (inclusive) and 1 (exclusive). |
| `Math.sign(number)` | Returns the sign of a number, indicating whether it is positive, negative, or zero. |
| `Math.cbrt(number)` | Returns the cube root of a number. |
| `Math.hypot(...numbers)` | Returns the square root of the sum of the squares of its arguments. |
| `Math.clz32(number)` | Returns the number of leading zero bits in the 32-bit binary representation of a number. |
| `Math.imul(a, b)` | Returns the result of a 32-bit integer multiplication of the two parameters. |
| `Math.fround(number)` | Returns the nearest 32-bit single precision float representation of a number. |
| `Math.log10(number)` | Returns the base 10 logarithm of a number. |
| `Math.log2(number)` | Returns the base 2 logarithm of a number. |
| `Math.log1p(number)` | Returns the natural logarithm of 1 plus the given number. |
| `Math.expm1(number)` | Returns `e` raised to the power of the given number minus 1. |
| `Math.sinh(number)` | Returns the hyperbolic sine of a number. |
| `Math.cosh(number)` | Returns the hyperbolic cosine of a number. |
| `Math.tanh(number)` | Returns the hyperbolic tangent of a number. |
| `Math.asin(number)` | Returns the arcsine of a number (in radians). |
| `Math.acos(number)` | Returns the arccosine of a number (in radians). |
| `Math.atan(number)` | Returns the arctangent of a number (in radians). |
| `Math.atan2(y, x)` | Returns the arctangent of the quotient of its arguments (in radians). |
| `Math.asinh(number)` | Returns the hyperbolic arcsine of a number. |
| `Math.acosh(number)` | Returns the hyperbolic arccosine of a number. |
| `Math.atanh(number)` | Returns the hyperbolic arctangent of a number. |
| `Math.cbrt(number)` | Returns the cube root of a number. |

## Number Methods

| Method | Description |
|--------|-------------|
| `Number.isFinite(value)` | Determines whether the passed value is a finite number. |
| `Number.isInteger(value)` | Determines whether the passed value is an integer. |
| `Number.isNaN(value)` | Determines whether the passed value is `NaN`. |
| `Number.isSafeInteger(value)` | Determines whether the passed value is a safe integer. |
| `Number.parseFloat(string)` | Parses a string argument and returns a floating point number. |
| `Number.parseInt(string, radix)` | Parses a string argument and returns an integer of the specified radix. |
| `Number.prototype.toExponential(fractionDigits)` | Returns a string representing the number in exponential notation. |
| `Number.prototype.toFixed(digits)` | Returns a string representing the number in fixed-point notation. |
| `Number.prototype.toPrecision(precision)` | Returns a string representing the number to the specified precision. |
| `Number.prototype.toString(radix)` | Returns a string representing the number in the specified radix. |
| `Number.prototype.valueOf()` | Returns the primitive value of the number object. |


# ES6 Features in JavaScript

## What is ES6?

ES6, also known as ECMAScript 2015, is the sixth edition of the ECMAScript language specification. It introduced several new features and improvements to JavaScript, making it more powerful and easier to work with.

Some of the key features of ES6 include:
- Arrow functions
- Classes
- Template literals
- Destructuring assignment
- Default parameters
- Rest and spread operators
- Modules
- Promises
- Let and const keywords
- Enhanced object literals
- Default iterators
- Generators
- Symbols
- Map and Set data structures
- WeakMap and WeakSet data structures
- Modules and import/export
- Async/await


## Arrow Functions

## Why Arrow Functions introduced, and is it better than traditional functions?

Arrow functions were introduced in ES6 to provide a shorter syntax for writing functions and to address some of the issues with the `this` keyword in traditional functions. They are particularly useful for writing concise callbacks and for maintaining the lexical scope of `this`.

Advantages of arrow functions over traditional functions include:
- Shorter syntax
- Lexical scoping of `this`
- Implicit return for single-expression functions

However, arrow functions are not suitable for all situations, such as defining object methods or constructors.

## What problems do arrow functions solve?

Arrow functions primarily solve the problem of maintaining the correct `this` context in callbacks and nested functions. In traditional functions, the value of `this` can change depending on how the function is called, which often leads to unexpected behavior. Arrow functions capture the `this` value from the surrounding lexical scope, ensuring consistent behavior.

They also provide a more concise syntax for writing functions, especially for short, single-expression functions, reducing boilerplate code.

## Examples of Arrow Functions

Here are some examples demonstrating the use of arrow functions:

```javascript
// Traditional function
function add(a, b) {
  return a + b;
}

// Arrow function
const add = (a, b) => a + b;

// Arrow function with a single parameter
const square = x => x * x;

// Arrow function with no parameters
const greet = () => console.log("Hello, world!");
```

## Key Points to Remember About Arrow Functions

- Arrow functions provide a shorter syntax for writing functions.
- They do not have their own `this` context; they inherit `this` from the surrounding lexical scope.
- They are not suitable for defining object methods or constructors.
- They are ideal for short, single-expression functions and callbacks.

## What is Destructuring and why is it useful?

Destructuring is a feature in ES6 that allows you to unpack values from arrays or properties from objects into distinct variables. It provides a more concise and readable way to extract data from complex structures.

Advantages of destructuring include:
- Cleaner and more readable code
- Easier extraction of multiple properties or elements
- Reduces the need for repetitive code when accessing object properties or array elements
- Makes it easier to work with nested data structures

## What problems does destructuring solve?
Destructuring solves several problems related to extracting values from arrays and objects:
- It eliminates the need for repetitive code when accessing multiple properties or elements.
- It makes the code more readable and easier to understand.
- It helps avoid errors when working with nested data structures by providing a clear and concise syntax.
- It allows for default values, making the code more robust and less error-prone.

## Before Destructuring how we accessed values

Before destructuring, extracting values from arrays or objects often required repetitive code. For example:

```javascript
// Accessing array elements
const numbers = [1, 2, 3];
const first = numbers[0];
const second = numbers[1];

// Accessing object properties
const person = { name: "Alice", age: 25 };
const name = person.name;
const age = person.age;
```

## Using Destructuring to Access Values

With destructuring, you can extract values from arrays and objects more concisely:

```javascript
// Destructuring array elements
const numbers = [1, 2, 3];
const [first, second] = numbers;

// Destructuring object properties
const person = { name: "Alice", age: 25 };
const { name, age } = person;
```

## Destructuring with Default Values

Destructuring also allows you to set default values for variables in case the unpacked value is `undefined`:

```javascript
// Array destructuring with default values
const numbers = [1];
const [first, second = 2] = numbers; // second will be 2

// Object destructuring with default values
const person = { name: "Alice" };
const { name, age = 25 } = person; // age will be 25
```

## Nested Destructuring

Destructuring can also be used with nested objects and arrays, allowing you to extract deeply nested values in a concise manner:

```javascript
// Nested array destructuring
const numbers = [1, [2, 3]];
const [first, [second, third]] = numbers;

// Nested object destructuring
const person = { name: "Alice", address: { city: "Wonderland", zip: "12345" } };
const { name, address: { city, zip } } = person;
```

## What is Spread and Rest and what it the meaning of them?

Spread and Rest are two related concepts in JavaScript that allow you to work with arrays and objects more flexibly.

- **Spread** syntax (`...`) allows an iterable (like an array or object) to be expanded into individual elements.
- **Rest** syntax (`...`) allows you to collect multiple elements into a single array or object.

### Spread Example

```javascript
// Spread with arrays
const numbers = [1, 2, 3];
const moreNumbers = [...numbers, 4, 5]; // [1, 2, 3, 4, 5]

// Spread with objects
const person = { name: "Alice", age: 25 };
const updatedPerson = { ...person, age: 26 }; // { name: "Alice", age: 26 }
```

### Rest Example

```javascript
// Rest with arrays
const [first, ...rest] = [1, 2, 3, 4]; // first = 1, rest = [2, 3, 4]

// Rest with objects
const { name, ...otherProps } = { name: "Alice", age: 25, city: "Wonderland" };
// name = "Alice", otherProps = { age: 25, city: "Wonderland" }
```

## What problem do Spread and Rest solve?

Spread and Rest help solve the problem of handling multiple elements in arrays and objects more efficiently. 
Without them, you would need to manually copy elements or use loops to collect remaining elements, which can be verbose and error-prone.

For example:
- Spread allows you to easily combine arrays or objects without mutating the original ones.
- Rest allows you to capture remaining elements or properties without explicitly listing them all.

## Before Spread and Rest how did we handle multiple elements?

Before the introduction of Spread and Rest, handling multiple elements in arrays and objects often required manual copying or using loops, which could be cumbersome and error-prone.

For example:

```javascript
// Combining arrays before spread
const numbers = [1, 2, 3];
const moreNumbers = numbers.concat([4, 5]); // [1, 2, 3, 4, 5]

// Capturing remaining elements before rest
const array = [1, 2, 3, 4];
const first = array[0];
const rest = array.slice(1); // [2, 3, 4]

// Combining objects before spread
const person = { name: "Alice", age: 25 };
const updatedPerson = Object.assign({}, person, { age: 26 }); // { name: "Alice", age: 26 }

// Capturing remaining properties before rest
const original = { name: "Alice", age: 25, city: "Wonderland" };
const name = original.name;
const otherProps = Object.assign({}, original);
delete otherProps.name; // { age: 25, city: "Wonderland" }
```

## What is classes?

Classes in JavaScript are a way to create objects and handle inheritance more easily. They provide a syntactical sugar over the existing prototype-based inheritance and make the code more readable and structured.

### Class Example

```javascript
// Defining a class
class Person {
  constructor(name, age) {
    this.name = name;
    this.age = age;
  }

  greet() {
    console.log(`Hello, my name is ${this.name} and I am ${this.age} years old.`);
  }
}

// Creating an instance of the class
const alice = new Person("Alice", 25);
alice.greet(); // Hello, my name is Alice and I am 25 years old.
```

## What problem do Classes solve?

Classes solve the problem of creating objects and managing inheritance in a more structured and readable way. 
Before classes, JavaScript relied on prototype-based inheritance, which could be less intuitive and harder to manage, especially for developers coming from class-based languages. 
Classes provide a clear and concise syntax for defining constructors, methods, and inheritance, making the code easier to understand and maintain.

```javascript
// Creating objects and managing inheritance before classes
function Person(name, age) {
  this.name = name;
  this.age = age;
}

Person.prototype.greet = function() {
  console.log(`Hello, my name is ${this.name} and I am ${this.age} years old.`);
};

const alice = new Person("Alice", 25);
alice.greet(); // Hello, my name is Alice and I am 25 years old.
```

## What are the benefits of using Classes?

Classes offer several benefits over traditional prototype-based inheritance:
- **Clearer syntax**: Classes provide a more readable and structured way to define constructors and methods.
- **Inheritance**: Classes make it easier to create subclasses and manage inheritance using the `extends` and `super` keywords.
- **Encapsulation**: Classes allow for better encapsulation of data and behavior, making it easier to manage and maintain code.
- **Consistency**: Using classes provides a consistent approach to object-oriented programming in JavaScript, especially for developers coming from other class-based languages.

## classes and its features

Classes in JavaScript come with several features that make object-oriented programming more convenient:

- **Constructor**: A special method for creating and initializing an object instance of a class.
- **Methods**: Functions defined inside a class that operate on instances of the class.
- **Inheritance**: The ability to create a class that is a child of another class using the `extends` keyword.
- **Super**: The `super` keyword is used to call the constructor or methods of the parent class.
- **Static methods**: Methods that belong to the class itself rather than an instance of the class.
- **Getters and Setters**: Special methods to get and set the values of properties in a controlled manner.

## Example of Class Features

```javascript
class Person {
  constructor(name, age) {
    this.name = name;
    this.age = age;
  }

  greet() {
    console.log(`Hello, my name is ${this.name} and I am ${this.age} years old.`);
  }

  static species() {
    return "Homo sapiens";
  }

  get info() {
    return `${this.name} is ${this.age} years old.`;
  }

  set updateAge(newAge) {
    this.age = newAge;
  }
}

const bob = new Person("Bob", 30);
bob.greet(); // Hello, my name is Bob and I am 30 years old.
console.log(Person.species()); // Homo sapiens
console.log(bob.info); // Bob is 30 years old.
bob.updateAge = 31;
console.log(bob.info); // Bob is 31 years old.
```

## When do we use classes and when do we use objects?

In JavaScript, you might choose to use classes or plain objects depending on the situation:

- **Use classes when**:
  - You need to create multiple instances of similar objects.
  - You want to take advantage of inheritance and polymorphism.
  - You prefer a structured, object-oriented approach.

- **Use plain objects when**:
  - You only need a single instance of an object.
  - You don't need inheritance or complex behavior.
  - You prefer a simpler, functional approach.

## What is Modules?

Modules in JavaScript are reusable pieces of code that can be exported from one file and imported into another. They help in organizing code, maintaining separation of concerns, and avoiding global namespace pollution.

## What problem do modules solve?

Before modules, JavaScript code was often written in a single file or split across multiple files that all shared the same global scope. This could lead to:
- **Global namespace pollution**: Variables and functions could accidentally overwrite each other.
- **Tight coupling**: Code in different files could become interdependent and hard to maintain.
- **Difficulty in reuse**: Reusing code across projects was cumbersome.

Modules solve these problems by providing a way to encapsulate code and explicitly export and import only what is needed.

## Before modules how did we manage code?

Before the introduction of modules, developers had to rely on patterns like Immediately Invoked Function Expressions (IIFEs) or the Revealing Module Pattern to create private scopes and avoid polluting the global namespace. This often led to more complex and less maintainable code.

## Example of IIFE for Code Management

```javascript
(function() {
  const privateVariable = "I am private";

  function privateFunction() {
    console.log(privateVariable);
  }

  window.myModule = {
    publicMethod: function() {
      privateFunction();
    }
  };
})();

// Usage
myModule.publicMethod(); // I am private
```

## Example of Revealing Module Pattern

```javascript
const myRevealingModule = (function() {
  const privateVariable = "I am private";

  function privateFunction() {
    console.log(privateVariable);
  }

  function publicMethod() {
    privateFunction();
  }

  return {
    publicMethod: publicMethod
  };
})();

// Usage
myRevealingModule.publicMethod(); // I am private
```

## What is Promise?

A Promise in JavaScript is an object that represents the eventual completion (or failure) of an asynchronous operation and its resulting value. Promises provide a cleaner and more manageable way to handle asynchronous code compared to traditional callback functions.

## Example of a Promise

```javascript
const myPromise = new Promise((resolve, reject) => {
  const success = true; // Simulate an asynchronous operation
  if (success) {
    resolve("Operation was successful");
  } else {
    reject("Operation failed");
  }
});

myPromise
  .then((message) => {
    console.log(message);
  })
  .catch((error) => {
    console.error(error);
  });
```

## What problem do Promises solve?

Before Promises, handling asynchronous operations in JavaScript was typically done using callbacks. This often led to "callback hell," where callbacks were nested within callbacks, making the code difficult to read and maintain. Promises provide a more structured and manageable way to handle asynchronous operations, allowing for cleaner chaining of asynchronous tasks and better error handling.

## How do we handle asynchronous before Promises?

Before Promises, asynchronous operations in JavaScript were typically handled using callbacks. A callback is a function passed as an argument to another function, which is then invoked after the asynchronous operation completes. While this approach works, it often leads to deeply nested code, commonly referred to as "callback hell."

### Example of Asynchronous Handling with Callbacks

```javascript
function asyncOperation(callback) {
  setTimeout(() => {
    const success = true; // Simulate an asynchronous operation
    if (success) {
      callback(null, "Operation was successful");
    } else {
      callback("Operation failed", null);
    }
  }, 1000);
}

asyncOperation((error, message) => {
  if (error) {
    console.error(error);
  } else {
    console.log(message);
  }
});
```

## Callback Hell

Callback hell refers to the situation where multiple asynchronous operations are nested within each other using callbacks, leading to deeply indented and hard-to-read code. This makes it difficult to maintain and debug the code.

### Example of Callback Hell

```javascript
function asyncOperation1(callback) {
  setTimeout(() => {
    const success = true;
    if (success) {
      callback(null, "Operation 1 successful");
    } else {
      callback("Operation 1 failed", null);
    }
  }, 1000);
}

function asyncOperation2(callback) {
  setTimeout(() => {
    const success = true;
    if (success) {
      callback(null, "Operation 2 successful");
    } else {
      callback("Operation 2 failed", null);
    }
  }, 1000);
}

asyncOperation1((error, message) => {
  if (error) {
    console.error(error);
  } else {
    console.log(message);
    asyncOperation2((error, message) => {
      if (error) {
        console.error(error);
      } else {
        console.log(message);
      }
    });
  }
});
```

## How to create promises?

In JavaScript, a Promise is created using the `Promise` constructor, which takes a function (executor) with two parameters: `resolve` and `reject`. The `resolve` function is called when the asynchronous operation is successful, and the `reject` function is called when it fails.

### Example of Creating a Promise

```javascript
const myPromise = new Promise((resolve, reject) => {
  const success = true; // Simulate an asynchronous operation
  if (success) {
    resolve("Operation was successful");
  } else {
    reject("Operation failed");
  }
});

myPromise
  .then((message) => {
    console.log(message);
  })
  .catch((error) => {
    console.error(error);
  });
```

## Promises and its features

Promises in JavaScript have several key features:

1. **Chaining**: Promises can be chained using `.then()`, allowing sequential asynchronous operations without deeply nested callbacks.
2. **Error Handling**: Errors in Promises can be caught using `.catch()`, providing a centralized way to handle errors.
3. **State**: A Promise has three states: `pending`, `fulfilled`, and `rejected`.
4. **Immutability**: Once a Promise is settled (either fulfilled or rejected), its state cannot change.
5. **Composability**: Promises can be combined using `Promise.all()`, `Promise.race()`, and other utility methods to handle multiple asynchronous operations concurrently.

## Promise.all() and Promise.race()

### Example of Promise.all()

```javascript
const promise1 = new Promise((resolve, reject) => {
  setTimeout(() => resolve("Promise 1 resolved"), 1000);
});

const promise2 = new Promise((resolve, reject) => {
  setTimeout(() => resolve("Promise 2 resolved"), 2000);
});

Promise.all([promise1, promise2])
  .then((messages) => {
    console.log(messages); // ["Promise 1 resolved", "Promise 2 resolved"]
  })
  .catch((error) => {
    console.error(error);
  });
```

### Example of Promise.race()

```javascript
const promise3 = new Promise((resolve, reject) => {
  setTimeout(() => resolve("Promise 3 resolved"), 1000);
});

const promise4 = new Promise((resolve, reject) => {
  setTimeout(() => resolve("Promise 4 resolved"), 2000);
});

Promise.race([promise3, promise4])
  .then((message) => {
    console.log(message); // "Promise 3 resolved"
  })
  .catch((error) => {
    console.error(error);
  });
```

## What is Iterators

In JavaScript, an iterator is an object that provides a mechanism to traverse through a collection (like an array or a string) one element at a time. An iterator has a `next()` method that returns an object with two properties: `value` (the current element) and `done` (a boolean indicating whether the iteration is complete).

### Example of an Iterator

```javascript
const array = [1, 2, 3];
const iterator = array[Symbol.iterator]();

console.log(iterator.next()); // { value: 1, done: false }
console.log(iterator.next()); // { value: 2, done: false }
console.log(iterator.next()); // { value: 3, done: false }
console.log(iterator.next()); // { value: undefined, done: true }
```

### Example of a String Iterator

```javascript
const str = "hello";
const strIterator = str[Symbol.iterator]();

console.log(strIterator.next()); // { value: 'h', done: false }
console.log(strIterator.next()); // { value: 'e', done: false }
console.log(strIterator.next()); // { value: 'l', done: false }
console.log(strIterator.next()); // { value: 'l', done: false }
console.log(strIterator.next()); // { value: 'o', done: false }
console.log(strIterator.next()); // { value: undefined, done: true }
```

## What is Generators

In JavaScript, a generator is a special type of function that can be paused and resumed, allowing you to control the flow of iteration. Generators are defined using the `function*` syntax and use the `yield` keyword to produce values.

### Example of a Generator

```javascript
function* generatorExample() {
  yield 1;
  yield 2;
  yield 3;
}

const gen = generatorExample();

console.log(gen.next()); // { value: 1, done: false }
console.log(gen.next()); // { value: 2, done: false }
console.log(gen.next()); // { value: 3, done: false }
console.log(gen.next()); // { value: undefined, done: true }
```

### Example of a Generator with Parameters

```javascript
function* generatorWithParams(start, end) {
  for (let i = start; i <= end; i++) {
    yield i;
  }
}

const genParams = generatorWithParams(1, 3);

console.log(genParams.next()); // { value: 1, done: false }
console.log(genParams.next()); // { value: 2, done: false }
console.log(genParams.next()); // { value: 3, done: false }
console.log(genParams.next()); // { value: undefined, done: true }
```

## Map and Set

In JavaScript, `Map` and `Set` are built-in objects that allow you to store collections of data. A `Map` is a collection of key-value pairs, while a `Set` is a collection of unique values.

## What problem do Map and Set solve?

`Map` and `Set` solve the problem of efficiently storing and managing collections of data. 
- `Map` allows you to store key-value pairs with any type of key, providing fast lookups, additions, and deletions.
- `Set` allows you to store unique values, automatically handling duplicates and providing efficient membership checks.

### Example of a Map

```javascript
const map = new Map();
map.set('a', 1);
map.set('b', 2);
map.set('c', 3);

console.log(map.get('a')); // 1
console.log(map.get('b')); // 2
console.log(map.get('c')); // 3
console.log(map.has('a')); // true
console.log(map.has('d')); // false
console.log(map.size); // 3
```

### Example of a Set

```javascript
const set = new Set();
set.add(1);
set.add(2);
set.add(3);
set.add(2); // Duplicate value, will not be added

console.log(set.has(1)); // true
console.log(set.has(4)); // false
console.log(set.size); // 3
console.log(set); // Set(3) { 1, 2, 3 }
```

## WeakMap and WeakSet

In JavaScript, `WeakMap` and `WeakSet` are similar to `Map` and `Set`, but they only hold "weak" references to objects, meaning the objects can be garbage-collected if there are no other references to them. `WeakMap` keys must be objects, and `WeakSet` values must be objects.

## What problem do WeakMap and WeakSet solve?

`WeakMap` and `WeakSet` solve the problem of memory management for objects that are only needed temporarily. 
- `WeakMap` allows you to associate data with objects without preventing garbage collection of those objects.
- `WeakSet` allows you to store objects without preventing their garbage collection, ensuring that memory is efficiently managed.

### Example of a WeakMap

```javascript
const weakMap = new WeakMap();
const obj1 = {};
const obj2 = {};

weakMap.set(obj1, 'value1');
weakMap.set(obj2, 'value2');

console.log(weakMap.get(obj1)); // 'value1'
console.log(weakMap.get(obj2)); // 'value2'
console.log(weakMap.has(obj1)); // true
console.log(weakMap.has(obj2)); // true
```

### Example of a WeakSet

```javascript
const weakSet = new WeakSet();
const obj3 = {};
const obj4 = {};

weakSet.add(obj3);
weakSet.add(obj4);

console.log(weakSet.has(obj3)); // true
console.log(weakSet.has(obj4)); // true
```

## Optional Chaining

Optional chaining (`?.`) is a feature in JavaScript that allows you to safely access deeply nested properties of an object without having to check if each reference in the chain is valid.

### Example of Optional Chaining

```javascript
const user = {
  name: 'John',
  address: {
    city: 'New York',
  },
};

console.log(user?.name); // 'John'
console.log(user?.address?.city); // 'New York'
console.log(user?.address?.zip); // undefined
console.log(user?.contact?.phone); // undefined
```

## Nullish Coalescing Operator

The nullish coalescing operator (`??`) is a feature in JavaScript that allows you to provide a default value for `null` or `undefined` expressions, without affecting other falsy values like `0` or `''`.

### Example of Nullish Coalescing Operator

```javascript
const user = {
  name: 'John',
  age: null,
};

console.log(user.name ?? 'Default Name'); // 'John'
console.log(user.age ?? 25); // 25
console.log(user.address ?? 'No Address'); // 'No Address'
```

## Logical Assignment Operators

Logical assignment operators combine logical operations with assignment, providing a shorthand way to update variables based on certain conditions.

### Example of Logical Assignment Operators

```javascript
let a = true;
let b = false;

a &&= false; // Equivalent to: a && (a = false)
b ||= true;  // Equivalent to: b || (b = true)
console.log(a); // false
console.log(b); // true
```

## Numeric Separators

Numeric separators (`_`) are a feature in JavaScript that allows you to improve the readability of large numeric literals by using underscores as visual separators.

### Example of Numeric Separators

```javascript
const billion = 1_000_000_000;
const bytes = 0b1010_0001_1000_0101;
const hex = 0xFF_FF_FF_FF;

console.log(billion); // 1000000000
console.log(bytes);   // 41349
console.log(hex);     // 4294967295
```

# DOM Manipulation

DOM manipulation in JavaScript allows you to interact with and modify the structure, content, and style of HTML documents dynamically.

## What is the DOM?

The Document Object Model (DOM) is a programming interface for web documents. It represents the page so that programs can change the document structure, style, and content dynamically. The DOM provides a structured representation of the document as a tree of objects, and it defines methods by which these objects can be accessed and manipulated.

## Accessing DOM Elements
There are several ways to access DOM elements in JavaScript, including:

- `getElementById`: Selects an element by its ID.
- `getElementsByClassName`: Selects elements by their class name.
- `getElementsByTagName`: Selects elements by their tag name.
- `querySelector`: Selects the first element that matches a CSS selector.
- `querySelectorAll`: Selects all elements that match a CSS selector.

### Example of Accessing DOM Elements

```javascript
const elementById = document.getElementById('myId');
const elementsByClassName = document.getElementsByClassName('myClass');
const elementsByTagName = document.getElementsByTagName('div');
const firstElement = document.querySelector('.myClass');
const allElements = document.querySelectorAll('.myClass');

console.log(elementById);
console.log(elementsByClassName);
console.log(elementsByTagName);
console.log(firstElement);
console.log(allElements);
```

## DOM tree

The DOM tree is a hierarchical representation of the elements in an HTML document. Each element, attribute, and piece of text is represented as a node in the tree. The root of the tree is the `document` object, and all other nodes are descendants of this root.

### Example of DOM Tree Structure

```html
<!DOCTYPE html>
<html>
  <head>
    <title>DOM Tree Example</title>
  </head>
  <body>
    <div id="container">
      <p>Hello, World!</p>
    </div>
  </body>
</html>
```

In this example:
- The `document` object is the root of the DOM tree.
- The `<html>` element is a child of the `document`.
- The `<head>` and `<body>` elements are children of the `<html>` element.
- The `<div>` element is a child of the `<body>` element.
- The `<p>` element is a child of the `<div>` element.

![DOM Tree](./images/DOM%20Tree.png)

## document Object

The `document` object represents the entire HTML document. It serves as the entry point for accessing and manipulating the content of the web page. Through the `document` object, you can select elements, create new elements, modify existing elements, and respond to user interactions.

### Example of Using the document Object

```javascript
// Accessing the document title
console.log(document.title);

// Changing the document title
document.title = "New Title";

// Accessing the body element
const body = document.body;
console.log(body);
```

## Creating and Modifying Elements

You can create new elements using the `document.createElement` method and modify existing elements using properties like `textContent`, `innerHTML`, and `setAttribute`.

### Example of Creating and Modifying Elements

```javascript
// Creating a new paragraph element
const newParagraph = document.createElement('p');
newParagraph.textContent = "This is a new paragraph.";

// Adding the new paragraph to the body
document.body.appendChild(newParagraph);

// Modifying an existing element
const existingDiv = document.getElementById('container');
existingDiv.setAttribute('class', 'highlighted');
existingDiv.innerHTML = "<p>Updated content inside the div.</p>";
```

## Removing Elements

You can remove elements from the DOM using the `removeChild` method or the `remove` method.

### Example of Removing Elements

```javascript
// Removing a child element using removeChild
const container = document.getElementById('container');
const paragraph = container.querySelector('p');
container.removeChild(paragraph);

// Removing an element directly using remove
const existingDiv = document.getElementById('container');
existingDiv.remove();
```

## append() and prepend()

The `append()` and `prepend()` methods allow you to insert elements or content at the end or the beginning of a parent element, respectively.

### Example of Using append() and prepend()

```javascript
const container = document.getElementById('container');

// Appending a new paragraph to the container
const appendedParagraph = document.createElement('p');
appendedParagraph.textContent = "This paragraph is appended.";
container.append(appendedParagraph);

// Prepending a new paragraph to the container
const prependedParagraph = document.createElement('p');
prependedParagraph.textContent = "This paragraph is prepended.";
container.prepend(prependedParagraph);
```

## before() and after()

The `before()` and `after()` methods allow you to insert elements or content immediately before or after a specified element, respectively.

### Example of Using before() and after()

```javascript
const container = document.getElementById('container');

// Inserting a new paragraph before the container
const beforeParagraph = document.createElement('p');
beforeParagraph.textContent = "This paragraph is inserted before the container.";
container.before(beforeParagraph);

// Inserting a new paragraph after the container
const afterParagraph = document.createElement('p');
afterParagraph.textContent = "This paragraph is inserted after the container.";
container.after(afterParagraph);
```

## innerHTML, textContent, and innerText

The `innerHTML`, `textContent`, and `innerText` properties allow you to get or set the content of an element.

- `innerHTML` gets or sets the HTML content of an element.
- `textContent` gets or sets the text content of an element, ignoring any HTML tags.
- `innerText` gets or sets the visible text content of an element, taking CSS styling into account.

### Example of Using innerHTML, textContent, and innerText

```javascript
const container = document.getElementById('container');

// Using innerHTML
container.innerHTML = "<p>This is set using innerHTML.</p>";

// Using textContent
container.textContent = "<p>This is set using textContent.</p>";

// Using innerText
container.innerText = "<p>This is set using innerText.</p>";
```

## GetAttribute(), setAttribute() and removeAttribute()

The `getAttribute()`, `setAttribute()`, and `removeAttribute()` methods allow you to get, set, or remove attributes of an element, respectively.

### Example of Using getAttribute(), setAttribute(), and removeAttribute()

```javascript
const container = document.getElementById('container');

// Using getAttribute
const id = container.getAttribute('id');
console.log(id); // Output: "container"

// Using setAttribute
container.setAttribute('class', 'my-container');

// Using removeAttribute
container.removeAttribute('class');
```

## classList

The `classList` property provides methods to add, remove, and toggle CSS classes on an element.

### Example of Using classList

```javascript
const container = document.getElementById('container');

// Adding a class
container.classList.add('my-container');

// Removing a class
container.classList.remove('my-container');

// Toggling a class
container.classList.toggle('my-container');
```

## style

The `style` property allows you to get or set the inline CSS styles of an element.

### Example of Using style

```javascript
const container = document.getElementById('container');

// Setting the background color
container.style.backgroundColor = 'lightblue';

// Setting the font size
container.style.fontSize = '20px';

// Setting multiple styles
container.style.cssText = 'color: red; border: 1px solid black;';
```

## What is DOM Traversal

DOM Traversal refers to the process of navigating through the elements in the Document Object Model (DOM) tree. It allows you to access parent, child, and sibling elements relative to a specific element.

### Example of DOM Traversal

```javascript
const container = document.getElementById('container');

// Accessing the parent element
const parent = container.parentElement;
console.log(parent);

// Accessing the first child element
const firstChild = container.firstElementChild;
console.log(firstChild);

// Accessing the last child element
const lastChild = container.lastElementChild;
console.log(lastChild);

// Accessing the next sibling element
const nextSibling = container.nextElementSibling;
console.log(nextSibling);

// Accessing the previous sibling element
const previousSibling = container.previousElementSibling;
console.log(previousSibling);
```

# Events

Events in JavaScript are actions or occurrences that happen in the browser, such as clicks, key presses, or mouse movements. You can use event listeners to execute code in response to these events.

## Example of Using Events

```javascript
const button = document.getElementById('myButton');

// Adding a click event listener
button.addEventListener('click', () => {
    console.log('Button was clicked!');
});
```

## What are events?

Events are actions or occurrences that happen in the browser, which the JavaScript code can respond to. Examples of events include user interactions like clicks, key presses, mouse movements, and form submissions. Event listeners are used to execute specific code when these events occur.

## Common Event Types

### Mouse Events
- `click`: Fired when an element is clicked.
- `dblclick`: Fired when an element is double-clicked.
- `mouseover`: Fired when the mouse pointer is moved onto an element.
- `mouseout`: Fired when the mouse pointer is moved out of an element.

### Keyboard Events
- `keydown`: Fired when a key is pressed down.
- `keyup`: Fired when a key is released.
- `keypress`: Fired when a key is pressed and released.

### Form Events
- `submit`: Fired when a form is submitted.
- `change`: Fired when the value of an input element changes.
- `focus`: Fired when an element gains focus.
- `blur`: Fired when an element loses focus.

### Window Events
- `load`: Fired when the entire page has loaded, including all dependent resources such as images and stylesheets.
- `resize`: Fired when the browser window is resized.
- `scroll`: Fired when the document view is scrolled.
- `unload`: Fired when the document or a child resource is being unloaded.

### Touch Events
- `touchstart`: Fired when a touch point is placed on the touch surface.
- `touchmove`: Fired when a touch point is moved along the touch surface.
- `touchend`: Fired when a touch point is removed from the touch surface.
- `touchcancel`: Fired when a touch point is interrupted in some way.

### Drag Events
- `drag`: Fired when an element is being dragged.
- `dragstart`: Fired when the user starts dragging an element.
- `dragend`: Fired when the user stops dragging an element.
- `dragenter`: Fired when a dragged element enters a valid drop target.
- `dragover`: Fired when a dragged element is being dragged over a valid drop target.
- `dragleave`: Fired when a dragged element leaves a valid drop target.
- `drop`: Fired when a dragged element is dropped on a valid drop target.

### Clipboard Events
- `copy`: Fired when the user copies content.
- `cut`: Fired when the user cuts content.
- `paste`: Fired when the user pastes content.

### Media Events
- `play`: Fired when the media starts playing.
- `pause`: Fired when the media is paused.
- `ended`: Fired when the media has reached the end.
- `volumechange`: Fired when the volume of the media changes.
- `timeupdate`: Fired when the current playback position changes.
- `seeking`: Fired when the user starts seeking through the media.
- `seeked`: Fired when the user has finished seeking through the media.

### Focus/Blur Events

- `focus`: Fired when an element gains focus.
- `blur`: Fired when an element loses focus.

## Event Object

The event object is automatically passed to event handlers and contains information about the event.

- `type`: The type of the event (e.g., `click`, `keydown`).
- `target`: The element that triggered the event.
- `currentTarget`: The element to which the event handler is attached.
- `preventDefault()`: A method that cancels the event's default action.
- `stopPropagation()`: A method that stops the event from propagating further.
- `stopImmediatePropagation()`: A method that stops the event from propagating and prevents other listeners of the same event from being called.
- `bubbles`: A boolean indicating whether the event bubbles up through the DOM.
- `cancelable`: A boolean indicating whether the event can be canceled.
- `defaultPrevented`: A boolean indicating whether `preventDefault()` has been called on the event.

## Event Phases

Events in the DOM go through three phases:

- `capturing phase`: The event starts from the root and travels down to the target element.
- `target phase`: The event has reached the target element.
- `bubbling phase`: The event bubbles up from the target element back to the root.

## Event Bubbling and Capturing

Event bubbling and capturing are two ways of event propagation in the DOM:

- `bubbling`: The event starts from the target element and bubbles up to the root.
- `capturing`: The event starts from the root and travels down to the target element.

## Event Delegation

Event delegation is a technique where a single event listener is added to a parent element to manage events for its child elements. This is useful for handling events on dynamically added elements and improving performance.

Example:
```javascript
document.getElementById('parent').addEventListener('click', function(event) {
  if (event.target && event.target.matches('button.child')) {
    console.log('Child button clicked:', event.target);
  }
});
```

## Event Propagation

Event propagation refers to the order in which events are received on the page. It can occur in two ways:

- **Capturing phase**: The event starts from the root and travels down to the target element.
- **Bubbling phase**: The event starts from the target element and bubbles up to the root.

By default, most events bubble up, but you can control this behavior using the `capture` option when adding event listeners.

### Controlling Event Propagation

You can control event propagation using the following methods:

- `event.stopPropagation()`: Stops the event from propagating further in the capturing and bubbling phases.
- `event.stopImmediatePropagation()`: Stops the event from propagating and prevents other listeners of the same event from being called.

You can also specify the `capture` option when adding an event listener to control whether it listens during the capturing phase:

```javascript
document.getElementById('element').addEventListener('click', function(event) {
  console.log('Capturing phase listener');
}, true); // true indicates capturing phase
```

### Example: Stopping Event Propagation

```javascript
document.getElementById('parent').addEventListener('click', function(event) {
  console.log('Parent clicked');
});

document.getElementById('child').addEventListener('click', function(event) {
  console.log('Child clicked');
  event.stopPropagation(); // Stops the event from bubbling up to the parent
});
```

## Custom Events

Custom events allow you to create and dispatch your own events in the DOM. This is useful for creating more modular and decoupled code.

Example:
```javascript
// Create a custom event
const myEvent = new CustomEvent('myEvent', {
  detail: { message: 'Hello, world!' }
});

// Add an event listener for the custom event
document.getElementById('element').addEventListener('myEvent', function(event) {
  console.log('Custom event triggered:', event.detail.message);
});

// Dispatch the custom event
document.getElementById('element').dispatchEvent(myEvent);
```

# Browser APIs

## window

The `window` object represents the browser's window. It is the global object in the browser environment and provides methods and properties to interact with the browser.

Example:
```javascript
// Get the current URL
console.log(window.location.href);

// Open a new window
window.open('https://www.example.com', '_blank');

// Set a timeout
window.setTimeout(function() {
  console.log('Timeout executed');
}, 1000);
```

## document

The `document` object represents the HTML document loaded in the browser. It provides methods and properties to interact with the DOM.

Example:
```javascript
// Get an element by its ID
const element = document.getElementById('element');
console.log(element);

// Create a new element
const newElement = document.createElement('div');
newElement.textContent = 'Hello, world!';
document.body.appendChild(newElement);
```

## navigator

The `navigator` object provides information about the browser and the user's environment.

Example:
```javascript
// Get the user agent string
console.log(navigator.userAgent);

// Check if cookies are enabled
console.log(navigator.cookieEnabled);
```

## location

The `location` object provides information about the current URL and allows you to manipulate it.

Example:
```javascript
// Get the current URL
console.log(window.location.href);

// Redirect to a new URL
window.location.href = 'https://www.example.com';

// Reload the current page
window.location.reload();
```

## history

The `history` object provides access to the browser's session history, allowing you to navigate back and forth between pages.

Example:
```javascript
// Go back to the previous page
window.history.back();

// Go forward to the next page
window.history.forward();

// Go to a specific page in the history
window.history.go(-1); // Equivalent to back()
```

## screen

The `screen` object provides information about the user's screen, such as its width, height, and color depth.

Example:
```javascript
// Get the screen width and height
console.log(screen.width, screen.height);

// Get the available screen width and height
console.log(screen.availWidth, screen.availHeight);

// Get the color depth of the screen
console.log(screen.colorDepth);
```

## localStorage

The `localStorage` object provides access to a storage area that persists even after the browser is closed. It allows you to store key-value pairs in the browser.

Example:
```javascript
// Set an item in localStorage
localStorage.setItem('key', 'value');

// Get an item from localStorage
console.log(localStorage.getItem('key'));

// Remove an item from localStorage
localStorage.removeItem('key');

// Clear all items from localStorage
localStorage.clear();
```

## sessionStorage

The `sessionStorage` object provides access to a storage area that persists only for the duration of the page session. It allows you to store key-value pairs in the browser.

Example:
```javascript
// Set an item in sessionStorage
sessionStorage.setItem('key', 'value');

// Get an item from sessionStorage
console.log(sessionStorage.getItem('key'));

// Remove an item from sessionStorage
sessionStorage.removeItem('key');

// Clear all items from sessionStorage
sessionStorage.clear();
```

## Cookies

The `document.cookie` property allows you to get and set cookies associated with the current document.

Example:
```javascript
// Set a cookie
document.cookie = "username=John Doe; expires=Fri, 31 Dec 2024 23:59:59 GMT; path=/";

// Get all cookies
console.log(document.cookie);

// Delete a cookie by setting its expiration date to a past date
document.cookie = "username=; expires=Thu, 01 Jan 1970 00:00:00 GMT; path=/";
```

## Clipboard API

The `navigator.clipboard` object provides access to the system clipboard, allowing you to read from and write to it.

Example:
```javascript
// Write text to the clipboard
navigator.clipboard.writeText('Hello, world!').then(() => {
  console.log('Text copied to clipboard');
}).catch(err => {
  console.error('Failed to copy text: ', err);
});

// Read text from the clipboard
navigator.clipboard.readText().then(text => {
  console.log('Text read from clipboard: ', text);
}).catch(err => {
  console.error('Failed to read text: ', err);
});
```

## Geolocation API

The `navigator.geolocation` object provides access to the device's geographical location.

Example:
```javascript
// Get the current position
navigator.geolocation.getCurrentPosition(position => {
  console.log('Latitude: ', position.coords.latitude);
  console.log('Longitude: ', position.coords.longitude);
}, error => {
  console.error('Error getting location: ', error);
});
```

## Notifications API

The `Notification` object allows you to display notifications to the user.

Example:
```javascript
// Request permission to show notifications
Notification.requestPermission().then(permission => {
  if (permission === 'granted') {
    // Show a notification
    new Notification('Hello, world!');
  }
});
```

## Web Workers

The `Worker` object allows you to run JavaScript code in the background, on a separate thread from the main execution thread.

Example:
```javascript
// Create a new web worker
const worker = new Worker('worker.js');

// Listen for messages from the worker
worker.onmessage = event => {
  console.log('Message from worker: ', event.data);
};

// Send a message to the worker
worker.postMessage('Hello, worker!');
```

## Intersection Observer

The `IntersectionObserver` object allows you to asynchronously observe changes in the intersection of a target element with an ancestor element or with a top-level document's viewport.

Example:
```javascript
// Create an intersection observer
const observer = new IntersectionObserver((entries, observer) => {
  entries.forEach(entry => {
    if (entry.isIntersecting) {
      console.log('Element is in view: ', entry.target);
    }
  });
});

// Target element to observe
const target = document.querySelector('#targetElement');
observer.observe(target);
```

## Mutation Observer

The `MutationObserver` object allows you to watch for changes being made to the DOM tree.

Example:
```javascript
// Create a mutation observer
const observer = new MutationObserver((mutationsList, observer) => {
  for (const mutation of mutationsList) {
    if (mutation.type === 'childList') {
      console.log('A child node has been added or removed.');
    } else if (mutation.type === 'attributes') {
      console.log('The ' + mutation.attributeName + ' attribute was modified.');
    }
  }
});

// Target element to observe
const target = document.querySelector('#targetElement');

// Observer configuration
const config = { attributes: true, childList: true, subtree: true };

// Start observing the target element
observer.observe(target, config);
```

## Resize Observer

The `ResizeObserver` object allows you to watch for changes to the size of an element.

Example:
```javascript
// Create a resize observer
const resizeObserver = new ResizeObserver(entries => {
  for (let entry of entries) {
    console.log('Element resized: ', entry.target);
  }
});

// Target element to observe
const target = document.querySelector('#targetElement');
resizeObserver.observe(target);
```

## SetTimeout() and SetInterval()

The `setTimeout()` function allows you to execute a function after a specified delay, while the `setInterval()` function allows you to execute a function repeatedly at specified intervals.

Example:
```javascript
// Execute a function after 2 seconds
setTimeout(() => {
  console.log('Executed after 2 seconds');
}, 2000);

// Execute a function every 3 seconds
setInterval(() => {
  console.log('Executed every 3 seconds');
}, 3000);
```

# Asynchronous JavaScript

## Synchronous vs Asynchronous JavaScript

Synchronous JavaScript executes code sequentially, meaning each operation must complete before the next one starts. Asynchronous JavaScript allows certain operations to run independently of the main program flow, enabling non-blocking behavior.

Example of synchronous code:
```javascript
console.log('Start');
console.log('Middle');
console.log('End');
```

Example of asynchronous code using `setTimeout`:
```javascript
console.log('Start');
setTimeout(() => {
  console.log('Middle');
}, 2000);
console.log('End');
```

## Blocking vs Non-Blocking JavaScript

Blocking JavaScript operations prevent the execution of subsequent code until the current operation completes, while non-blocking operations allow the program to continue executing other code while waiting for the operation to complete.

Example of blocking code:
```javascript
console.log('Start');
for (let i = 0; i < 1000000000; i++) {
  // Blocking operation
}
console.log('End');
```

Example of non-blocking code using `setTimeout`:
```javascript
console.log('Start');
setTimeout(() => {
  console.log('Middle');
}, 0);
console.log('End');
```

## Async await

The `async` keyword is used to define an asynchronous function, which returns a `Promise`. The `await` keyword is used to pause the execution of an `async` function until the `Promise` is resolved.

Example:
```javascript
async function fetchData() {
  try {
    const response = await fetch('https://api.example.com/data');
    const data = await response.json();
    console.log(data);
  } catch (error) {
    console.error('Error:', error);
  }
}

fetchData();
```

## Error Handling with Async/Await

When using `async` and `await`, it's important to handle errors properly. You can use `try...catch` blocks to catch and handle errors that occur during the asynchronous operation.

Example:
```javascript
async function fetchData() {
  try {
    const response = await fetch('https://api.example.com/data');
    const data = await response.json();
    console.log(data);
  } catch (error) {
    console.error('Error:', error);
  }
}

fetchData();
```

## Parallel promises

When you have multiple asynchronous operations that can be executed concurrently, you can use `Promise.all` to run them in parallel and wait for all of them to complete.

Example:
```javascript
async function fetchMultipleData() {
  try {
    const [response1, response2] = await Promise.all([
      fetch('https://api.example.com/data1'),
      fetch('https://api.example.com/data2')
    ]);
    const data1 = await response1.json();
    const data2 = await response2.json();
    console.log(data1, data2);
  } catch (error) {
    console.error('Error:', error);
  }
}

fetchMultipleData();
```

## Sequential promises

When you have multiple asynchronous operations that need to be executed one after the other, you can use `await` sequentially to ensure each operation completes before moving on to the next.

Example:
```javascript
async function fetchSequentialData() {
  try {
    const response1 = await fetch('https://api.example.com/data1');
    const data1 = await response1.json();
    console.log(data1);

    const response2 = await fetch('https://api.example.com/data2');
    const data2 = await response2.json();
    console.log(data2);
  } catch (error) {
    console.error('Error:', error);
  }
}

fetchSequentialData();
```

## Promise cancellation concepts

Promise cancellation is not natively supported in JavaScript, but you can implement it using techniques like `AbortController` with the Fetch API. This allows you to cancel an ongoing fetch request if it's no longer needed.

Example:
```javascript
const controller = new AbortController();
const signal = controller.signal;

async function fetchData() {
  try {
    const response = await fetch('https://api.example.com/data', { signal });
    const data = await response.json();
    console.log(data);
  } catch (error) {
    if (error.name === 'AbortError') {
      console.log('Fetch aborted');
    } else {
      console.error('Error:', error);
    }
  }
}

// Start fetching data
fetchData();

// Cancel the fetch request after 2 seconds
setTimeout(() => controller.abort(), 2000);
```

## AbortController

`AbortController` is a built-in JavaScript object that allows you to abort one or more web requests. It is commonly used with the Fetch API to cancel ongoing requests.

Example:
```javascript
const controller = new AbortController();
const signal = controller.signal;

fetch('https://api.example.com/data', { signal })
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => {
    if (error.name === 'AbortError') {
      console.log('Fetch aborted');
    } else {
      console.error('Error:', error);
    }
  });

// Cancel the fetch request after 2 seconds
setTimeout(() => controller.abort(), 2000);
```

# Fetch & APIs
The Fetch API provides a modern way to make network requests similar to `XMLHttpRequest`. It returns a promise that resolves to the `Response` object representing the response to the request.

## XHR (XMLHttpRequest)

XMLHttpRequest (XHR) is an older way to make network requests in JavaScript. It allows you to send HTTP requests and handle responses asynchronously, but it uses a callback-based approach rather than promises.

Example:
```javascript
const xhr = new XMLHttpRequest();
xhr.open('GET', 'https://api.example.com/data', true);
xhr.onreadystatechange = function () {
  if (xhr.readyState === 4) {
    if (xhr.status === 200) {
      console.log(JSON.parse(xhr.responseText));
    } else {
      console.error('Error:', xhr.statusText);
    }
  }
};
xhr.send();
```

## Fetch API

The Fetch API provides a modern way to make network requests in JavaScript. It returns a promise that resolves to the `Response` object representing the response to the request.

Example:
```javascript
fetch('https://api.example.com/data')
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```

## Async/Await with Fetch

You can also use the `async`/`await` syntax with the Fetch API to make the code more readable and easier to work with.

Example:
```javascript
async function fetchData() {
  try {
    const response = await fetch('https://api.example.com/data');
    const data = await response.json();
    console.log(data);
  } catch (error) {
    console.error('Error:', error);
  }
}

fetchData();
```

## HTTP basics

HTTP (Hypertext Transfer Protocol) is the foundation of data communication on the web. It defines how messages are formatted and transmitted, and how web servers and browsers should respond to various commands.

Common HTTP methods:
- `GET`: Retrieve data from the server.
- `POST`: Send data to the server.
- `PUT`: Update existing data on the server.
- `PATCH`: Apply partial modifications to a resource.
- `DELETE`: Remove data from the server.

HTTP status codes:
- `200 OK`: The request was successful.
- `201 Created`: The resource was successfully created.
- `400 Bad Request`: The server could not understand the request.
- `401 Unauthorized`: Authentication is required and has failed or has not yet been provided.
- `403 Forbidden`: The server understood the request but refuses to authorize it.
- `404 Not Found`: The requested resource could not be found.
- `500 Internal Server Error`: The server encountered an unexpected condition.
## Common HTTP Headers

HTTP headers provide additional information about the request or response. Some common headers include:
- `Content-Type`: Indicates the media type of the resource (e.g., `application/json`).
- `Authorization`: Contains credentials for authenticating the client with the server.
- `Accept`: Specifies the media types that the client is willing to receive.
- `Cache-Control`: Directives for caching mechanisms in both requests and responses.
- `User-Agent`: Contains information about the client software making the request.
- `Referer`: The address of the previous web page from which a link to the currently requested page was followed.


## Request headers using xhr 

You can set request headers when making an HTTP request using the `XMLHttpRequest` object. Here's an example:
```javascript
const xhr = new XMLHttpRequest();
xhr.open('GET', 'https://api.example.com/data', true);
xhr.setRequestHeader('Authorization', 'Bearer your-token-here');
xhr.setRequestHeader('Content-Type', 'application/json');
xhr.onreadystatechange = function () {
  if (xhr.readyState === 4 && xhr.status === 200) {
    console.log(JSON.parse(xhr.responseText));
  }
};
xhr.send();
```

## Response headers using xhr

You can access response headers after making an HTTP request using the `XMLHttpRequest` object. Here's an example:
```javascript
const xhr = new XMLHttpRequest();
xhr.open('GET', 'https://api.example.com/data', true);
xhr.onreadystatechange = function () {
  if (xhr.readyState === 4 && xhr.status === 200) {
    console.log('Content-Type:', xhr.getResponseHeader('Content-Type'));
    console.log('Authorization:', xhr.getResponseHeader('Authorization'));
    console.log('Cache-Control:', xhr.getResponseHeader('Cache-Control'));
  }
};
xhr.send();
```

## Request headers using fetch

You can set request headers when making an HTTP request using the `fetch` API. Here's an example:
```javascript
fetch('https://api.example.com/data', {
  method: 'GET',
  headers: {
    'Authorization': 'Bearer your-token-here',
    'Content-Type': 'application/json'
  }
})
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```

## Response headers using fetch

You can access response headers after making an HTTP request using the `fetch` API. Here's an example:
```javascript
fetch('https://api.example.com/data', {
  method: 'GET'
})
  .then(response => {
    console.log('Content-Type:', response.headers.get('Content-Type'));
    console.log('Authorization:', response.headers.get('Authorization'));
    console.log('Cache-Control:', response.headers.get('Cache-Control'));
    return response.json();
  })
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```

## Request body using xhr

You can send a request body when making an HTTP request using the `XMLHttpRequest` object. Here's an example:
```javascript
const xhr = new XMLHttpRequest();
xhr.open('POST', 'https://api.example.com/data', true);
xhr.setRequestHeader('Content-Type', 'application/json');
xhr.onreadystatechange = function () {
  if (xhr.readyState === 4 && xhr.status === 200) {
    console.log(JSON.parse(xhr.responseText));
  }
};
const requestBody = JSON.stringify({ key: 'value' });
xhr.send(requestBody);
```

## Request body using fetch

You can send a request body when making an HTTP request using the `fetch` API. Here's an example:
```javascript
fetch('https://api.example.com/data', {
  method: 'POST',
  headers: {
    'Content-Type': 'application/json'
  },
  body: JSON.stringify({ key: 'value' })
})
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```

## Response body using fetch

You can access the response body after making an HTTP request using the `fetch` API. Here's an example:
```javascript
fetch('https://api.example.com/data', {
  method: 'GET'
})
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```

## Response body using xhr

You can access the response body after making an HTTP request using the `XMLHttpRequest` object. Here's an example:
```javascript
const xhr = new XMLHttpRequest();
xhr.open('GET', 'https://api.example.com/data', true);
xhr.onreadystatechange = function () {
  if (xhr.readyState === 4 && xhr.status === 200) {
    console.log(JSON.parse(xhr.responseText));
  }
};
xhr.send();
```

## JSON.stringify and JSON.parse

`JSON.stringify` is used to convert a JavaScript object into a JSON string, and `JSON.parse` is used to convert a JSON string back into a JavaScript object. Here's an example:
```javascript
const obj = { key: 'value' };
const jsonString = JSON.stringify(obj);
console.log(jsonString); // '{"key":"value"}'

const parsedObj = JSON.parse(jsonString);
console.log(parsedObj); // { key: 'value' }
```

## What is REST APIs?

REST (Representational State Transfer) is an architectural style for designing networked applications. REST APIs are web services that adhere to the principles of REST, allowing clients to interact with servers using standard HTTP methods such as GET, POST, PUT, DELETE, etc. REST APIs typically use JSON as the format for request and response bodies.

## Key Principles of REST APIs

1. **Statelessness**: Each request from a client to a server must contain all the information needed to understand and process the request. The server does not store any client context between requests.
2. **Client-Server Architecture**: The client and server are separate entities, allowing them to evolve independently. The client handles the user interface, while the server manages data and business logic.
3. **Uniform Interface**: REST APIs have a consistent and standardized way of interacting with resources, typically using HTTP methods (GET, POST, PUT, DELETE) and resource URIs.
4. **Resource-Based**: Resources (such as users, posts, or products) are identified by URIs, and interactions with these resources are performed using standard HTTP methods.
5. **Representation**: Resources can have multiple representations (e.g., JSON, XML). Clients interact with the resource representations rather than the resource itself.
6. **Stateless Communication**: Each request from the client to the server must contain all the information needed to understand and process the request, and the server should not store any client context between requests.
7. **Cacheability**: Responses from the server can be explicitly marked as cacheable or non-cacheable to improve performance and reduce the need for repeated requests.
8. **Layered System**: REST APIs can be composed of multiple layers, with each layer having a specific responsibility, such as security, caching, or load balancing.
9. **Code on Demand (Optional)**: Servers can extend the functionality of a client by transferring executable code, such as JavaScript. This is an optional constraint and is not commonly used in all REST APIs.

## Query Parameters

Query parameters are used to send additional information to the server as part of the URL. They are typically used to filter, sort, or paginate data. Query parameters are appended to the URL after a `?` and are separated by `&`. Here's an example:
```javascript
// URL with query parameters
const url = 'https://api.example.com/users?role=admin&sort=asc';

fetch(url)
  .then(response => response.json())
  .then(data => console.log(data));
```

## Path Parameters

Path parameters are used to identify specific resources within a REST API. They are part of the URL path and are typically used to specify the resource ID or other unique identifiers. Here's an example:
```javascript
// URL with path parameters
const userId = 123;
const url = `https://api.example.com/users/${userId}`;

fetch(url)
  .then(response => response.json())
  .then(data => console.log(data));
```

## Authentication concepts

Authentication is a crucial aspect of REST APIs to ensure that only authorized users can access certain resources. Common authentication methods include:

1. **API Key**: A unique key provided to the client, which must be included in each request, usually in the headers or query parameters.
2. **Basic Authentication**: The client sends a username and password encoded in the `Authorization` header.
3. **Bearer Token (OAuth)**: The client obtains a token from an authentication server and includes it in the `Authorization` header for subsequent requests.

Here's an example of using a Bearer token with the `fetch` API:
```javascript
const url = 'https://api.example.com/protected-resource';
const token = 'your-access-token';

fetch(url, {
  headers: {
    'Authorization': `Bearer ${token}`
  }
})
  .then(response => response.json())
  .then(data => console.log(data));
```

## CORS basics

CORS (Cross-Origin Resource Sharing) is a security feature implemented by browsers to restrict web pages from making requests to a different domain than the one that served the web page. It helps prevent malicious websites from accessing sensitive data on other domains.

When making cross-origin requests, the server must include appropriate CORS headers to allow the request. Here's an example of a simple `fetch` request that may be subject to CORS restrictions:
```javascript
const url = 'https://api.example.com/data';

fetch(url)
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```

## What is Defensive programming

Defensive programming is a practice aimed at improving software and source code, in terms of:

- **Error handling**: Anticipating potential errors and handling them gracefully.
- **Input validation**: Ensuring that inputs meet expected formats and constraints.
- **Code robustness**: Writing code that can handle unexpected situations without crashing.

In the context of JavaScript and REST APIs, defensive programming might involve checking for the presence of required fields in API responses, validating user inputs before sending requests, and handling network errors appropriately. Here's an example:
```javascript
const url = 'https://api.example.com/data';

fetch(url)
  .then(response => {
    if (!response.ok) {
      throw new Error('Network response was not ok');
    }
    return response.json();
  })
  .then(data => {
    if (!data || !data.requiredField) {
      throw new Error('Invalid data received');
    }
    console.log(data);
  })
  .catch(error => console.error('Error:', error));
```


# Object-Oriented JavaScript

## What is Object-Oriented JavaScript

Object-Oriented JavaScript is a programming paradigm that uses objects and classes to structure and organize code. It allows developers to create reusable and modular code by defining objects with properties and methods.

## Key Concepts of Object-Oriented JavaScript

1. **Classes**: Blueprints for creating objects with predefined properties and methods.
2. **Objects**: Instances of classes that hold data and behavior.
3. **Encapsulation**: The practice of keeping an object's state private and exposing only necessary methods.
4. **Inheritance**: The mechanism by which one class can inherit properties and methods from another class.
5. **Polymorphism**: The ability of different classes to be treated as instances of the same class through a common interface.

## What is the Difference Between Object-Oriented and Procedural JavaScript

Object-Oriented JavaScript focuses on creating objects that encapsulate data and behavior, promoting code reuse and modularity. Procedural JavaScript, on the other hand, is centered around writing procedures or functions that operate on data, often leading to less modular and less reusable code.

## What is the meaning of Procedural JavaScript

Procedural JavaScript is a programming paradigm that focuses on writing procedures or functions that operate on data. It emphasizes a step-by-step approach to solving problems, where the program's logic is organized into reusable functions rather than objects and classes.

### Example of Procedural JavaScript

```javascript
// Procedural approach
let name = 'Alice';
let age = 30;

function greet(name, age) {
  console.log(`Hello, my name is ${name} and I am ${age} years old.`);
}

greet(name, age); // Output: Hello, my name is Alice and I am 30 years old.
```

### Example of Object-Oriented JavaScript

```javascript
// Object-Oriented approach
class Person {
  constructor(name, age) {
    this.name = name;
    this.age = age;
  }

  greet() {
    console.log(`Hello, my name is ${this.name} and I am ${this.age} years old.`);
  }
}

const person1 = new Person('Alice', 30);
person1.greet(); // Output: Hello, my name is Alice and I am 30 years old.
```

## How to Create Classes

In JavaScript, classes are created using the `class` keyword. A class can have a constructor method to initialize object properties and other methods to define the behavior of the objects.

### Syntax

```javascript
class ClassName {
  constructor(property1, property2) {
    this.property1 = property1;
    this.property2 = property2;
  }

  method1() {
    // Method logic
  }
}
```

### Example

```javascript
class Person {
  constructor(name, age) {
    this.name = name;
    this.age = age;
  }

  greet() {
    console.log(`Hello, my name is ${this.name} and I am ${this.age} years old.`);
  }
}

const person1 = new Person('Alice', 30);
person1.greet(); // Output: Hello, my name is Alice and I am 30 years old.
```

## What is Constructor and why do we use it

In JavaScript, a constructor is a special method of a class that is used to initialize objects. It is called automatically when a new instance of the class is created using the `new` keyword. The constructor allows you to set up the initial state of an object by assigning values to its properties.

### Example

```javascript
class Person {
  constructor(name, age) {
    this.name = name;
    this.age = age;
  }
}

const person1 = new Person('Alice', 30);
console.log(person1.name); // Output: Alice
console.log(person1.age);  // Output: 30
```

## What is new keyword and why do we use it

In JavaScript, the `new` keyword is used to create an instance of a class. When you use `new`, it performs the following steps:
1. Creates a new empty object.
2. Sets the prototype of the new object to the constructor function's prototype.
3. Calls the constructor function with `this` set to the new object.
4. Returns the new object.

### Example

```javascript
class Person {
  constructor(name, age) {
    this.name = name;
    this.age = age;
  }
}

const person1 = new Person('Alice', 30);
console.log(person1.name); // Output: Alice
console.log(person1.age);  // Output: 30
```

## What is instance mean

In JavaScript, an instance refers to a specific object created from a class. When you create an object using the `new` keyword and a class constructor, that object is an instance of the class. Each instance has its own set of properties and can use the methods defined in the class.

### Example

```javascript
class Person {
  constructor(name, age) {
    this.name = name;
    this.age = age;
  }
}

const person1 = new Person('Alice', 30);
const person2 = new Person('Bob', 25);

console.log(person1 instanceof Person); // Output: true
console.log(person2 instanceof Person); // Output: true
```

## What is Prototypes

In JavaScript, every object has a prototype. A prototype is an object from which other objects inherit properties and methods. Prototypes allow you to add methods and properties to all instances of a class or constructor function.

### Example

```javascript
class Person {
  constructor(name, age) {
    this.name = name;
    this.age = age;
  }
}

Person.prototype.greet = function() {
  console.log(`Hello, my name is ${this.name} and I am ${this.age} years old.`);
};

const person1 = new Person('Alice', 30);
person1.greet(); // Output: Hello, my name is Alice and I am 30 years old.
```

## Can we use prototypes with any objects like arrays, strings, etc.

Yes, in JavaScript, you can use prototypes with built-in objects like arrays, strings, and others. This allows you to add custom methods to these objects, which will be available to all instances of that object type.

### Example

```javascript
Array.prototype.first = function() {
  return this[0];
};

const numbers = [1, 2, 3, 4, 5];
console.log(numbers.first()); // Output: 1
```

## Prototype Methods

Prototype methods are functions that are added to the prototype of a constructor function or class. These methods are available to all instances of the class or constructor function.

### Example

```javascript
class Person {
  constructor(name, age) {
    this.name = name;
    this.age = age;
  }
}

Person.prototype.greet = function() {
  console.log(`Hello, my name is ${this.name} and I am ${this.age} years old.`);
};

const person1 = new Person('Alice', 30);
const person2 = new Person('Bob', 25);

person1.greet(); // Output: Hello, my name is Alice and I am 30 years old.
person2.greet(); // Output: Hello, my name is Bob and I am 25 years old.
```

## prototype chain

In JavaScript, the prototype chain is a mechanism by which objects inherit properties and methods from other objects. When you try to access a property or method on an object, JavaScript will first look for it on the object itself. If it doesn't find it, it will look up the prototype chain until it finds the property or reaches the end of the chain (usually `Object.prototype`).

### Example

```javascript
class Person {
  constructor(name, age) {
    this.name = name;
    this.age = age;
  }
}

Person.prototype.greet = function() {
  console.log(`Hello, my name is ${this.name} and I am ${this.age} years old.`);
};

const person1 = new Person('Alice', 30);
console.log(person1.toString()); // Output: [object Object] (inherited from Object.prototype)
person1.greet(); // Output: Hello, my name is Alice and I am 30 years old.
```

## __proto__ vs prototype

In JavaScript, `__proto__` is a reference to the prototype of an object, while `prototype` is a property of a constructor function that is used to build the `__proto__` of instances created by that constructor.

### Example

```javascript
function Person(name, age) {
  this.name = name;
  this.age = age;
}

Person.prototype.greet = function() {
  console.log(`Hello, my name is ${this.name} and I am ${this.age} years old.`);
};

const person1 = new Person('Alice', 30);
console.log(person1.__proto__ === Person.prototype); // Output: true
```
### Key Points

- `__proto__` is an internal property of an object that points to the prototype from which the object inherits.
- `prototype` is a property of a constructor function that is used to set the `__proto__` of instances created by that constructor.
- Changing the `prototype` of a constructor function will affect all instances created after the change, but not the existing instances.
- Modifying `__proto__` directly is generally discouraged in favor of using `Object.create` or `Object.setPrototypeOf`.

## Object.getPrototypeOf and Object.setPrototypeOf

`Object.getPrototypeOf` is a method that returns the prototype of a given object, while `Object.setPrototypeOf` is a method that sets the prototype of a given object.

### Example

```javascript
const obj = {};
const proto = { greet() { console.log('Hello!'); } };

Object.setPrototypeOf(obj, proto);
console.log(Object.getPrototypeOf(obj) === proto); // Output: true
obj.greet(); // Output: Hello!
```

## Instance methods

Instance methods are functions that are defined on the prototype of a class or constructor function and are available to all instances of that class.

### Example

```javascript
class Person {
  constructor(name, age) {
    this.name = name;
    this.age = age;
  }

  greet() {
    console.log(`Hello, my name is ${this.name} and I am ${this.age} years old.`);
  }
}

const person1 = new Person('Alice', 30);
person1.greet(); // Output: Hello, my name is Alice and I am 30 years old.
```

## Static methods

Static methods are functions that are defined on the class itself, rather than on the prototype, and are called on the class rather than on instances of the class.

### Example

```javascript
class Person {
  constructor(name, age) {
    this.name = name;
    this.age = age;
  }

  greet() {
    console.log(`Hello, my name is ${this.name} and I am ${this.age} years old.`);
  }

  static species() {
    return 'Homo sapiens';
  }
}

console.log(Person.species()); // Output: Homo sapiens
const person1 = new Person('Alice', 30);
// person1.species(); // Error: person1.species is not a function
```

## Static properties

Static properties are properties that are defined on the class itself, rather than on the prototype, and are accessed on the class rather than on instances of the class.

### Example

```javascript
class Person {
  constructor(name, age) {
    this.name = name;
    this.age = age;
  }

  greet() {
    console.log(`Hello, my name is ${this.name} and I am ${this.age} years old.`);
  }

  static species = 'Homo sapiens';
}

console.log(Person.species); // Output: Homo sapiens
const person1 = new Person('Alice', 30);
// console.log(person1.species); // Error: person1.species is undefined
```

## Getters and Setters

Getters and setters are special methods that allow you to define how to access and modify the properties of an object. A getter is used to retrieve the value of a property, while a setter is used to set the value of a property.

### Example

```javascript
class Person {
  constructor(name, age) {
    this._name = name;
    this._age = age;
  }

  get name() {
    return this._name;
  }

  set name(newName) {
    this._name = newName;
  }

  get age() {
    return this._age;
  }

  set age(newAge) {
    this._age = newAge;
  }
}

const person1 = new Person('Alice', 30);
console.log(person1.name); // Output: Alice
person1.name = 'Bob';
console.log(person1.name); // Output: Bob
console.log(person1.age); // Output: 30
person1.age = 35;
console.log(person1.age); // Output: 35
```

## Private fields

Private fields are properties that are only accessible within the class they are defined in. They are prefixed with a `#` symbol.

### Example

```javascript
class Person {
  #name;
  #age;

  constructor(name, age) {
    this.#name = name;
    this.#age = age;
  }

  getName() {
    return this.#name;
  }

  setName(newName) {
    this.#name = newName;
  }

  getAge() {
    return this.#age;
  }

  setAge(newAge) {
    this.#age = newAge;
  }
}

const person1 = new Person('Alice', 30);
console.log(person1.getName()); // Output: Alice
person1.setName('Bob');
console.log(person1.getName()); // Output: Bob
console.log(person1.getAge()); // Output: 30
person1.setAge(35);
console.log(person1.getAge()); // Output: 35
// console.log(person1.#name); // Error: Private field '#name' must be declared in an enclosing class
```

## Public fields

Public fields are properties that are accessible from anywhere, both inside and outside the class. They are defined without any special prefix.

### Example

```javascript
class Person {
  name;
  age;

  constructor(name, age) {
    this.name = name;
    this.age = age;
  }
}

const person1 = new Person('Alice', 30);
console.log(person1.name); // Output: Alice
console.log(person1.age); // Output: 30
person1.name = 'Bob';
person1.age = 35;
console.log(person1.name); // Output: Bob
console.log(person1.age); // Output: 35
```

## Inheritance

Inheritance allows a class to inherit properties and methods from another class. The class that is inherited from is called the parent class (or superclass), and the class that inherits is called the child class (or subclass).

### Example

```javascript
class Person {
  constructor(name, age) {
    this.name = name;
    this.age = age;
  }
}

class Student extends Person {
  constructor(name, age, grade) {
    super(name, age);
    this.grade = grade;
  }
}

const student1 = new Student('Alice', 20, 'A');
console.log(student1.name); // Output: Alice
console.log(student1.age); // Output: 20
console.log(student1.grade); // Output: A
```

## extends and super

The `extends` keyword is used to create a class that is a child of another class. The `super` keyword is used to call the constructor of the parent class.

### Example

```javascript
class Person {
  constructor(name, age) {
    this.name = name;
    this.age = age;
  }
}

class Student extends Person {
  constructor(name, age, grade) {
    super(name, age); // Calls the constructor of the parent class
    this.grade = grade;
  }
}

const student1 = new Student('Alice', 20, 'A');
console.log(student1.name); // Output: Alice
console.log(student1.age); // Output: 20
console.log(student1.grade); // Output: A
```

## polymorphism

Polymorphism allows objects of different classes to be treated as objects of a common superclass. It is often used to implement methods that can work with objects of different types.

### Example

```javascript
class Person {
  constructor(name, age) {
    this.name = name;
    this.age = age;
  }

  greet() {
    console.log(`Hello, my name is ${this.name}`);
  }
}

class Student extends Person {
  constructor(name, age, grade) {
    super(name, age);
    this.grade = grade;
  }

  greet() {
    console.log(`Hello, my name is ${this.name} and I am in grade ${this.grade}`);
  }
}

const person1 = new Person('Alice', 30);
const student1 = new Student('Bob', 20, 'A');

person1.greet(); // Output: Hello, my name is Alice
student1.greet(); // Output: Hello, my name is Bob and I am in grade A
```

## Encapsulation

Encapsulation is the concept of restricting access to certain properties and methods of an object, making them private and only accessible through public methods.

### Example

```javascript
class Person {
  #name;
  #age;

  constructor(name, age) {
    this.#name = name;
    this.#age = age;
  }

  getName() {
    return this.#name;
  }

  getAge() {
    return this.#age;
  }

  setName(name) {
    this.#name = name;
  }

  setAge(age) {
    this.#age = age;
  }
}

const person1 = new Person('Alice', 30);
console.log(person1.getName()); // Output: Alice
console.log(person1.getAge()); // Output: 30
person1.setName('Bob');
person1.setAge(35);
console.log(person1.getName()); // Output: Bob
console.log(person1.getAge()); // Output: 35
```

## Abstraction

Abstraction is the concept of hiding the complex implementation details of a class and exposing only the necessary functionalities to the outside world.

### Example

```javascript
class Person {
  #name;
  #age;

  constructor(name, age) {
    this.#name = name;
    this.#age = age;
  }

  getDetails() {
    return `Name: ${this.#name}, Age: ${this.#age}`;
  }
}

const person1 = new Person('Alice', 30);
console.log(person1.getDetails()); // Output: Name: Alice, Age: 30
```

## Composition vs inheritance

Composition and inheritance are two ways to reuse code in object-oriented programming. Inheritance allows a class to inherit properties and methods from a parent class, while composition involves building classes using instances of other classes.

### Example of Inheritance

```javascript
class Engine {
  start() {
    console.log('Engine started');
  }
}

class Car extends Engine {
  drive() {
    console.log('Car is driving');
  }
}

const myCar = new Car();
myCar.start(); // Output: Engine started
myCar.drive(); // Output: Car is driving
```

### Example of Composition

```javascript
class Engine {
  start() {
    console.log('Engine started');
  }
}

class Car {
  constructor() {
    this.engine = new Engine();
  }

  drive() {
    console.log('Car is driving');
  }
}

const myCar = new Car();
myCar.engine.start(); // Output: Engine started
myCar.drive(); // Output: Car is driving
```

# `this` Keyword

## Global `this`

In the global context, `this` refers to the global object. In a browser, it is `window`, and in Node.js, it is `global`.

### Example

```javascript
console.log(this); // In browser: Window, In Node.js: global
```
## `this` inside functions

In a regular function, `this` refers to the object that called the function. If the function is called in the global context, `this` refers to the global object.

### Example

```javascript
function showThis() {
  console.log(this);
}

showThis(); // In browser: Window, In Node.js: global
```

## `this` inside objects

In an object method, `this` refers to the object that owns the method.

### Example

```javascript
const person = {
  name: 'Alice',
  greet() {
    console.log(this.name);
  }
};

person.greet(); // Output: Alice
```

## `this` inside methods

In a class method, `this` refers to the instance of the class that called the method.

### Example

```javascript
class Person {
  constructor(name) {
    this.name = name;
  }

  greet() {
    console.log(this.name);
  }
}

const person1 = new Person('Alice');
person1.greet(); // Output: Alice
```

## `this` inside arrow functions

In an arrow function, `this` is lexically bound, meaning it uses `this` from the surrounding non-arrow function or global context.

### Example

```javascript
const person = {
  name: 'Alice',
  greet: () => {
    console.log(this.name);
  }
};

person.greet(); // Output: undefined (in strict mode) or global object's name property
```

## Constructor `this`

In a constructor function, `this` refers to the newly created instance of the object.

### Example

```javascript
function Person(name) {
  this.name = name;
}

const person1 = new Person('Alice');
console.log(person1.name); // Output: Alice
```

## call(), apply() and bind()

These methods allow you to explicitly set the value of `this` when invoking a function.

- `call(thisArg, arg1, arg2, ...)` calls a function with a given `this` value and arguments provided individually.
- `apply(thisArg, [argsArray])` calls a function with a given `this` value and arguments provided as an array.
- `bind(thisArg, arg1, arg2, ...)` returns a new function with a given `this` value and optional arguments prepended.

### Example

```javascript
function greet(greeting) {
  console.log(`${greeting}, my name is ${this.name}`);
}

const person = { name: 'Alice' };

greet.call(person, 'Hello'); // Output: Hello, my name is Alice
greet.apply(person, ['Hi']); // Output: Hi, my name is Alice
const boundGreet = greet.bind(person, 'Hey');
boundGreet(); // Output: Hey, my name is Alice
```

## Losing `this`

In JavaScript, it's common to lose the intended value of `this` when passing methods as callbacks or when extracting them from objects.

### Example

```javascript
const person = {
  name: 'Alice',
  greet() {
    console.log(this.name);
  }
};

const greet = person.greet;
greet(); // Output: undefined (in strict mode) or global object's name property
```

### Solution

You can solve this problem by using `bind` to explicitly set the value of `this` or by using an arrow function.

#### Using `bind`

```javascript
const greet = person.greet.bind(person);
greet(); // Output: Alice
```

#### Using an arrow function

```javascript
const greet = () => person.greet();
greet(); // Output: Alice
```

## Explicit vs Implicit binding

In JavaScript, `this` can be bound explicitly using `call`, `apply`, or `bind`, or implicitly through the object that is calling the function.

### Example

```javascript
const person = {
  name: 'Alice',
  greet() {
    console.log(this.name);
  }
};

// Implicit binding
person.greet(); // Output: Alice

// Explicit binding
const greet = person.greet;
greet.call(person); // Output: Alice
```

## New binding

When a function is used as a constructor with the `new` keyword, `this` inside the function refers to the newly created object.

### Example

```javascript
function Person(name) {
  this.name = name;
}

const person1 = new Person('Alice');
console.log(person1.name); // Output: Alice
```

# Advanced Functions

## Closures

A closure is a function that has access to its own scope, the outer function's scope, and the global scope, even after the outer function has returned.

### Example

```javascript
function outerFunction(outerVariable) {
  return function innerFunction(innerVariable) {
    console.log('Outer Variable: ' + outerVariable);
    console.log('Inner Variable: ' + innerVariable);
  };
}

const closure = outerFunction('outside');
closure('inside');
// Output:
// Outer Variable: outside
// Inner Variable: inside
```

## Higher-Order Functions

A higher-order function is a function that either takes one or more functions as arguments or returns a function as its result.

### Example

```javascript
function higherOrderFunction(callback) {
  return function() {
    console.log('Before callback');
    callback();
    console.log('After callback');
  };
}

function sayHello() {
  console.log('Hello!');
}

const wrappedFunction = higherOrderFunction(sayHello);
wrappedFunction();
// Output:
// Before callback
// Hello!
// After callback
```

## Currying

Currying is a technique in functional programming where a function with multiple arguments is transformed into a sequence of functions, each taking a single argument.

### Example

```javascript
function multiply(a) {
  return function(b) {
    return a * b;
  };
}

const double = multiply(2);
console.log(double(5)); // Output: 10
```

## Partial application

Partial application is a technique in functional programming where a function is transformed into another function with some of its arguments fixed.

### Example

```javascript
function multiply(a, b) {
  return a * b;
}

function partialMultiplyBy2(b) {
  return multiply(2, b);
}

console.log(partialMultiplyBy2(5)); // Output: 10
```

## Function composition

Function composition is a technique in functional programming where multiple functions are combined to produce a new function.

### Example

```javascript
function add2(x) {
  return x + 2;
}

function multiplyBy3(x) {
  return x * 3;
}

function compose(f, g) {
  return function(x) {
    return f(g(x));
  };
}

const add2ThenMultiplyBy3 = compose(multiplyBy3, add2);
console.log(add2ThenMultiplyBy3(5)); // Output: 21
```

## Memoization

Memoization is an optimization technique in functional programming where the results of expensive function calls are cached and returned when the same inputs occur again.

### Example

```javascript
function memoize(fn) {
  const cache = {};
  return function(...args) {
    const key = JSON.stringify(args);
    if (cache[key]) {
      return cache[key];
    }
    const result = fn(...args);
    cache[key] = result;
    return result;
  };
}

function slowAdd(a, b) {
  console.log('Computing...');
  return a + b;
}

const memoizedAdd = memoize(slowAdd);
console.log(memoizedAdd(2, 3)); // Computing... 5
console.log(memoizedAdd(2, 3)); // 5 (cached)
```

## IIFE

IIFE (Immediately Invoked Function Expression) is a JavaScript function that is executed immediately after it is defined.

### Example

```javascript
(function() {
  console.log('This is an IIFE');
})();
// Output:
// This is an IIFE
```

## Callback patterns

Callback patterns in JavaScript involve passing a function as an argument to another function, which is then invoked inside the outer function to complete some kind of routine or action.

### Example

```javascript
function fetchData(callback) {
  setTimeout(() => {
    const data = { name: 'John', age: 30 };
    callback(data);
  }, 1000);
}

function handleData(data) {
  console.log('Received data:', data);
}

fetchData(handleData);
// Output (after 1 second):
// Received data: { name: 'John', age: 30 }
```

## Factory functions

Factory functions are functions that return new objects. They are an alternative to using classes for creating multiple similar objects.

### Example

```javascript
function createPerson(name, age) {
  return {
    name,
    age,
    greet() {
      console.log(`Hello, my name is ${name} and I am ${age} years old.`);
    }
  };
}

const person1 = createPerson('Alice', 25);
const person2 = createPerson('Bob', 30);

person1.greet(); // Output: Hello, my name is Alice and I am 25 years old.
person2.greet(); // Output: Hello, my name is Bob and I am 30 years old.
```

## Function decorators

Function decorators are higher-order functions that take a function as an argument and return a new function with extended or modified behavior.

### Example

```javascript
function logExecution(fn) {
  return function(...args) {
    console.log(`Executing function with arguments: ${args}`);
    const result = fn(...args);
    console.log(`Function result: ${result}`);
    return result;
  };
}

function add(a, b) {
  return a + b;
}

const decoratedAdd = logExecution(add);
decoratedAdd(2, 3);
// Output:
// Executing function with arguments: 2,3
// Function result: 5
```

## call(), apply() and bind()

These methods are used to control the `this` context of functions in JavaScript.

### Example

```javascript
const person = {
  name: 'Alice',
  greet(greeting) {
    console.log(`${greeting}, my name is ${this.name}`);
  }
};

const anotherPerson = { name: 'Bob' };

// Using call
person.greet.call(anotherPerson, 'Hello'); // Output: Hello, my name is Bob

// Using apply
person.greet.apply(anotherPerson, ['Hi']); // Output: Hi, my name is Bob

// Using bind
const boundGreet = person.greet.bind(anotherPerson);
boundGreet('Hey'); // Output: Hey, my name is Bob
```

# Debouncing & Throttling

## What is debouncing?

Debouncing is a technique used to limit the rate at which a function is executed. It ensures that the function is only called after a certain amount of time has passed since the last time it was invoked. This is particularly useful for handling events like window resizing, scrolling, or input changes.

### Example

```javascript
function debounce(fn, delay) {
  let timeoutId;
  return function(...args) {
    clearTimeout(timeoutId);
    timeoutId = setTimeout(() => {
      fn(...args);
    }, delay);
  };
}

function handleResize() {
  console.log('Window resized');
}

const debouncedResize = debounce(handleResize, 500);
window.addEventListener('resize', debouncedResize);
```

## Implement debounce from scratch

### Example

```javascript
function customDebounce(fn, delay) {
  let timeoutId;
  return function(...args) {
    if (timeoutId) {
      clearTimeout(timeoutId);
    }
    timeoutId = setTimeout(() => {
      fn(...args);
    }, delay);
  };
}

function handleScroll() {
  console.log('Window scrolled');
}

const debouncedScroll = customDebounce(handleScroll, 300);
window.addEventListener('scroll', debouncedScroll);
```

## Debounce with `setTimeout`

### Example

```javascript
function debounceWithSetTimeout(fn, delay) {
  let timeoutId;
  return function(...args) {
    clearTimeout(timeoutId);
    timeoutId = setTimeout(() => {
      fn(...args);
    }, delay);
  };
}

function handleInput() {
  console.log('Input event triggered');
}

const debouncedInput = debounceWithSetTimeout(handleInput, 400);
document.querySelector('input').addEventListener('input', debouncedInput);
```

## Debounce API search

### Example

```javascript
function debounceApiSearch(fn, delay) {
  let timeoutId;
  return function(...args) {
    clearTimeout(timeoutId);
    timeoutId = setTimeout(() => {
      fn(...args);
    }, delay);
  };
}

function handleSearch() {
  console.log('API search triggered');
}

const debouncedSearch = debounceApiSearch(handleSearch, 500);
document.querySelector('input').addEventListener('input', debouncedSearch);
```

## Debounce input events

### Example

```javascript
function debounceInput(fn, delay) {
  let timeoutId;
  return function(...args) {
    clearTimeout(timeoutId);
    timeoutId = setTimeout(() => {
      fn(...args);
    }, delay);
  };
}

function handleInputEvent() {
  console.log('Input event debounced');
}

const debouncedInputEvent = debounceInput(handleInputEvent, 300);
document.querySelector('input').addEventListener('input', debouncedInputEvent);
```

## Debounce resize events

### Example

```javascript
function debounceResize(fn, delay) {
  let timeoutId;
  return function(...args) {
    clearTimeout(timeoutId);
    timeoutId = setTimeout(() => {
      fn(...args);
    }, delay);
  };
}

function handleResizeEvent() {
  console.log('Resize event debounced');
}

const debouncedResizeEvent = debounceResize(handleResizeEvent, 300);
window.addEventListener('resize', debouncedResizeEvent);
```

## What is Throttling?

Throttling is a technique used to control the rate at which a function is executed. Unlike debouncing, which delays the execution until after a certain period of inactivity, throttling ensures that a function is called at most once in a specified time interval. This is particularly useful for events that fire continuously, such as scrolling or resizing, where you want to limit the number of times a function is executed to improve performance.

### Example

```javascript
function throttle(fn, limit) {
  let lastCall = 0;
  return function(...args) {
    const now = Date.now();
    if (now - lastCall >= limit) {
      lastCall = now;
      fn(...args);
    }
  };
}

function handleScrollEvent() {
  console.log('Scroll event throttled');
}

const throttledScrollEvent = throttle(handleScrollEvent, 300);
window.addEventListener('scroll', throttledScrollEvent);
```

## Implement throttle from scratch

### Example

```javascript
function throttleFromScratch(fn, limit) {
  let lastCall = 0;
  return function(...args) {
    const now = Date.now();
    if (now - lastCall >= limit) {
      lastCall = now;
      fn(...args);
    }
  };
}

function handleCustomScrollEvent() {
  console.log('Custom scroll event throttled');
}

const customThrottledScrollEvent = throttleFromScratch(handleCustomScrollEvent, 300);
window.addEventListener('scroll', customThrottledScrollEvent);
```

## Throttle scroll events

### Example

```javascript
const throttledScroll = throttle(() => {
  console.log('Scroll event throttled');
}, 300);

window.addEventListener('scroll', throttledScroll);
```

## Throttle mouse events

### Example

```javascript
const throttledMouseMove = throttle((event) => {
  console.log('Mouse move event throttled', event);
}, 300);

window.addEventListener('mousemove', throttledMouseMove);
```

## Debounce vs throttle

Debouncing and throttling are both techniques used to control the rate at which a function is executed, but they work in different ways:

- **Debounce**: Delays the execution of a function until after a specified period of inactivity. It is useful for scenarios where you want to ensure that a function is only called once after a series of rapid events, such as form input or window resizing.
- **Throttle**: Ensures that a function is called at most once in a specified time interval. It is useful for scenarios where you want to limit the rate of execution for continuously firing events, such as scrolling or mouse movement.

## Leading execution

Leading execution refers to the scenario where a throttled function is executed immediately on the first call, rather than waiting for the specified time interval to elapse. This can be useful when you want the function to respond immediately to the first event, but still limit the rate of subsequent executions.

### Example

```javascript
function throttleLeading(fn, limit) {
  let lastCall = 0;
  return function(...args) {
    const now = Date.now();
    if (now - lastCall >= limit) {
      lastCall = now;
      fn(...args);
    }
  };
}

function handleLeadingScrollEvent() {
  console.log('Leading scroll event throttled');
}

const leadingThrottledScrollEvent = throttleLeading(handleLeadingScrollEvent, 300);
window.addEventListener('scroll', leadingThrottledScrollEvent);
```

## Trailing execution

Trailing execution refers to the scenario where a throttled function is executed after the specified time interval has elapsed since the last call. This can be useful when you want to ensure that the function responds to the final event in a series of rapid events, rather than the first one.

### Example

```javascript
function throttleTrailing(fn, limit) {
  let lastCall = 0;
  let timeoutId;
  return function(...args) {
    const now = Date.now();
    const remaining = limit - (now - lastCall);
    clearTimeout(timeoutId);
    if (remaining <= 0) {
      lastCall = now;
      fn(...args);
    } else {
      timeoutId = setTimeout(() => {
        lastCall = Date.now();
        fn(...args);
      }, remaining);
    }
  };
}

function handleTrailingScrollEvent() {
  console.log('Trailing scroll event throttled');
}

const trailingThrottledScrollEvent = throttleTrailing(handleTrailingScrollEvent, 300);
window.addEventListener('scroll', trailingThrottledScrollEvent);
```

## Cancelable debounce

Cancelable debounce refers to a debounce function that can be canceled before it executes. This is useful when you want to prevent the debounced function from running if certain conditions are met before the delay period ends.

### Example

```javascript
function debounceCancelable(fn, delay) {
  let timeoutId;
  const debounced = function(...args) {
    clearTimeout(timeoutId);
    timeoutId = setTimeout(() => {
      fn(...args);
    }, delay);
  };
  debounced.cancel = function() {
    clearTimeout(timeoutId);
  };
  return debounced;
}

function handleInputEvent() {
  console.log('Input event debounced');
}

const debouncedInputEvent = debounceCancelable(handleInputEvent, 300);
window.addEventListener('input', debouncedInputEvent);

// To cancel the debounced function
// debouncedInputEvent.cancel();
```

## Cancelable throttle

Cancelable throttle refers to a throttle function that can be canceled before it executes. This is useful when you want to prevent the throttled function from running if certain conditions are met before the time interval elapses.

### Example

```javascript
function throttleCancelable(fn, limit) {
  let lastCall = 0;
  let timeoutId;
  const throttled = function(...args) {
    const now = Date.now();
    const remaining = limit - (now - lastCall);
    clearTimeout(timeoutId);
    if (remaining <= 0) {
      lastCall = now;
      fn(...args);
    } else {
      timeoutId = setTimeout(() => {
        lastCall = Date.now();
        fn(...args);
      }, remaining);
    }
  };
  throttled.cancel = function() {
    clearTimeout(timeoutId);
  };
  return throttled;
}

function handleCancelableScrollEvent() {
  console.log('Cancelable scroll event throttled');
}

const cancelableThrottledScrollEvent = throttleCancelable(handleCancelableScrollEvent, 300);
window.addEventListener('scroll', cancelableThrottledScrollEvent);

// To cancel the throttled function
// cancelableThrottledScrollEvent.cancel();
```

# Execution Context & JavaScript Internals

## Execution context

Execution context is the environment in which JavaScript code is executed. It contains information about the variables, functions, and the value of `this` that are accessible at a particular point in the code. There are three main types of execution context in JavaScript:

1. **Global Execution Context**: This is the default context in which code runs initially. It creates a global object (`window` in browsers) and sets `this` to point to that global object.
2. **Function Execution Context**: Created whenever a function is invoked. It contains the function's arguments, local variables, and the value of `this` specific to that function.
3. **Eval Execution Context**: Created by the `eval` function, though its use is generally discouraged due to security and performance concerns.

## Global Execution Context

The global execution context is the default context in which JavaScript code runs initially. It creates a global object (`window` in browsers) and sets `this` to point to that global object. All global variables and functions are part of this context. There is only one global execution context in a JavaScript program, and it remains active throughout the lifetime of the application.

## Function Execution Context

A function execution context is created whenever a function is invoked. It contains the function's arguments, local variables, and the value of `this` specific to that function. Each function call has its own execution context, which is pushed onto the execution context stack when the function is invoked and popped off when the function completes execution. This ensures that each function has its own scope and does not interfere with other functions' execution contexts.

## Creation phase and Execution phase

The creation phase is the first phase of the execution context lifecycle. During this phase, the JavaScript engine scans the code and allocates memory for variables, functions, and the `this` keyword. Variables are initialized with `undefined`, and functions are stored in memory.

The execution phase is the second phase, where the code is actually executed line by line. During this phase, the values of variables are assigned, functions are invoked, and the `this` keyword is resolved.

## Lexical Environment

A lexical environment is the structure that holds identifier-variable mapping. In other words, it is a mechanism to store variables and their values within a particular scope. Each execution context has a lexical environment associated with it, which consists of:

1. **Environment Record**: Stores the actual variable and function declarations.
2. **Reference to the Outer Lexical Environment**: Points to the lexical environment of the parent scope, enabling scope chain resolution.

Lexical environments are crucial for understanding closures, as they allow functions to access variables from their outer scopes even after those outer functions have finished execution.

## Variable Environment

The variable environment is a component of the lexical environment that specifically deals with variable declarations and their values. It keeps track of all the variables within a particular scope and their current values. During the creation phase of the execution context, memory is allocated for these variables, and they are initialized with `undefined`. During the execution phase, the actual values are assigned to the variables.

## Environment Record

The environment record is a part of the lexical environment that stores the actual variable and function declarations. It acts as a repository for all the identifiers within a particular scope and their corresponding values. The environment record is used by the JavaScript engine to resolve variable and function references during code execution.

## Scope Chain

The scope chain is the mechanism by which the JavaScript engine resolves variable and function references. It consists of the current lexical environment and all its outer lexical environments, forming a chain that the engine traverses to find the requested identifier. The scope chain ensures that variables are accessed in the correct scope and allows for nested functions to access variables from their parent scopes.

## Hoisting

Hoisting is a JavaScript mechanism where variable and function declarations are moved to the top of their containing scope during the creation phase of the execution context. This means that you can use variables and functions before they are actually declared in the code. However, only the declarations are hoisted, not the initializations. Variables declared with `var` are hoisted and initialized with `undefined`, while `let` and `const` declarations are hoisted but not initialized, leading to a temporal dead zone until the declaration is encountered. Functions declared using function declarations are fully hoisted, meaning both the declaration and the definition are moved to the top of the scope.

## Function hoisting

Function hoisting refers to the behavior in JavaScript where function declarations are moved to the top of their containing scope during the creation phase of the execution context. This allows functions to be called before they are defined in the code. It is important to note that only function declarations are hoisted, not function expressions. For example:

```javascript
console.log(foo()); // Output: "Hello"

function foo() {
  return "Hello";
}
```

In the above example, the function `foo` can be called before its declaration due to function hoisting. However, if `foo` were defined as a function expression, it would not be hoisted:

```javascript
console.log(bar()); // Error: bar is not a function

var bar = function() {
  return "Hello";
};
```

## Variable hoisting

Variable hoisting refers to the behavior in JavaScript where variable declarations are moved to the top of their containing scope during the creation phase of the execution context. This allows variables to be referenced before they are declared, but their values will be `undefined` until the actual initialization is encountered. For example:

```javascript
console.log(x); // Output: undefined
var x = 5;
console.log(x); // Output: 5
```

In the above example, the variable `x` is hoisted to the top of its scope, but its initialization with the value `5` occurs at the original line of code. Variables declared with `let` and `const` are also hoisted, but they are not initialized, leading to a temporal dead zone until the declaration is encountered:

```javascript
console.log(y); // ReferenceError: Cannot access 'y' before initialization
let y = 10;
```

## TDZ (Temporal Dead Zone)

The Temporal Dead Zone (TDZ) is the period between the entering of the scope and the actual declaration of a variable using `let` or `const`. During this period, any attempt to access the variable will result in a `ReferenceError`. This concept helps prevent the use of variables before they are properly declared and initialized. For example:

```javascript
console.log(a); // ReferenceError: Cannot access 'a' before initialization
let a = 20;
```

## Call stack

The call stack is a data structure used by the JavaScript engine to keep track of function calls. It operates in a last-in, first-out (LIFO) manner, meaning the most recently called function is the first one to be executed and removed from the stack. When a function is called, it is pushed onto the stack, and when it returns, it is popped off the stack. For example:

```javascript
function first() {
  console.log("First function");
  second();
}

function second() {
  console.log("Second function");
  third();
}

function third() {
  console.log("Third function");
}

first();
```

In the above example, the call stack will look like this during execution:
1. `first` is called and pushed onto the stack.
2. `second` is called from within `first` and pushed onto the stack.
3. `third` is called from within `second` and pushed onto the stack.
4. `third` finishes execution and is popped off the stack.
5. `second` finishes execution and is popped off the stack.
6. `first` finishes execution and is popped off the stack.

## Heap

The heap is a region of memory used for dynamic memory allocation in JavaScript. Unlike the call stack, which operates in a LIFO manner, the heap allows for the storage of objects and data that need to persist beyond the execution of a single function. Memory in the heap is managed by the JavaScript engine's garbage collector, which automatically frees up memory that is no longer referenced. For example:

```javascript
let obj = {
  name: "John",
  age: 30
};
```

In the above example, the object `obj` is allocated in the heap, and it will remain there until it is no longer referenced and the garbage collector cleans it up.

## Garbage Collection

Garbage collection is the process by which the JavaScript engine automatically identifies and frees up memory that is no longer in use. This helps prevent memory leaks and ensures efficient memory management. The garbage collector typically uses algorithms like reference counting and mark-and-sweep to determine which objects are no longer reachable and can be safely removed from the heap. For example:

```javascript
let obj = {
  name: "John",
  age: 30
};

// Later in the code
obj = null; // The object is now eligible for garbage collection
```

## Memory Management

Memory management in JavaScript involves the efficient allocation and deallocation of memory to ensure optimal performance and prevent memory leaks. The JavaScript engine automatically handles memory management through the use of the call stack, heap, and garbage collection. Developers can aid memory management by:

- Avoiding global variables that persist for the lifetime of the application.
- Nullifying references to objects that are no longer needed.
- Being mindful of closures that may unintentionally retain references to outer scope variables.

Proper memory management helps maintain application performance and prevents excessive memory consumption.

# Event Loop - Deep Dive

The event loop is a fundamental concept in JavaScript that allows for non-blocking asynchronous operations. It continuously monitors the call stack and the task queue, ensuring that functions are executed in the correct order. When the call stack is empty, the event loop picks the next task from the task queue and pushes it onto the stack for execution. This mechanism enables JavaScript to handle asynchronous events like I/O operations, timers, and user interactions efficiently.

## Call Stack

The call stack is a data structure that keeps track of function calls in a LIFO (Last In, First Out) manner. When a function is invoked, it is pushed onto the stack, and when the function completes, it is popped off the stack. This ensures that functions are executed in the correct order and that the JavaScript engine knows where to return after a function finishes execution. For example:

## Web APIs

Web APIs are provided by the browser (or the environment in which JavaScript is running) and allow JavaScript to perform tasks that are not natively part of the language, such as making HTTP requests, manipulating the DOM, or setting timers. When a Web API is called, it runs independently of the call stack, and once it completes, it places the callback function in the task queue to be executed by the event loop. For example:

```javascript
setTimeout(() => {
  console.log("This runs after 2 seconds");
}, 2000);
```

## Macrotasks

Macrotasks are tasks that are scheduled to run after the current execution context and all microtasks have been completed. Examples of macrotasks include `setTimeout`, `setInterval`, and I/O operations. The event loop processes macrotasks one at a time, ensuring that the call stack is empty before executing the next macrotask. For example:

```javascript
setTimeout(() => {
  console.log("This is a macrotask");
}, 0);
```

## Microtasks

Microtasks are tasks that are scheduled to run immediately after the current execution context and before any macrotasks. Examples of microtasks include `Promise` callbacks and `MutationObserver` callbacks. The event loop ensures that all microtasks are completed before moving on to the next macrotask. For example:

```javascript
Promise.resolve().then(() => {
  console.log("This is a microtask");
});
```

## Callback queue

The callback queue (also known as the task queue) is a data structure that holds callbacks from Web APIs that are ready to be executed. When the call stack is empty, the event loop picks the next callback from the callback queue and pushes it onto the call stack for execution. This ensures that asynchronous operations are handled efficiently without blocking the main thread. For example:

```javascript
setTimeout(() => {
  console.log("This callback is in the callback queue");
}, 0);
```

## Microtask queue

The microtask queue is a data structure that holds microtasks that are ready to be executed. Microtasks are executed immediately after the current execution context and before any macrotasks. This ensures that microtasks have a higher priority than macrotasks. For example:

```javascript
Promise.resolve().then(() => {
  console.log("This microtask is in the microtask queue");
});
```

## setTimeout and setInterval

`setTimeout` and `setInterval` are Web API functions that allow you to schedule code execution after a specified delay or at regular intervals, respectively. `setTimeout` executes the callback function once after the delay, while `setInterval` executes the callback function repeatedly at the specified interval. Both functions place their callbacks in the callback queue, which are then picked up by the event loop when the call stack is empty. For example:

```javascript
setTimeout(() => {
  console.log("This runs after 2 seconds");
}, 2000);

setInterval(() => {
  console.log("This runs every 3 seconds");
}, 3000);
```

## Promises

Promises are objects that represent the eventual completion (or failure) of an asynchronous operation and its resulting value. A promise can be in one of three states: `pending`, `fulfilled`, or `rejected`. Promises provide a cleaner way to handle asynchronous operations compared to traditional callback-based approaches. For example:

```javascript
const myPromise = new Promise((resolve, reject) => {
  setTimeout(() => {
    resolve("Promise resolved successfully");
  }, 2000);
});

myPromise.then((message) => {
  console.log(message);
});
```

## queueMicrotask()

`queueMicrotask` is a Web API function that allows you to schedule a microtask to be executed after the current execution context and before any macrotasks. This ensures that the microtask has a higher priority than macrotasks. For example:

```javascript
queueMicrotask(() => {
  console.log("This microtask is scheduled using queueMicrotask");
});
```

## async/await

`async/await` is syntactic sugar built on top of promises that allows you to write asynchronous code in a more synchronous and readable manner. An `async` function always returns a promise, and the `await` keyword can be used inside an `async` function to pause its execution until the awaited promise is resolved. For example:

```javascript
async function fetchData() {
  try {
    const result = await new Promise((resolve, reject) => {
      setTimeout(() => {
        resolve("Data fetched successfully");
      }, 2000);
    });
    console.log(result);
  } catch (error) {
    console.error(error);
  }
}

fetchData();
```

## Execution order
The execution order of different asynchronous tasks in JavaScript is determined by the event loop, the call stack, and the task queues (microtask queue and macrotask queue). In general:
- Synchronous code runs first, as it is executed immediately on the call stack.
- Microtasks (e.g., promises and `queueMicrotask`) are executed next, after the current synchronous code completes but before any macrotasks.
- Macrotasks (e.g., `setTimeout` and `setInterval`) are executed last, after the microtask queue is emptied.

In summary, the order of execution is:
1. Synchronous code
2. Microtasks
3. Macrotasks

# Prototypes

## Prototype objects

In JavaScript, every object has an internal property called `[[Prototype]]`, which refers to another object. This prototype object can have its own properties and methods, and the original object can access them through the prototype chain. The `prototype` property is used primarily with constructor functions to set up inheritance. For example:

```javascript
function Person(name) {
  this.name = name;
}

Person.prototype.greet = function() {
  console.log(`Hello, my name is ${this.name}`);
};

const alice = new Person("Alice");
alice.greet(); // Output: Hello, my name is Alice
```

## Prototype inheritance

Prototype inheritance is a mechanism in JavaScript that allows objects to inherit properties and methods from other objects. This is achieved through the prototype chain. When you try to access a property or method on an object, JavaScript first looks for it on the object itself. If it is not found, it looks up the prototype chain until it finds the property or reaches the end of the chain (`null`). For example:

```javascript
function Animal(name) {
  this.name = name;
}

Animal.prototype.speak = function() {
  console.log(`${this.name} makes a sound`);
};

function Dog(name) {
  Animal.call(this, name);
}

Dog.prototype = Object.create(Animal.prototype);
Dog.prototype.constructor = Dog;

Dog.prototype.speak = function() {
  console.log(`${this.name} barks`);
};

const dog = new Dog("Rex");
dog.speak(); // Output: Rex barks
```

## Prototype chain

The prototype chain is the mechanism by which JavaScript objects inherit properties and methods from other objects. When you try to access a property or method on an object, JavaScript first looks for it on the object itself. If it is not found, it looks up the prototype chain until it finds the property or reaches the end of the chain (`null`). For example:

```javascript
function Vehicle(type) {
  this.type = type;
}

Vehicle.prototype.describe = function() {
  console.log(`This is a ${this.type}`);
};

function Car(type, brand) {
  Vehicle.call(this, type);
  this.brand = brand;
}

Car.prototype = Object.create(Vehicle.prototype);
Car.prototype.constructor = Car;

Car.prototype.describe = function() {
  console.log(`This is a ${this.brand} ${this.type}`);
};

const myCar = new Car("car", "Toyota");
myCar.describe(); // Output: This is a Toyota car
```

## Constructor prototype

In JavaScript, every function has a `prototype` property that is used to build the `[[Prototype]]` chain for objects created with that function as a constructor. The `prototype` property allows you to add properties and methods that will be shared by all instances created by the constructor. For example:

```javascript
function Person(name) {
  this.name = name;
}

Person.prototype.greet = function() {
  console.log(`Hello, my name is ${this.name}`);
};

const bob = new Person("Bob");
bob.greet(); // Output: Hello, my name is Bob
```

## Instance prototype

In JavaScript, each instance of an object created by a constructor function has an internal `[[Prototype]]` property that points to the constructor's `prototype` object. This allows instances to inherit properties and methods defined on the constructor's prototype. For example:

```javascript
function Person(name) {
  this.name = name;
}

Person.prototype.greet = function() {
  console.log(`Hello, my name is ${this.name}`);
};

const charlie = new Person("Charlie");
charlie.greet(); // Output: Hello, my name is Charlie
```

## `prototype` property

The `prototype` property of a constructor function is an object that is shared among all instances created by that constructor. It allows you to define methods and properties that should be available to all instances. For example:

```javascript
function Animal(name) {
  this.name = name;
}

Animal.prototype.speak = function() {
  console.log(`${this.name} makes a sound`);
};

const dog = new Animal("Dog");
dog.speak(); // Output: Dog makes a sound
```

## __proto__

The `__proto__` property of an object points to the object's internal `[[Prototype]]`. It allows you to access and modify the prototype of an object directly. For example:

```javascript
const animal = {
  speak() {
    console.log(`${this.name} makes a sound`);
  }
};

const dog = {
  name: "Dog"
};

dog.__proto__ = animal;
dog.speak(); // Output: Dog makes a sound
```

## Object.create()

The `Object.create()` method creates a new object with the specified prototype object and properties. It allows you to directly set the prototype of the new object. For example:

```javascript
const animal = {
  speak() {
    console.log(`${this.name} makes a sound`);
  }
};

const dog = Object.create(animal);
dog.name = "Dog";
dog.speak(); // Output: Dog makes a sound
```

## Shadowing

Shadowing occurs when a property in an object overrides a property with the same name in its prototype chain. The object's own property takes precedence over the prototype's property. For example:

```javascript
const animal = {
  speak() {
    console.log(`${this.name} makes a sound`);
  }
};

const dog = Object.create(animal);
dog.name = "Dog";
dog.speak(); // Output: Dog makes a sound

dog.speak = function() {
  console.log(`${this.name} barks`);
};

dog.speak(); // Output: Dog barks
```

## Property lookup

Property lookup in JavaScript follows the prototype chain. When you try to access a property on an object, JavaScript first looks for the property on the object itself. If it doesn't find it, it continues searching up the prototype chain until it either finds the property or reaches the end of the chain (`null`). For example:

```javascript
const animal = {
  speak() {
    console.log(`${this.name} makes a sound`);
  }
};

const dog = Object.create(animal);
dog.name = "Dog";

console.log(dog.name); // Output: Dog (found on the object itself)
console.log(dog.speak); // Output: [Function: speak] (found on the prototype)
```

## Built-in prototypes

In JavaScript, most built-in objects have prototypes that provide additional methods and properties. For example, arrays have the `Array.prototype` which includes methods like `push`, `pop`, and `forEach`. You can also extend built-in prototypes, but it is generally discouraged to avoid conflicts. For example:

```javascript
const arr = [1, 2, 3];
console.log(arr.length); // Output: 3 (from Array.prototype)

Array.prototype.first = function() {
  return this[0];
};

console.log(arr.first()); // Output: 1
```

## Extending prototypes

You can extend the prototypes of built-in objects to add custom methods. However, this practice should be used with caution to avoid conflicts with future JavaScript versions or other libraries. For example:

```javascript
String.prototype.reverse = function() {
  return this.split('').reverse().join('');
};

const str = "hello";
console.log(str.reverse()); // Output: "olleh"
```

## Prototype vs class

In JavaScript, classes are essentially syntactic sugar over the existing prototype-based inheritance. While prototypes allow you to define methods and properties that are shared among all instances, classes provide a more familiar and structured way to define constructor functions and methods. For example:

```javascript
// Using prototype
function Animal(name) {
  this.name = name;
}

Animal.prototype.speak = function() {
  console.log(`${this.name} makes a sound`);
};

const dog1 = new Animal("Dog");
dog1.speak(); // Output: Dog makes a sound

// Using class
class AnimalClass {
  constructor(name) {
    this.name = name;
  }
  speak() {
    console.log(`${this.name} makes a sound`);
  }
}

const dog2 = new AnimalClass("Dog");
dog2.speak(); // Output: Dog makes a sound
```

# Iterators & Generators

## Iterable

An object is considered iterable if it implements the `@@iterator` method, meaning it has a method with the key `Symbol.iterator` that returns an iterator. Iterables can be used with the `for...of` loop and other constructs that expect iterables. For example:

```javascript
const iterable = {
  *[Symbol.iterator]() {
    yield 1;
    yield 2;
    yield 3;
  }
};

for (const value of iterable) {
  console.log(value); // Output: 1, 2, 3
}
```

## Iterator

An iterator is an object that provides a `next()` method which returns an object with two properties: `value` (the next value) and `done` (a boolean indicating if the iteration is complete). For example:

```javascript
const iterator = iterable[Symbol.iterator]();
console.log(iterator.next()); // Output: { value: 1, done: false }
console.log(iterator.next()); // Output: { value: 2, done: false }
console.log(iterator.next()); // Output: { value: 3, done: false }
console.log(iterator.next()); // Output: { value: undefined, done: true }
```

## Iterator protocol

The iterator protocol defines a standard way to produce a sequence of values. An object is an iterator when it implements a `next()` method that returns an object with `value` and `done` properties. Any object that follows this protocol can be used as an iterator. For example:

```javascript
const myIterator = {
  current: 1,
  last: 3,
  next() {
    if (this.current <= this.last) {
      return { value: this.current++, done: false };
    } else {
      return { value: undefined, done: true };
    }
  }
};

console.log(myIterator.next()); // Output: { value: 1, done: false }
console.log(myIterator.next()); // Output: { value: 2, done: false }
console.log(myIterator.next()); // Output: { value: 3, done: false }
console.log(myIterator.next()); // Output: { value: undefined, done: true }
```

## Symbol.iterator

The `Symbol.iterator` is a well-known symbol that specifies the default iterator for an object. It allows an object to be iterable using the `for...of` loop and other constructs that expect iterables. For example:

```javascript
const myIterable = {
  *[Symbol.iterator]() {
    yield 'a';
    yield 'b';
    yield 'c';
  }
};

for (const value of myIterable) {
  console.log(value); // Output: a, b, c
}
```

## next()

The `next()` method is used to retrieve the next item from an iterator. It returns an object with two properties: `value` (the next value) and `done` (a boolean indicating if the iteration is complete). For example:

```javascript
const iterator = myIterable[Symbol.iterator]();
console.log(iterator.next()); // Output: { value: 'a', done: false }
console.log(iterator.next()); // Output: { value: 'b', done: false }
console.log(iterator.next()); // Output: { value: 'c', done: false }
console.log(iterator.next()); // Output: { value: undefined, done: true }
```

## Generator functions

Generator functions are a special type of function that can be paused and resumed, allowing them to produce a sequence of values over time. They are defined using the `function*` syntax and use the `yield` keyword to yield values. For example:

```javascript
function* myGenerator() {
  yield 1;
  yield 2;
  yield 3;
}

const gen = myGenerator();
console.log(gen.next()); // Output: { value: 1, done: false }
console.log(gen.next()); // Output: { value: 2, done: false }
console.log(gen.next()); // Output: { value: 3, done: false }
console.log(gen.next()); // Output: { value: undefined, done: true }
```

## yield

The `yield` keyword is used inside generator functions to pause the function execution and return a value to the caller. The function can later be resumed from where it was paused. For example:

```javascript
function* myGenerator() {
  yield 1;
  yield 2;
  yield 3;
}

const gen = myGenerator();
console.log(gen.next()); // Output: { value: 1, done: false }
console.log(gen.next()); // Output: { value: 2, done: false }
console.log(gen.next()); // Output: { value: 3, done: false }
console.log(gen.next()); // Output: { value: undefined, done: true }
```

## Generator delegation

Generator delegation allows a generator function to delegate part of its iteration to another generator function using the `yield*` expression. This can be useful for composing generators. For example:

```javascript
function* generatorA() {
  yield 1;
  yield 2;
}

function* generatorB() {
  yield* generatorA();
  yield 3;
}

const gen = generatorB();
console.log(gen.next()); // Output: { value: 1, done: false }
console.log(gen.next()); // Output: { value: 2, done: false }
console.log(gen.next()); // Output: { value: 3, done: false }
console.log(gen.next()); // Output: { value: undefined, done: true }
```

## Async iterators

Async iterators are similar to regular iterators but are used for asynchronous operations. They implement the `Symbol.asyncIterator` method and return a promise that resolves to an object with `value` and `done` properties. For example:

```javascript
const myAsyncIterable = {
  async *[Symbol.asyncIterator]() {
    yield 'a';
    yield 'b';
    yield 'c';
  }
};

(async () => {
  for await (const value of myAsyncIterable) {
    console.log(value); // Output: a, b, c
  }
})();
```

## for await...of

The `for await...of` loop is used to iterate over asynchronous iterables. It allows you to handle each value as it becomes available, waiting for promises to resolve. For example:

```javascript
const myAsyncIterable = {
  async *[Symbol.asyncIterator]() {
    yield 'a';
    yield 'b';
    yield 'c';
  }
};

(async () => {
  for await (const value of myAsyncIterable) {
    console.log(value); // Output: a, b, c
  }
})();
```

# Map, Set & Weak Collections

## Map

The `Map` object holds key-value pairs and remembers the original insertion order of the keys. Any value (both objects and primitive values) may be used as either a key or a value. For example:

```javascript
const myMap = new Map();
myMap.set('a', 1);
myMap.set('b', 2);
myMap.set('c', 3);

console.log(myMap.get('a')); // Output: 1
console.log(myMap.get('b')); // Output: 2
console.log(myMap.get('c')); // Output: 3
console.log(myMap.size);     // Output: 3
```

## Map keys

You can retrieve all the keys of a `Map` object using the `keys()` method, which returns an iterator. For example:

```javascript
const myMap = new Map();
myMap.set('a', 1);
myMap.set('b', 2);
myMap.set('c', 3);

for (const key of myMap.keys()) {
  console.log(key); // Output: a, b, c
}
```

## Map methods

The `Map` object provides several useful methods for working with key-value pairs. Some of the commonly used methods include:

- `set(key, value)`: Adds or updates an element with the specified key and value.
- `get(key)`: Returns the value associated with the specified key.
- `has(key)`: Returns a boolean indicating whether the map contains the specified key.
- `delete(key)`: Removes the element with the specified key.
- `clear()`: Removes all elements from the map.
- `keys()`: Returns an iterator over the keys of the map.
- `values()`: Returns an iterator over the values of the map.
- `entries()`: Returns an iterator over the `[key, value]` pairs of the map.

For example:

```javascript
const myMap = new Map();
myMap.set('a', 1);
myMap.set('b', 2);
myMap.set('c', 3);

console.log(myMap.has('a')); // Output: true
console.log(myMap.delete('b')); // Output: true
console.log(myMap.size); // Output: 2

for (const [key, value] of myMap.entries()) {
  console.log(`${key}: ${value}`); // Output: a: 1, c: 3
}
```
## Set

The `Set` object lets you store unique values of any type, whether primitive values or object references. For example:

```javascript
const mySet = new Set();
mySet.add(1);
mySet.add(2);
mySet.add(3);
mySet.add(2); // Duplicate values are ignored

console.log(mySet.has(1)); // Output: true
console.log(mySet.has(4)); // Output: false
console.log(mySet.size);   // Output: 3

for (const value of mySet.values()) {
  console.log(value); // Output: 1, 2, 3
}
```

## WeakMap and WeakSet

The `WeakMap` object is similar to `Map`, but it only allows objects as keys and does not prevent garbage collection of the keys. The `WeakSet` object is similar to `Set`, but it only stores objects and also does not prevent garbage collection of the objects. For example:

```javascript
const myWeakMap = new WeakMap();
const obj = {};
myWeakMap.set(obj, 'value');
console.log(myWeakMap.get(obj)); // Output: value

const myWeakSet = new WeakSet();
myWeakSet.add(obj);
console.log(myWeakSet.has(obj)); // Output: true
```

## Map vs Object

While both `Map` and `Object` can be used to store key-value pairs, there are some key differences:

- `Map` allows keys of any type, whereas `Object` only allows strings and symbols as keys.
- `Map` maintains the insertion order of its elements, whereas `Object` does not guarantee order.
- `Map` has a `size` property to easily get the number of elements, whereas `Object` requires manual counting.
- `Map` provides built-in methods like `set`, `get`, `has`, `delete`, and `clear`, whereas `Object` requires manual handling for these operations.
- `Map` is generally more suitable for scenarios where frequent additions and removals of key-value pairs are required.

Example:

```javascript
const myMap = new Map();
myMap.set('a', 1);
myMap.set('b', 2);

const myObj = { a: 1, b: 2 };

console.log(myMap.get('a')); // Output: 1
console.log(myObj['a']);     // Output: 1
```

## Set vs Array

While both `Set` and `Array` can be used to store collections of values, there are some key differences:

- `Set` only stores unique values, whereas `Array` can contain duplicate values.
- `Set` provides methods like `add`, `has`, `delete`, and `clear`, whereas `Array` requires manual handling for these operations.
- `Set` does not maintain indexes, whereas `Array` elements are indexed.
- `Set` is generally more suitable for scenarios where uniqueness of elements is important.

Example:

```javascript
const mySet = new Set([1, 2, 3, 2]);
console.log(mySet); // Output: Set { 1, 2, 3 }

const myArray = [1, 2, 3, 2];
console.log(myArray); // Output: [ 1, 2, 3, 2 ]
```

## Weak references

Weak references allow you to hold a reference to an object without preventing it from being garbage collected. This can be useful in scenarios where you want to cache objects without affecting their lifecycle. For example:

```javascript
let obj = { name: 'John' };
const weakRef = new WeakRef(obj);

console.log(weakRef.deref()); // Output: { name: 'John' }

obj = null; // The object can now be garbage collected
console.log(weakRef.deref()); // Output: undefined (if garbage collected)
```

## Garbage collection use cases

Garbage collection is the process by which JavaScript automatically frees up memory by removing objects that are no longer reachable. Understanding when and how garbage collection occurs can help you write more efficient code. Some common use cases include:

- **Caching:** Using `WeakMap` or `WeakSet` to store temporary data without preventing garbage collection.
- **Event listeners:** Ensuring that event listeners are removed when they are no longer needed to avoid memory leaks.
- **DOM references:** Avoiding long-lived references to DOM elements that may be removed from the document.
- **Large data structures:** Using weak references to manage memory for large objects that are expensive to keep in memory.

# Modules

## Why Modules

Modules in JavaScript allow you to break your code into smaller, reusable pieces. They help in organizing code, managing dependencies, and avoiding global namespace pollution. By using modules, you can import and export functionality between different files, making your code more maintainable and scalable.

## ES Modules

ES Modules (ECMAScript Modules) are the standard way to work with modules in modern JavaScript. They allow you to export and import functionality between different files using the `export` and `import` keywords.

Example:

```javascript
// math.js
export function add(a, b) {
  return a + b;
}

// main.js
import { add } from './math.js';
console.log(add(2, 3)); // Output: 5
```

## export and export default

In JavaScript, you can use `export` to export multiple named values from a module, and `export default` to export a single default value.

Example of named exports:

```javascript
// math.js
export function add(a, b) {
  return a + b;
}

export function subtract(a, b) {
  return a - b;
}

// main.js
import { add, subtract } from './math.js';
console.log(add(2, 3)); // Output: 5
console.log(subtract(5, 2)); // Output: 3
```

Example of default export:

```javascript
// math.js
export default function multiply(a, b) {
  return a * b;
}

// main.js
import multiply from './math.js';
console.log(multiply(2, 3)); // Output: 6
```

## import, named import, default import, namespace import

In JavaScript, the `import` statement is used to bring in functionality from other modules. There are several ways to import modules:

- **Named import:** Import specific named exports from a module.
- **Default import:** Import the default export from a module.
- **Namespace import:** Import all exports from a module as a single object.

Examples:

```javascript
// math.js
export function add(a, b) {
  return a + b;
}

export default function multiply(a, b) {
  return a * b;
}

// main.js
import multiply, { add } from './math.js'; // Default import and named import
import * as math from './math.js'; // Namespace import

console.log(add(2, 3)); // Output: 5
console.log(multiply(2, 3)); // Output: 6
console.log(math.add(2, 3)); // Output: 5
console.log(math.default(2, 3)); // Output: 6
```

## Re-exporting

Re-exporting allows you to export values from another module without importing them first. This is useful for creating a single entry point for multiple modules.

Example:

```javascript
// math.js
export function add(a, b) {
  return a + b;
}

export function subtract(a, b) {
  return a - b;
}

// index.js
export { add, subtract } from './math.js';

// main.js
import { add, subtract } from './index.js';
console.log(add(2, 3)); // Output: 5
console.log(subtract(5, 2)); // Output: 3
```

## Dynamic import

Dynamic import allows you to import modules on demand, rather than at the top of the file. This can be useful for code splitting and lazy loading.

Example:

```javascript
// main.js
async function loadMath() {
  const math = await import('./math.js');
  console.log(math.add(2, 3)); // Output: 5
  console.log(math.default(2, 3)); // Output: 6
}

loadMath();
```

## CommonJS vs ES Modules

JavaScript has two main module systems: CommonJS (used in Node.js) and ES Modules (standardized in modern JavaScript).

- **CommonJS:** Uses `require` and `module.exports`.
- **ES Modules:** Uses `import` and `export`.

Example of CommonJS:

```javascript
// math.js
function add(a, b) {
  return a + b;
}

function subtract(a, b) {
  return a - b;
}

module.exports = { add, subtract };

// main.js
const { add, subtract } = require('./math.js');
console.log(add(2, 3)); // Output: 5
console.log(subtract(5, 2)); // Output: 3
```

Example of ES Modules:

```javascript
// math.js
export function add(a, b) {
  return a + b;
}

export function subtract(a, b) {
  return a - b;
}

// main.js
import { add, subtract } from './math.js';
console.log(add(2, 3)); // Output: 5
console.log(subtract(5, 2)); // Output: 3
```

## require()

The `require()` function is used in CommonJS modules to import other modules. It is synchronous and can be used anywhere in the code.

Example:

```javascript
// math.js
function add(a, b) {
  return a + b;
}

function subtract(a, b) {
  return a - b;
}

module.exports = { add, subtract };

// main.js
const { add, subtract } = require('./math.js');
console.log(add(2, 3)); // Output: 5
console.log(subtract(5, 2)); // Output: 3
```

## module.exports

The `module.exports` object is used in CommonJS modules to export values so that they can be imported using `require()`. You can assign an object, function, or any value to `module.exports`.

Example:

```javascript
// math.js
function add(a, b) {
  return a + b;
}

function subtract(a, b) {
  return a - b;
}

module.exports = { add, subtract };

// main.js
const { add, subtract } = require('./math.js');
console.log(add(2, 3)); // Output: 5
console.log(subtract(5, 2)); // Output: 3
```

## Module resolution

Module resolution is the process by which JavaScript determines the location of a module when it is imported using `require()` or `import`. In Node.js, the module resolution algorithm looks for modules in the following order:

1. **Core modules:** Built-in Node.js modules like `fs` and `path`.
2. **File modules:** Relative or absolute file paths.
3. **Node modules:** Modules installed in the `node_modules` directory.

Example:

```javascript
// Assuming lodash is installed in node_modules
const _ = require('lodash');
console.log(_.isEmpty({})); // Output: true
```

## Circular dependencies

Circular dependencies occur when two or more modules depend on each other directly or indirectly. This can lead to incomplete module exports and unexpected behavior.

Example:

```javascript
// a.js
const b = require('./b.js');
module.exports = {
  name: 'Module A',
  bName: b.name,
};

// b.js
const a = require('./a.js');
module.exports = {
  name: 'Module B',
  aName: a.name,
};

// main.js
const a = require('./a.js');
const b = require('./b.js');
console.log(a); // Output may have undefined bName
console.log(b); // Output may have undefined aName
```

# JSON & Data Handling

## JSON syntax

JSON (JavaScript Object Notation) is a lightweight data interchange format that is easy for humans to read and write and easy for machines to parse and generate. JSON syntax is a subset of JavaScript object syntax.

Example:

```javascript
const jsonData = {
  "name": "John Doe",
  "age": 30,
  "isStudent": false,
  "courses": ["Math", "Science"],
  "address": {
    "street": "123 Main St",
    "city": "Anytown"
  }
};
console.log(jsonData.name); // Output: John Doe
```

## JSON.parse()

The `JSON.parse()` method is used to parse a JSON string and convert it into a JavaScript object.

Example:

```javascript
const jsonString = '{"name": "John Doe", "age": 30}';
const jsonData = JSON.parse(jsonString);
console.log(jsonData.name); // Output: John Doe
```

## JSON.stringify()

The `JSON.stringify()` method is used to convert a JavaScript object into a JSON string.

Example:

```javascript
const jsonData = { name: "John Doe", age: 30 };
const jsonString = JSON.stringify(jsonData);
console.log(jsonString); // Output: '{"name":"John Doe","age":30}'
```

## Serialization

Serialization is the process of converting a data structure or object into a format that can be easily stored or transmitted and later reconstructed. In JavaScript, JSON is commonly used for serialization.

Example:

```javascript
const jsonData = { name: "John Doe", age: 30 };
const serializedData = JSON.stringify(jsonData); // Serialize the object
console.log(serializedData); // Output: '{"name":"John Doe","age":30}'

const deserializedData = JSON.parse(serializedData); // Deserialize the JSON string
console.log(deserializedData); // Output: { name: 'John Doe', age: 30 }
```

## Deserialization

Deserialization is the process of converting serialized data back into its original data structure or object form. In JavaScript, this is commonly done using `JSON.parse()`.

Example:

```javascript
const serializedData = '{"name":"John Doe","age":30}';
const deserializedData = JSON.parse(serializedData);
console.log(deserializedData); // Output: { name: 'John Doe', age: 30 }
```

## Deep cloning concepts

Deep cloning is the process of creating a new object that is a copy of an existing object, including all nested objects. This ensures that changes to the new object do not affect the original object. In JavaScript, deep cloning can be achieved using `JSON.stringify()` and `JSON.parse()`.

Example:

```javascript
const originalData = { name: "John Doe", address: { city: "Anytown" } };
const deepClonedData = JSON.parse(JSON.stringify(originalData));
deepClonedData.address.city = "Othertown";
console.log(originalData.address.city); // Output: "Anytown"
console.log(deepClonedData.address.city); // Output: "Othertown"
```

## Structured Cloning

Structured cloning is a method of creating a deep copy of an object, including all nested objects, arrays, and other complex data types. Unlike JSON-based deep cloning, structured cloning can handle more data types such as `Date`, `Map`, `Set`, `ArrayBuffer`, and more.

Example:

```javascript
const originalData = { name: "John Doe", address: { city: "Anytown" }, date: new Date() };
const deepClonedData = structuredClone(originalData);
deepClonedData.address.city = "Othertown";
console.log(originalData.address.city); // Output: "Anytown"
console.log(deepClonedData.address.city); // Output: "Othertown"
console.log(originalData.date === deepClonedData.date); // Output: false
```

## structuredClone()

The `structuredClone()` function is used to create a deep copy of a given value, including all nested objects, arrays, and other complex data types. It can handle more data types than JSON-based cloning, such as `Date`, `Map`, `Set`, `ArrayBuffer`, and more.

Example:

```javascript
const originalData = { name: "John Doe", address: { city: "Anytown" }, date: new Date() };
const deepClonedData = structuredClone(originalData);
deepClonedData.address.city = "Othertown";
console.log(originalData.address.city); // Output: "Anytown"
console.log(deepClonedData.address.city); // Output: "Othertown"
console.log(originalData.date === deepClonedData.date); // Output: false
```

## Handling API data

When working with APIs, data is often received in JSON format. To work with this data in JavaScript, it needs to be deserialized using `JSON.parse()`. Similarly, when sending data to an API, it often needs to be serialized using `JSON.stringify()`.

Example:

```javascript
// Fetching data from an API
fetch("https://api.example.com/user/1")
  .then(response => response.json()) // Deserialization
  .then(data => {
    console.log(data); // Work with the deserialized data
  });

// Sending data to an API
const userData = { name: "John Doe", age: 30 };
fetch("https://api.example.com/user", {
  method: "POST",
  headers: {
    "Content-Type": "application/json"
  },
  body: JSON.stringify(userData) // Serialization
});
```

## Transforming nested data

When working with nested data structures, it is often necessary to transform or update specific parts of the data. This can be done using techniques such as deep cloning and structured cloning to avoid mutating the original data.

Example:

```javascript
const originalData = { name: "John Doe", address: { city: "Anytown" } };
const deepClonedData = structuredClone(originalData);
deepClonedData.address.city = "Othertown";
console.log(originalData.address.city); // Output: "Anytown"
console.log(deepClonedData.address.city); // Output: "Othertown"
```

# Regular Expressions

## What are regex?

Regular expressions (regex) are patterns used to match character combinations in strings. In JavaScript, regular expressions are implemented using the `RegExp` object or by using literal syntax.

Example:

```javascript
const regex = /hello/;
console.log(regex.test("hello world")); // Output: true
console.log(regex.test("goodbye world")); // Output: false
```

## Regex syntax

Regular expressions have their own syntax for defining patterns. Some common elements include:
- `.`: Matches any single character except newline.
- `*`: Matches 0 or more occurrences of the preceding element.
- `+`: Matches 1 or more occurrences of the preceding element.
- `?`: Matches 0 or 1 occurrence of the preceding element.
- `\d`: Matches any digit (equivalent to `[0-9]`).
- `\w`: Matches any word character (alphanumeric + underscore).
- `\s`: Matches any whitespace character.
- `^`: Matches the beginning of a string.
- `$`: Matches the end of a string.
- `[abc]`: Matches any one of the characters `a`, `b`, or `c`.
- `(abc)`: Groups multiple tokens together and remembers the match.

Example:

```javascript
const regex = /^\d{3}-\d{2}-\d{4}$/; // Matches a pattern like 123-45-6789
console.log(regex.test("123-45-6789")); // Output: true
console.log(regex.test("123-456-789")); // Output: false
```

## Character classes

Character classes allow you to define a set of characters to match. Some common character classes include:
- `[abc]`: Matches any one of the characters `a`, `b`, or `c`.
- `[^abc]`: Matches any character except `a`, `b`, or `c`.
- `[a-z]`: Matches any lowercase letter from `a` to `z`.
- `[A-Z]`: Matches any uppercase letter from `A` to `Z`.
- `[0-9]`: Matches any digit from `0` to `9`.

Example:

```javascript
const regex = /[a-z]/;
console.log(regex.test("hello")); // Output: true
console.log(regex.test("HELLO")); // Output: false
```

## Quantifiers

Quantifiers specify how many instances of a character, group, or character class must be present in the input for a match to be found. Some common quantifiers include:
- `*`: Matches 0 or more occurrences of the preceding element.
- `+`: Matches 1 or more occurrences of the preceding element.
- `?`: Matches 0 or 1 occurrence of the preceding element.
- `{n}`: Matches exactly `n` occurrences of the preceding element.
- `{n,}`: Matches `n` or more occurrences of the preceding element.
- `{n,m}`: Matches between `n` and `m` occurrences of the preceding element.

Example:

```javascript
const regex = /\d{3}-\d{2}-\d{4}/; // Matches a pattern like 123-45-6789
console.log(regex.test("123-45-6789")); // Output: true
console.log(regex.test("12-345-6789")); // Output: false
```

## Groups

Groups allow you to combine multiple tokens together and apply quantifiers to the entire group. Groups are created using parentheses `()`.

Example:

```javascript
const regex = /(abc)+/; // Matches one or more occurrences of "abc"
console.log(regex.test("abc")); // Output: true
console.log(regex.test("abcabc")); // Output: true
console.log(regex.test("ab")); // Output: false
```

## Capturing groups

Capturing groups allow you to extract a portion of the matched string. They are created using parentheses `()` and can be accessed using the `match` method or the `RegExp` object's `exec` method.

Example:

```javascript
const regex = /(\d{3})-(\d{2})-(\d{4})/; // Captures parts of a pattern like 123-45-6789
const match = "123-45-6789".match(regex);
console.log(match[1]); // Output: 123
console.log(match[2]); // Output: 45
console.log(match[3]); // Output: 6789
```

## Non-capturing groups

Non-capturing groups allow you to group multiple tokens together without creating a capturing group. They are created using `(?:...)`.

Example:

```javascript
const regex = /(?:abc)+/; // Matches one or more occurrences of "abc" without capturing
console.log(regex.test("abc")); // Output: true
console.log(regex.test("abcabc")); // Output: true
console.log(regex.test("ab")); // Output: false
```

## Alternation

Alternation allows you to match one of several patterns. It is created using the pipe `|` symbol.

Example:

```javascript
const regex = /cat|dog/; // Matches either "cat" or "dog"
console.log(regex.test("cat")); // Output: true
console.log(regex.test("dog")); // Output: true
console.log(regex.test("bird")); // Output: false
```

## Anchors

Anchors are used to match positions within a string rather than actual characters. Common anchors include:
- `^`: Matches the beginning of the string.
- `$`: Matches the end of the string.

Example:

```javascript
const regexStart = /^Hello/; // Matches "Hello" at the beginning of the string
console.log(regexStart.test("Hello world")); // Output: true
console.log(regexStart.test("world Hello")); // Output: false

const regexEnd = /world$/; // Matches "world" at the end of the string
console.log(regexEnd.test("Hello world")); // Output: true
console.log(regexEnd.test("world Hello")); // Output: false
```

## Flags

Flags are used to modify the behavior of a regular expression. Common flags include:
- `g`: Global search (find all matches rather than stopping after the first match).
- `i`: Case-insensitive search.
- `m`: Multi-line search.
- `s`: Allows `.` to match newline characters.
- `u`: Enables full Unicode support.
- `y`: Sticky search (matches only from the last index position).

Example:

```javascript
const regex = /hello/gi; // Case-insensitive and global search
const str = "Hello hello HELLO";
const matches = str.match(regex);
console.log(matches); // Output: ["Hello", "hello", "HELLO"]
```

## test(), match(), matchAll(), replace(), search()

These are common methods used with regular expressions in JavaScript:

- `test()`: Tests for a match in a string. Returns `true` or `false`.
- `match()`: Retrieves the matches when matching a string against a regular expression.
- `matchAll()`: Returns an iterator of all matches, including capturing groups.
- `replace()`: Replaces matched substrings with a new substring.
- `search()`: Tests for a match and returns the index of the first match, or `-1` if not found.

# Dates & Time

## Date

In JavaScript, the `Date` object is used to work with dates and times.

Example:

```javascript
const now = new Date(); // Current date and time
console.log(now);

const specificDate = new Date("2024-06-15T12:00:00"); // Specific date and time
console.log(specificDate);
```

## Creating dates

You can create dates in JavaScript using the `Date` constructor in several ways:

```javascript
// Using year, month, day, hours, minutes, seconds, milliseconds
const date1 = new Date(2024, 5, 15, 12, 0, 0, 0); // Note: Month is 0-indexed (0 = January, 5 = June)
console.log(date1);

// Using a date string
const date2 = new Date("2024-06-15T12:00:00");
console.log(date2);

// Using milliseconds since the Unix epoch (January 1, 1970)
const date3 = new Date(1718472000000);
console.log(date3);
```

## Getting date values

You can retrieve various components of a date using the following methods:

```javascript
const date = new Date("2024-06-15T12:00:00");

console.log(date.getFullYear()); // Output: 2024
console.log(date.getMonth());    // Output: 5 (June, 0-indexed)
console.log(date.getDate());     // Output: 15
console.log(date.getDay());      // Output: 6 (Saturday, 0 = Sunday)
console.log(date.getHours());    // Output: 12
console.log(date.getMinutes());  // Output: 0
console.log(date.getSeconds());  // Output: 0
console.log(date.getMilliseconds()); // Output: 0
console.log(date.getTime());     // Output: 1718472000000 (milliseconds since Unix epoch)
```

## Setting date values

You can modify various components of a date using the following methods:

```javascript
const date = new Date("2024-06-15T12:00:00");

date.setFullYear(2025);
date.setMonth(6);    // July (0-indexed)
date.setDate(20);
date.setHours(15);
date.setMinutes(30);
date.setSeconds(45);
date.setMilliseconds(500);

console.log(date); // Output: 2025-07-20T15:30:45.500Z (depending on your timezone)
```

## Formatting dates

You can format dates in JavaScript using various methods, such as `toDateString()`, `toTimeString()`, `toISOString()`, and `toLocaleString()`.

```javascript
const date = new Date("2024-06-15T12:00:00");

console.log(date.toDateString());   // Output: Sat Jun 15 2024
console.log(date.toTimeString());   // Output: 12:00:00 GMT+0000 (Coordinated Universal Time)
console.log(date.toISOString());    // Output: 2024-06-15T12:00:00.000Z
console.log(date.toLocaleString()); // Output: 6/15/2024, 12:00:00 PM (depending on your locale)
```

## Timestamps

In JavaScript, a timestamp represents the number of milliseconds that have elapsed since the Unix epoch (January 1, 1970, 00:00:00 UTC). You can get the current timestamp using `Date.now()` or by calling `getTime()` on a `Date` object.

```javascript
const now = new Date();
const timestamp = now.getTime();
console.log(timestamp); // Output: 1718472000000 (example)

const currentTimestamp = Date.now();
console.log(currentTimestamp); // Output: 1718472000000 (example)
```

## UTC

JavaScript provides methods to work with dates and times in Coordinated Universal Time (UTC). These methods include `getUTCFullYear()`, `getUTCMonth()`, `getUTCDate()`, `getUTCDay()`, `getUTCHours()`, `getUTCMinutes()`, `getUTCSeconds()`, and `getUTCMilliseconds()`.

```javascript
const date = new Date("2024-06-15T12:00:00");

console.log(date.getUTCFullYear()); // Output: 2024
console.log(date.getUTCMonth());    // Output: 5 (June, 0-indexed)
console.log(date.getUTCDate());     // Output: 15
console.log(date.getUTCDay());      // Output: 6 (Saturday, 0 = Sunday)
console.log(date.getUTCHours());    // Output: 12
console.log(date.getUTCMinutes());  // Output: 0
console.log(date.getUTCSeconds());  // Output: 0
console.log(date.getUTCMilliseconds()); // Output: 0
```

## Time zones

JavaScript allows you to work with dates and times in different time zones using the `Intl.DateTimeFormat` object. You can specify the time zone when formatting a date.

```javascript
const date = new Date("2024-06-15T12:00:00");

const options = { timeZone: "America/New_York", timeZoneName: "short" };
console.log(new Intl.DateTimeFormat("en-US", options).format(date)); // Output: 6/15/2024, EDT

const optionsTokyo = { timeZone: "Asia/Tokyo", timeZoneName: "short" };
console.log(new Intl.DateTimeFormat("en-US", optionsTokyo).format(date)); // Output: 6/15/2024, JST
```

## Date calculations

You can perform date calculations in JavaScript by using timestamps or by manipulating `Date` objects directly. For example, you can add or subtract days from a date.

```javascript
const date = new Date("2024-06-15T12:00:00");

// Add 5 days
const newDate = new Date(date);
newDate.setDate(newDate.getDate() + 5);
console.log(newDate.toDateString()); // Output: Thu Jun 20 2024

// Subtract 3 days
const previousDate = new Date(date);
previousDate.setDate(previousDate.getDate() - 3);
console.log(previousDate.toDateString()); // Output: Wed Jun 12 2024
```

## Intl.DateTimeFormat

The `Intl.DateTimeFormat` object enables language-sensitive date and time formatting. You can customize the output by specifying options such as `year`, `month`, `day`, `hour`, `minute`, `second`, `timeZone`, and `timeZoneName`.

```javascript
const date = new Date("2024-06-15T12:00:00");

const options = { year: "numeric", month: "long", day: "numeric", timeZone: "UTC" };
console.log(new Intl.DateTimeFormat("en-US", options).format(date)); // Output: June 15, 2024

const optionsWithTime = { year: "numeric", month: "long", day: "numeric", hour: "2-digit", minute: "2-digit", second: "2-digit", timeZone: "UTC" };
console.log(new Intl.DateTimeFormat("en-US", optionsWithTime).format(date)); // Output: June 15, 2024, 12:00:00 PM
```

## Temporal API concepts

The Temporal API provides a modern way to work with dates and times in JavaScript. It includes objects like `Temporal.PlainDate`, `Temporal.PlainTime`, `Temporal.PlainDateTime`, `Temporal.ZonedDateTime`, and `Temporal.Duration` for more precise and flexible date-time handling.

```javascript
const { PlainDate, PlainTime, PlainDateTime, ZonedDateTime, Duration } = Temporal;

// Create a plain date
const date = PlainDate.from("2024-06-15");
console.log(date.toString()); // Output: 2024-06-15

// Create a plain time
const time = PlainTime.from("12:00:00");
console.log(time.toString()); // Output: 12:00:00

// Create a plain date-time
const dateTime = PlainDateTime.from("2024-06-15T12:00:00");
console.log(dateTime.toString()); // Output: 2024-06-15T12:00:00

// Create a zoned date-time
const zonedDateTime = ZonedDateTime.from("2024-06-15T12:00:00[America/New_York]");
console.log(zonedDateTime.toString()); // Output: 2024-06-15T12:00:00-04:00[America/New_York]

// Create a duration
const duration = Duration.from({ days: 5, hours: 3 });
console.log(duration.toString()); // Output: P5DT3H
```

# Internationalization

## Intl

The `Intl` object provides a namespace for several constructors and functions that enable language-sensitive string comparison, number formatting, and date and time formatting.

## Intl.NumberFormat

The `Intl.NumberFormat` object enables language-sensitive number formatting. You can customize the output by specifying options such as `style`, `currency`, `minimumFractionDigits`, and `maximumFractionDigits`.

```javascript
const number = 1234567.89;

// Format as a plain number
console.log(new Intl.NumberFormat("en-US").format(number)); // Output: 1,234,567.89

// Format as currency
const currencyOptions = { style: "currency", currency: "USD" };
console.log(new Intl.NumberFormat("en-US", currencyOptions).format(number)); // Output: $1,234,567.89

// Format with minimum and maximum fraction digits
const fractionOptions = { minimumFractionDigits: 2, maximumFractionDigits: 2 };
console.log(new Intl.NumberFormat("en-US", fractionOptions).format(number)); // Output: 1,234,567.89
```

## Intl.DateTimeFormat

The `Intl.DateTimeFormat` object enables language-sensitive date and time formatting. You can customize the output by specifying options such as `year`, `month`, `day`, `hour`, `minute`, `second`, and `timeZone`.

```javascript
const date = new Date("2024-06-15T12:00:00");

// Format as a plain date
const options = { year: "numeric", month: "long", day: "numeric", timeZone: "UTC" };
console.log(new Intl.DateTimeFormat("en-US", options).format(date)); // Output: June 15, 2024

// Format with time
const optionsWithTime = { year: "numeric", month: "long", day: "numeric", hour: "2-digit", minute: "2-digit", second: "2-digit", timeZone: "UTC" };
console.log(new Intl.DateTimeFormat("en-US", optionsWithTime).format(date)); // Output: June 15, 2024, 12:00:00 PM
```

## Intl.Collator

The `Intl.Collator` object enables language-sensitive string comparison. You can customize the comparison by specifying options such as `locale` and `sensitivity`.

```javascript
const strings = ["apple", "Banana", "cherry"];

// Sort strings in a case-insensitive manner
const collator = new Intl.Collator("en-US", { sensitivity: "base" });
console.log(strings.sort(collator.compare)); // Output: ["apple", "Banana", "cherry"]
```

## Intl.RelativeTimeFormat

The `Intl.RelativeTimeFormat` object enables language-sensitive relative time formatting. You can customize the output by specifying options such as `locale`, `style`, and `numeric`.

```javascript
const rtf = new Intl.RelativeTimeFormat("en-US", { numeric: "auto" });

console.log(rtf.format(-1, "day")); // Output: yesterday
console.log(rtf.format(1, "day"));  // Output: tomorrow
console.log(rtf.format(-2, "day")); // Output: 2 days ago
console.log(rtf.format(2, "day"));  // Output: in 2 days
```

## Locale handling

JavaScript provides several ways to handle locales, primarily through the `Intl` object. You can specify the locale when creating instances of `Intl.NumberFormat`, `Intl.DateTimeFormat`, `Intl.Collator`, and `Intl.RelativeTimeFormat`. The locale determines the formatting conventions used for numbers, dates, times, and strings.

```javascript
const number = 1234567.89;

// Format number for German locale
console.log(new Intl.NumberFormat("de-DE").format(number)); // Output: 1.234.567,89

const date = new Date("2024-06-15T12:00:00");

// Format date for French locale
const dateOptions = { year: "numeric", month: "long", day: "numeric", timeZone: "UTC" };
console.log(new Intl.DateTimeFormat("fr-FR", dateOptions).format(date)); // Output: 15 juin 2024
```

## Currency formatting

JavaScript allows you to format numbers as currency using the `Intl.NumberFormat` object with the `style` option set to `"currency"` and specifying the `currency` code.

```javascript
const amount = 1234567.89;

// Format as US dollars
console.log(new Intl.NumberFormat("en-US", { style: "currency", currency: "USD" }).format(amount)); // Output: $1,234,567.89

// Format as Euros
console.log(new Intl.NumberFormat("de-DE", { style: "currency", currency: "EUR" }).format(amount)); // Output: 1.234.567,89 €
```

## Percentage formatting

JavaScript allows you to format numbers as percentages using the `Intl.NumberFormat` object with the `style` option set to `"percent"`.

```javascript
const percentage = 0.1234;

// Format as percentage for US locale
console.log(new Intl.NumberFormat("en-US", { style: "percent" }).format(percentage)); // Output: 12%

// Format as percentage for German locale
console.log(new Intl.NumberFormat("de-DE", { style: "percent" }).format(percentage)); // Output: 12 %
```

## Number formatting

JavaScript allows you to format numbers using the `Intl.NumberFormat` object. You can customize the formatting by specifying options such as `minimumFractionDigits` and `maximumFractionDigits`.

```javascript
const number = 1234567.89;

// Format number for US locale with 2 decimal places
console.log(new Intl.NumberFormat("en-US", { minimumFractionDigits: 2, maximumFractionDigits: 2 }).format(number)); // Output: 1,234,567.89

// Format number for German locale with 2 decimal places
console.log(new Intl.NumberFormat("de-DE", { minimumFractionDigits: 2, maximumFractionDigits: 2 }).format(number)); // Output: 1.234.567,89
```

# Memory & Performance

## Stack vs heap

In JavaScript, memory is managed in two main areas: the stack and the heap.

- **Stack**: The stack is used for static memory allocation. It stores primitive values (numbers, strings, booleans, `null`, `undefined`, and symbols) and function call frames. Memory allocation and deallocation on the stack are fast because it follows the Last In, First Out (LIFO) principle.
- **Heap**: The heap is used for dynamic memory allocation. It stores objects, arrays, and functions. Memory management in the heap is more complex and is handled by the JavaScript engine's garbage collector.

Example:
```javascript
// Stack allocation
let x = 10; // Primitive value stored on the stack

// Heap allocation
let obj = { name: "Alice", age: 25 }; // Object stored on the heap
```

## Garbage Collection

JavaScript automatically manages memory through a process called garbage collection. The garbage collector identifies and frees memory that is no longer in use, primarily focusing on objects that are no longer reachable from the root.

Example:
```javascript
let obj = { name: "Alice" };
obj = null; // The object is now eligible for garbage collection
```

## Memory leaks

A memory leak occurs when a program retains memory that is no longer needed, preventing the garbage collector from reclaiming it. Memory leaks can lead to increased memory usage and degraded performance over time.

Example of a memory leak:
```javascript
function createLeak() {
  const largeArray = new Array(1000000).fill("leak");
  return () => largeArray; // The closure retains a reference to largeArray
}

const leak = createLeak();
```

## Detached DOM nodes

A detached DOM node is an element that has been removed from the document but is still referenced by JavaScript. Detached nodes can lead to memory leaks if they are not properly cleaned up.

Example of a detached DOM node:
```javascript
let element = document.createElement("div");
document.body.appendChild(element);
document.body.removeChild(element); // The element is now detached
// If we still have a reference to it, it won't be garbage collected
console.log(element);
```

## Unnecessary event listeners

Unnecessary event listeners occur when event handlers are attached to DOM elements but are never removed, even after the elements are no longer needed. This can prevent the elements from being garbage collected, leading to memory leaks.

Example of an unnecessary event listener:
```javascript
let button = document.createElement("button");
document.body.appendChild(button);

function handleClick() {
  console.log("Button clicked");
}

button.addEventListener("click", handleClick);

// Later, if the button is removed but the event listener is not removed
document.body.removeChild(button); // The button is now detached but still referenced by the event listener
```

## Closures and memory

Closures can retain references to variables from their outer scope, which can lead to memory leaks if not managed carefully. Even if the outer function has finished executing, the closure keeps the variables alive as long as it is reachable.

Example of a closure retaining memory:
```javascript
function outer() {
  const largeArray = new Array(1000000).fill("closure");
  return function inner() {
    return largeArray; // The inner function retains a reference to largeArray
  };
}

const closure = outer();
```

## Performance profiling

Performance profiling involves analyzing the runtime performance of your JavaScript code to identify bottlenecks and optimize memory usage. Modern browsers provide built-in tools for profiling memory usage and detecting memory leaks.

Example of using performance profiling in Chrome DevTools:
1. Open Chrome DevTools (F12 or Ctrl+Shift+I).
2. Go to the "Performance" tab.
3. Click "Record" and interact with your web page.
4. Click "Stop" to analyze the recorded performance.
5. Look for memory usage patterns and potential leaks in the "Memory" section.

## Browser DevTools Performance

Modern browsers provide powerful DevTools for performance profiling and memory analysis. These tools help developers identify memory leaks, optimize resource usage, and improve overall application performance.

Example of using Chrome DevTools for performance profiling:
1. Open Chrome DevTools (F12 or Ctrl+Shift+I).
2. Go to the "Performance" tab.
3. Click "Record" and interact with your web page.
4. Click "Stop" to analyze the recorded performance.
5. Use the "Memory" section to inspect memory usage and detect potential leaks.

## Browser Memory tools

Modern browsers provide memory analysis tools within their DevTools to help developers monitor and optimize memory usage. These tools allow you to take heap snapshots, track memory allocations, and detect memory leaks.

Example of using Chrome DevTools for memory analysis:
1. Open Chrome DevTools (F12 or Ctrl+Shift+I).
2. Go to the "Memory" tab.
3. Choose the type of memory snapshot you want to take (e.g., "Heap snapshot").
4. Click "Take snapshot" to capture the current memory state.
5. Analyze the snapshot to identify memory usage patterns and potential leaks.

## Lazy loading

Lazy loading is a design pattern that defers the initialization of an object until it is needed. This can help improve performance and reduce memory usage by avoiding unnecessary computations or resource allocations.

Example of lazy loading in JavaScript:
```javascript
let expensiveObject;

function getExpensiveObject() {
  if (!expensiveObject) {
    expensiveObject = { data: new Array(1000000).fill("lazy") };
  }
  return expensiveObject;
}

// The expensive object is only created when needed
const obj = getExpensiveObject();
```

## Code splitting

Code splitting is a technique that allows you to split your JavaScript code into smaller bundles that can be loaded on demand. This can help reduce the initial load time and memory usage of your application.

Example of code splitting in JavaScript using dynamic imports:
```javascript
// main.js
document.getElementById("loadButton").addEventListener("click", async () => {
  const module = await import("./expensiveModule.js");
  module.loadExpensiveFeature();
});

// expensiveModule.js
export function loadExpensiveFeature() {
  console.log("Expensive feature loaded");
}
```

## Memoization

Memoization is an optimization technique that stores the results of expensive function calls and returns the cached result when the same inputs occur again. This can help improve performance and reduce memory usage by avoiding redundant computations.

Example of memoization in JavaScript:
```javascript
function memoize(fn) {
  const cache = new Map();
  return function (...args) {
    const key = JSON.stringify(args);
    if (cache.has(key)) {
      return cache.get(key);
    }
    const result = fn(...args);
    cache.set(key, result);
    return result;
  };
}

// Example usage
const factorial = memoize(function (n) {
  if (n === 0) return 1;
  return n * factorial(n - 1);
});

console.log(factorial(5)); // Computed and cached
console.log(factorial(5)); // Retrieved from cache
```

## Efficient DOM manipulation

Efficient DOM manipulation involves minimizing direct interactions with the DOM, as these operations can be costly in terms of performance and memory usage. Techniques include batching updates, using document fragments, and leveraging virtual DOM libraries.

Example of efficient DOM manipulation using a document fragment:
```javascript
const fragment = document.createDocumentFragment();
for (let i = 0; i < 1000; i++) {
  const div = document.createElement("div");
  div.textContent = `Item ${i}`;
  fragment.appendChild(div);
}
document.getElementById("container").appendChild(fragment);
```

## Event delegation

Event delegation is a technique that leverages event bubbling to handle events efficiently by attaching a single event listener to a parent element instead of multiple child elements.

Example of event delegation in JavaScript:
```javascript
document.getElementById("container").addEventListener("click", (event) => {
  if (event.target && event.target.nodeName === "DIV") {
    console.log(`Clicked on ${event.target.textContent}`);
  }
});
```

## Debouncing

Debouncing is a technique used to limit the rate at which a function is executed. It ensures that a function is only called after a certain amount of time has passed since the last time it was invoked. This is particularly useful for handling events like window resizing or input changes.

Example of debouncing in JavaScript:
```javascript
function debounce(fn, delay) {
  let timeoutId;
  return function (...args) {
    clearTimeout(timeoutId);
    timeoutId = setTimeout(() => {
      fn(...args);
    }, delay);
  };
}

// Example usage
const handleResize = debounce(() => {
  console.log("Window resized");
}, 300);

window.addEventListener("resize", handleResize);
```

## Throttling

Throttling is a technique used to limit the rate at which a function is executed. It ensures that a function is called at most once in a specified time interval, regardless of how many times the event is triggered. This is useful for scenarios like handling scroll or resize events.

Example of throttling in JavaScript:
```javascript
function throttle(fn, limit) {
  let lastCall = 0;
  return function (...args) {
    const now = Date.now();
    if (now - lastCall >= limit) {
      lastCall = now;
      fn(...args);
    }
  };
}

// Example usage
const handleScroll = throttle(() => {
  console.log("Scrolled");
}, 300);

window.addEventListener("scroll", handleScroll);
```

# Security
Security in JavaScript involves protecting your application from common vulnerabilities such as Cross-Site Scripting (XSS), Cross-Site Request Forgery (CSRF), and ensuring safe handling of user input and sensitive data.

## XSS

Cross-Site Scripting (XSS) is a security vulnerability that allows attackers to inject malicious scripts into web pages viewed by other users. To prevent XSS, always sanitize and escape user input before rendering it in the DOM.

Example of preventing XSS in JavaScript:
```javascript
function escapeHTML(str) {
  const div = document.createElement("div");
  div.textContent = str;
  return div.innerHTML;
}

const userInput = "<script>alert('XSS');</script>";
const safeContent = escapeHTML(userInput);
document.getElementById("output").innerHTML = safeContent;
```

## DOM-based XSS

DOM-based Cross-Site Scripting (XSS) occurs when the vulnerability exists in the client-side code rather than the server-side code. It happens when untrusted data is written to the DOM without proper sanitization.

Example of preventing DOM-based XSS in JavaScript:
```javascript
function escapeHTML(str) {
  const div = document.createElement("div");
  div.textContent = str;
  return div.innerHTML;
}

const userInput = "<script>alert('DOM XSS');</script>";
const safeContent = escapeHTML(userInput);
document.getElementById("output").innerHTML = safeContent;
```

## SQL injection awareness

SQL injection is a security vulnerability that allows attackers to manipulate SQL queries by injecting malicious input. To prevent SQL injection, always use parameterized queries or prepared statements when interacting with a database.

Example of preventing SQL injection in JavaScript (using a hypothetical database library):
```javascript
const userInput = "someUserInput";
// Using a parameterized query to prevent SQL injection
const query = "SELECT * FROM users WHERE username = ?";
database.execute(query, [userInput]);
```

## CSRF (Cross-Site Request Forgery)

Cross-Site Request Forgery (CSRF) is a security vulnerability that tricks a user into performing actions on a web application without their consent. To prevent CSRF, use anti-CSRF tokens and ensure that state-changing requests are protected.

Example of using a CSRF token in JavaScript (hypothetical example):
```javascript
const csrfToken = document.querySelector('meta[name="csrf-token"]').getAttribute('content');

fetch("/update-profile", {
  method: "POST",
  headers: {
    "Content-Type": "application/json",
    "CSRF-Token": csrfToken
  },
  body: JSON.stringify({ username: "newUsername" })
});
```

## CORS

Cross-Origin Resource Sharing (CORS) is a security feature implemented by browsers to restrict web pages from making requests to a different domain than the one that served the web page. Properly configuring CORS headers on the server helps prevent unauthorized cross-origin requests.

Example of setting CORS headers on a server (Node.js with Express):
```javascript
const express = require("express");
const app = express();

app.use((req, res, next) => {
  res.header("Access-Control-Allow-Origin", "https://your-allowed-origin.com");
  res.header("Access-Control-Allow-Methods", "GET,POST,PUT,DELETE");
  res.header("Access-Control-Allow-Headers", "Content-Type, Authorization");
  next();
});

app.get("/data", (req, res) => {
  res.json({ message: "This is CORS-protected data." });
});

app.listen(3000, () => {
  console.log("Server running on port 3000");
});
```

## Content Security Policy (CSP)

Content Security Policy (CSP) is a security feature that helps prevent various types of attacks, including XSS, by specifying which sources of content are allowed to be loaded and executed by the browser.

Example of setting a Content Security Policy header in an Express.js server:
```javascript
const express = require("express");
const app = express();

app.use((req, res, next) => {
  res.setHeader("Content-Security-Policy", "default-src 'self'; script-src 'self'");
  next();
});

app.get("/", (req, res) => {
  res.send("Hello, world!");
});

app.listen(3000, () => {
  console.log("Server running on port 3000");
});
```

## Input validation

Input validation is the process of ensuring that user input meets the expected format, type, and constraints before processing it. Proper input validation helps prevent various security vulnerabilities, including XSS, SQL injection, and buffer overflow attacks.

Example of input validation in JavaScript:
```javascript
function validateUsername(username) {
  const usernameRegex = /^[a-zA-Z0-9_]{3,20}$/;
  return usernameRegex.test(username);
}

const userInput = "someUserInput";
if (validateUsername(userInput)) {
  console.log("Valid username");
} else {
  console.log("Invalid username");
}
```

## Output escaping

Output escaping is the process of ensuring that data is properly encoded before being rendered in the browser, preventing XSS attacks by neutralizing potentially malicious content.

Example of output escaping in JavaScript:
```javascript
function escapeHTML(str) {
  return str.replace(/&/g, "&amp;")
            .replace(/</g, "&lt;")
            .replace(/>/g, "&gt;")
            .replace(/"/g, "&quot;")
            .replace(/'/g, "&#039;");
}

const userInput = "<script>alert('XSS');</script>";
const safeOutput = escapeHTML(userInput);
console.log(safeOutput); // &lt;script&gt;alert(&#039;XSS&#039;);&lt;/script&gt;
```

## Secure localStorage usage

When using `localStorage` to store sensitive data, it's important to ensure that the data is properly encrypted and that access is controlled to prevent unauthorized access.

Example of secure localStorage usage in JavaScript:
```javascript
function encryptData(data, key) {
  // Simple encryption example (for demonstration purposes only)
  return btoa(JSON.stringify(data) + key);
}

function decryptData(encryptedData, key) {
  const decoded = atob(encryptedData);
  const jsonData = decoded.replace(key, "");
  return JSON.parse(jsonData);
}

const sensitiveData = { token: "secretToken" };
const encryptionKey = "mySecretKey";

// Store encrypted data in localStorage
localStorage.setItem("secureData", encryptData(sensitiveData, encryptionKey));

// Retrieve and decrypt data from localStorage
const storedData = localStorage.getItem("secureData");
const decryptedData = decryptData(storedData, encryptionKey);
console.log(decryptedData); // { token: "secretToken" }
```

## JWT security concepts

JSON Web Tokens (JWT) are a compact, URL-safe means of representing claims to be transferred between two parties. Proper handling of JWTs is crucial for maintaining secure authentication and authorization mechanisms.

Example of JWT usage in JavaScript:
```javascript
const jwt = require("jsonwebtoken");

const payload = { userId: 123 };
const secretKey = "mySecretKey";

// Generate a JWT
const token = jwt.sign(payload, secretKey, { expiresIn: "1h" });
console.log("Generated JWT:", token);

// Verify and decode a JWT
try {
  const decoded = jwt.verify(token, secretKey);
  console.log("Decoded JWT:", decoded);
} catch (err) {
  console.error("Invalid or expired JWT");
}
```

## Never trust client-side validation

Client-side validation can improve user experience by providing immediate feedback, but it should never be relied upon for security. Always perform server-side validation to ensure data integrity and prevent malicious input.

Example of server-side validation in JavaScript (Node.js with Express):
```javascript
const express = require("express");
const app = express();

app.use(express.json());

app.post("/submit", (req, res) => {
  const { username } = req.body;
  if (!username || typeof username !== "string" || username.length < 3) {
    return res.status(400).json({ error: "Invalid username" });
  }
  res.json({ message: "Username is valid" });
});

app.listen(3000, () => {
  console.log("Server running on port 3000");
});
```

## Prototype pollution

Prototype pollution is a security vulnerability that occurs when an attacker is able to modify the prototype of a base object, potentially leading to unexpected behavior and security issues.

Example of prototype pollution in JavaScript:
```javascript
const obj = {};
const maliciousPayload = JSON.parse('{"__proto__": {"isAdmin": true}}');
Object.assign(obj, maliciousPayload);
console.log({}.isAdmin); // true (prototype has been polluted)
```

## Preventing prototype pollution

To prevent prototype pollution, avoid directly merging untrusted input into objects and use libraries that safely handle object merging.

Example of safe object merging in JavaScript:
```javascript
const _ = require("lodash");

const obj = {};
const maliciousPayload = JSON.parse('{"__proto__": {"isAdmin": true}}');
_.merge(obj, maliciousPayload);
console.log({}.isAdmin); // undefined (prototype is not polluted)
```

# Functional Programming

## Pure functions

Pure functions are functions that, given the same input, will always return the same output and have no side effects.

Example of a pure function in JavaScript:
```javascript
function add(a, b) {
  return a + b;
}

console.log(add(2, 3)); // 5
console.log(add(2, 3)); // 5 (always returns the same result for the same input)
```

## Immutability

Immutability is a concept where data cannot be changed once it is created. Instead of modifying existing data, new data structures are created with the desired changes.

Example of immutability in JavaScript:
```javascript
const originalArray = [1, 2, 3];
const newArray = [...originalArray, 4]; // create a new array instead of modifying the original

console.log(originalArray); // [1, 2, 3]
console.log(newArray);      // [1, 2, 3, 4]
```

## First-class functions

First-class functions are functions that are treated as first-class citizens, meaning they can be assigned to variables, passed as arguments, and returned from other functions.

Example of first-class functions in JavaScript:
```javascript
function greet(name) {
  return `Hello, ${name}!`;
}

const sayHello = greet; // assign function to a variable
console.log(sayHello("Alice")); // Hello, Alice!

function callFunction(fn, value) {
  return fn(value); // pass function as an argument
}

console.log(callFunction(greet, "Bob")); // Hello, Bob!
```

## Higher-order functions

Higher-order functions are functions that can take other functions as arguments or return functions as their result.

Example of higher-order functions in JavaScript:
```javascript
function multiplyBy(factor) {
  return function (number) {
    return number * factor;
  };
}

const double = multiplyBy(2); // returns a function that multiplies by 2
console.log(double(5)); // 10

const triple = multiplyBy(3); // returns a function that multiplies by 3
console.log(triple(5)); // 15
```

## Function composition

Function composition is the process of combining two or more functions to produce a new function.

Example of function composition in JavaScript:
```javascript
function add2(x) {
  return x + 2;
}

function multiplyBy3(x) {
  return x * 3;
}

const add2ThenMultiplyBy3 = (x) => multiplyBy3(add2(x));
console.log(add2ThenMultiplyBy3(4)); // (4 + 2) * 3 = 18
```

## Currying

Currying is the process of transforming a function with multiple arguments into a sequence of functions, each taking a single argument.

Example of currying in JavaScript:
```javascript
function multiply(a) {
  return function (b) {
    return a * b;
  };
}

const multiplyBy2 = multiply(2);
console.log(multiplyBy2(5)); // 10

const multiplyBy3 = multiply(3);
console.log(multiplyBy3(5)); // 15
```

## Partial application

Partial application is the process of fixing a number of arguments to a function, producing a new function with fewer arguments.

Example of partial application in JavaScript:
```javascript
function multiply(a, b) {
  return a * b;
}

const multiplyBy2 = multiply.bind(null, 2);
console.log(multiplyBy2(5)); // 10

const multiplyBy3 = multiply.bind(null, 3);
console.log(multiplyBy3(5)); // 15
```

## Map

Map is a method available on arrays that creates a new array populated with the results of calling a provided function on every element in the calling array.

Example of using `map` in JavaScript:
```javascript
const numbers = [1, 2, 3, 4, 5];
const doubled = numbers.map((num) => num * 2);
console.log(doubled); // [2, 4, 6, 8, 10]
```

## Filter

Filter is a method available on arrays that creates a new array with all elements that pass the test implemented by the provided function.

Example of using `filter` in JavaScript:
```javascript
const numbers = [1, 2, 3, 4, 5];
const evenNumbers = numbers.filter((num) => num % 2 === 0);
console.log(evenNumbers); // [2, 4]
```

## Reduce

Reduce is a method available on arrays that executes a reducer function on each element of the array, resulting in a single output value.

Example of using `reduce` in JavaScript:
```javascript
const numbers = [1, 2, 3, 4, 5];
const sum = numbers.reduce((accumulator, currentValue) => accumulator + currentValue, 0);
console.log(sum); // 15
```

## Referential transparency

Referential transparency is a property of pure functions where the function can be replaced with its output value without changing the program's behavior.

Example of referential transparency in JavaScript:
```javascript
function add(a, b) {
  return a + b;
}

const result = add(2, 3);
console.log(result); // 5
```

## Side effects

Side effects are any changes in state or observable interactions with the outside world that occur during the execution of a function, such as modifying a global variable, writing to the console, or making a network request.

Example of side effects in JavaScript:
```javascript
let counter = 0;

function incrementCounter() {
  counter++;
}

incrementCounter();
console.log(counter); // 1
```

## Declarative programming

Declarative programming is a programming paradigm that expresses the logic of a computation without describing its control flow. In JavaScript, this often involves using higher-order functions like `map`, `filter`, and `reduce` instead of loops and mutable state.

Example of declarative programming in JavaScript:
```javascript
const numbers = [1, 2, 3, 4, 5];
const doubled = numbers.map((num) => num * 2);
console.log(doubled); // [2, 4, 6, 8, 10]
```

# Advanced Browser Concepts

## Rendering pipeline

The rendering pipeline is the sequence of steps the browser takes to convert HTML, CSS, and JavaScript into pixels on the screen. It involves parsing HTML to create the DOM, parsing CSS to create the CSSOM, combining them into the render tree, layout, and painting.

Example of the rendering pipeline in action:
```javascript
// HTML
// <div id="app">Hello World</div>

// CSS
// #app { color: red; }

// JavaScript
const app = document.getElementById('app');
app.textContent = 'Hello Rendering Pipeline';
```

## Reflow

Reflow (also known as layout) is the process by which the browser calculates the positions and sizes of elements in the render tree. Reflow can be triggered by changes to the DOM or CSS that affect the layout.

Example of reflow in action:
```javascript
const app = document.getElementById('app');
app.style.width = '200px'; // This will trigger a reflow
```

## Repaint

Repaint is the process by which the browser updates the pixels on the screen when an element's appearance changes but its layout remains the same. Repaint can be triggered by changes to CSS properties like `color`, `background-color`, or `visibility`.

Example of repaint in action:
```javascript
const app = document.getElementById('app');
app.style.color = 'blue'; // This will trigger a repaint
```

## Layout

Layout is the process by which the browser calculates the exact position and size of each element in the render tree. Layout is typically triggered by reflow.

Example of layout in action:
```javascript
const app = document.getElementById('app');
app.style.height = '100px'; // This will trigger a layout
```

## Compositing

Compositing is the process by which the browser combines different layers of the render tree into a single image that is displayed on the screen. Compositing typically occurs after layout and painting.

Example of compositing in action:
```javascript
const app = document.getElementById('app');
app.style.transform = 'translateZ(0)'; // This will trigger compositing
```

## Critical rendering concepts

Critical rendering concepts refer to the key steps and processes involved in rendering a web page efficiently. Understanding these concepts helps in optimizing web performance and ensuring smooth user experiences.

Some critical rendering concepts include:
- **DOM (Document Object Model)**: The tree structure representing the HTML content.
- **CSSOM (CSS Object Model)**: The tree structure representing the CSS styles.
- **Render Tree**: The combination of the DOM and CSSOM that represents what will be displayed on the screen.
- **Reflow/Layout**: The process of calculating the positions and sizes of elements.
- **Repaint**: The process of updating the pixels on the screen when an element's appearance changes.
- **Compositing**: The process of combining different layers into a single image for display.

## requestAnimationFrame

`requestAnimationFrame` is a method that tells the browser to execute a specified callback function before the next repaint. It is commonly used for creating smooth animations and optimizing rendering performance.

Example of `requestAnimationFrame` in action:
```javascript
const app = document.getElementById('app');
let start = null;

function step(timestamp) {
  if (!start) start = timestamp;
  const progress = timestamp - start;
  app.style.transform = `translateX(${Math.min(progress / 10, 200)}px)`;
  if (progress < 2000) {
    requestAnimationFrame(step);
  }
}

requestAnimationFrame(step);
```

## Intersection Observer

The Intersection Observer API provides a way to asynchronously observe changes in the intersection of a target element with an ancestor element or with a top-level document's viewport. It is commonly used for lazy loading images, infinite scrolling, and triggering animations when elements come into view.

Example of `IntersectionObserver` in action:
```javascript
const app = document.getElementById('app');

const observer = new IntersectionObserver((entries) => {
  entries.forEach(entry => {
    if (entry.isIntersecting) {
      console.log('App is in view!');
    }
  });
});

observer.observe(app);
```

## Mutation Observer

The Mutation Observer API provides a way to asynchronously observe changes to the DOM tree. It is commonly used for detecting when elements are added, removed, or modified in the DOM.

Example of `MutationObserver` in action:
```javascript
const app = document.getElementById('app');

const observer = new MutationObserver((mutationsList) => {
  for (const mutation of mutationsList) {
    if (mutation.type === 'childList') {
      console.log('A child node has been added or removed.');
    } else if (mutation.type === 'attributes') {
      console.log(`The ${mutation.attributeName} attribute was modified.`);
    }
  }
});

observer.observe(app, { attributes: true, childList: true, subtree: true });
```

## Resize Observer

The Resize Observer API provides a way to asynchronously observe changes to the dimensions of an element. It is commonly used for responsive design and layout adjustments.

Example of `ResizeObserver` in action:
```javascript
const app = document.getElementById('app');

const resizeObserver = new ResizeObserver((entries) => {
  for (const entry of entries) {
    console.log('Element size changed:', entry.contentRect);
  }
});

resizeObserver.observe(app);
```

## Web Workers

The Web Workers API provides a way to run JavaScript code in the background, on a separate thread from the main execution thread. It is commonly used for performing computationally intensive tasks without blocking the user interface.

Example of `Web Worker` in action:
```javascript
// main.js
const worker = new Worker('worker.js');

worker.onmessage = (event) => {
  console.log('Message from worker:', event.data);
};

worker.postMessage('Hello, worker!');
```

```javascript
// worker.js
onmessage = (event) => {
  console.log('Message from main thread:', event.data);
  postMessage('Hello, main thread!');
};
```

## Service Workers

The Service Workers API provides a way to run scripts in the background, separate from the web page, enabling features like offline support, background sync, and push notifications.

Example of `Service Worker` in action:
```javascript
// main.js
if ('serviceWorker' in navigator) {
  navigator.serviceWorker.register('/service-worker.js')
    .then((registration) => {
      console.log('Service Worker registered with scope:', registration.scope);
    })
    .catch((error) => {
      console.log('Service Worker registration failed:', error);
    });
}
```

```javascript
// service-worker.js
self.addEventListener('install', (event) => {
  console.log('Service Worker installing.');
});

self.addEventListener('activate', (event) => {
  console.log('Service Worker activated.');
});
```

## WebSockets

The WebSockets API provides a way to establish a persistent, full-duplex communication channel between the client and the server. It is commonly used for real-time applications like chat apps and live notifications.

Example of `WebSocket` in action:
```javascript
// client.js
const socket = new WebSocket('ws://localhost:8080');

socket.onopen = () => {
  console.log('WebSocket connection established.');
  socket.send('Hello, server!');
};

socket.onmessage = (event) => {
  console.log('Message from server:', event.data);
};

socket.onclose = () => {
  console.log('WebSocket connection closed.');
};
```

## Server-Sent Events

The Server-Sent Events (SSE) API provides a way for the server to push updates to the client over a single HTTP connection. It is commonly used for real-time notifications and live updates.

Example of `Server-Sent Events` in action:
```javascript
// client.js
const eventSource = new EventSource('/events');

eventSource.onmessage = (event) => {
  console.log('Message from server:', event.data);
};

eventSource.onerror = (error) => {
  console.log('EventSource failed:', error);
};
```

## IndexedDB

The IndexedDB API provides a way to store large amounts of structured data in the browser. It is commonly used for offline storage and caching.

Example of `IndexedDB` in action:
```javascript
// main.js
const request = indexedDB.open('myDatabase', 1);

request.onupgradeneeded = (event) => {
  const db = event.target.result;
  const objectStore = db.createObjectStore('myStore', { keyPath: 'id' });
  objectStore.createIndex('name', 'name', { unique: false });
};

request.onsuccess = (event) => {
  const db = event.target.result;
  const transaction = db.transaction('myStore', 'readwrite');
  const objectStore = transaction.objectStore('myStore');
  objectStore.add({ id: 1, name: 'John Doe' });
};

request.onerror = (event) => {
  console.log('IndexedDB error:', event.target.error);
};
```

## Cache API

The Cache API provides a way to store and retrieve network requests and responses in the browser. It is commonly used for offline support and improving performance.

Example of `Cache API` in action:
```javascript
// main.js
caches.open('my-cache').then((cache) => {
  cache.add('/index.html');
  cache.add('/styles.css');
});

caches.match('/index.html').then((response) => {
  if (response) {
    console.log('Cache hit:', response);
  } else {
    console.log('Cache miss');
  }
});
```

# JavaScript Design Patterns

## Module Pattern

The Module Pattern is used to create self-contained modules with private and public members. It helps in organizing code and avoiding global namespace pollution.

Example of `Module Pattern` in action:
```javascript
const myModule = (() => {
  // Private members
  let privateVar = 'I am private';

  const privateMethod = () => {
    console.log(privateVar);
  };

  // Public members
  return {
    publicMethod: () => {
      privateMethod();
    }
  };
})();

myModule.publicMethod(); // Output: I am private
```

## Revealing module pattern

The Revealing Module Pattern is a variation of the Module Pattern where the public members are explicitly returned, revealing only the parts of the module that should be accessible from outside.

Example of `Revealing Module Pattern` in action:
```javascript
const myRevealingModule = (() => {
  // Private members
  let privateVar = 'I am private';

  const privateMethod = () => {
    console.log(privateVar);
  };

  // Public members
  const publicMethod = () => {
    privateMethod();
  };

  return {
    publicMethod
  };
})();

myRevealingModule.publicMethod(); // Output: I am private
```

## Factory pattern

The Factory Pattern is used to create objects without specifying the exact class of the object that will be created. It provides a way to encapsulate the object creation logic.

Example of `Factory Pattern` in action:
```javascript
const createPerson = (name, age) => {
  return {
    name,
    age,
    describe() {
      console.log(`Name: ${name}, Age: ${age}`);
    }
  };
};

const person1 = createPerson('John Doe', 30);
const person2 = createPerson('Jane Doe', 25);

person1.describe(); // Output: Name: John Doe, Age: 30
person2.describe(); // Output: Name: Jane Doe, Age: 25
```

## Constructor Pattern

The Constructor Pattern is used to create instances of objects using a constructor function. It allows for the creation of multiple objects with similar properties and methods.

Example of `Constructor Pattern` in action:
```javascript
function Person(name, age) {
  this.name = name;
  this.age = age;
  this.describe = function() {
    console.log(`Name: ${this.name}, Age: ${this.age}`);
  };
}

const person1 = new Person('John Doe', 30);
const person2 = new Person('Jane Doe', 25);

person1.describe(); // Output: Name: John Doe, Age: 30
person2.describe(); // Output: Name: Jane Doe, Age: 25
```

## Singleton Pattern

The Singleton Pattern ensures that a class has only one instance and provides a global point of access to it.

Example of `Singleton Pattern` in action:
```javascript
const Singleton = (() => {
  let instance;

  const createInstance = () => {
    return {
      name: 'I am the only instance'
    };
  };

  return {
    getInstance: () => {
      if (!instance) {
        instance = createInstance();
      }
      return instance;
    }
  };
})();

const instance1 = Singleton.getInstance();
const instance2 = Singleton.getInstance();

console.log(instance1 === instance2); // Output: true
```

## Observer pattern

The Observer Pattern is used to create a subscription mechanism to allow multiple objects to listen and react to events or changes in another object.

Example of `Observer Pattern` in action:
```javascript
class Subject {
  constructor() {
    this.observers = [];
  }

  subscribe(observer) {
    this.observers.push(observer);
  }

  unsubscribe(observer) {
    this.observers = this.observers.filter(obs => obs !== observer);
  }

  notify(data) {
    this.observers.forEach(observer => observer.update(data));
  }
}

class Observer {
  constructor(name) {
    this.name = name;
  }

  update(data) {
    console.log(`${this.name} received data: ${data}`);
  }
}

const subject = new Subject();
const observer1 = new Observer('Observer 1');
const observer2 = new Observer('Observer 2');

subject.subscribe(observer1);
subject.subscribe(observer2);

subject.notify('Some data'); 
// Output:
// Observer 1 received data: Some data
// Observer 2 received data: Some data
```

## Pub/Sub pattern

The Pub/Sub (Publisher/Subscriber) Pattern is used to create a messaging system where publishers send messages without knowing who will receive them, and subscribers listen for specific messages.

Example of `Pub/Sub Pattern` in action:
```javascript
class PubSub {
  constructor() {
    this.events = {};
  }

  subscribe(event, callback) {
    if (!this.events[event]) {
      this.events[event] = [];
    }
    this.events[event].push(callback);
  }

  unsubscribe(event, callback) {
    if (!this.events[event]) return;
    this.events[event] = this.events[event].filter(cb => cb !== callback);
  }

  publish(event, data) {
    if (!this.events[event]) return;
    this.events[event].forEach(callback => callback(data));
  }
}

const pubSub = new PubSub();

const subscriber1 = data => console.log(`Subscriber 1 received: ${data}`);
const subscriber2 = data => console.log(`Subscriber 2 received: ${data}`);

pubSub.subscribe('event1', subscriber1);
pubSub.subscribe('event1', subscriber2);

pubSub.publish('event1', 'Some data');
// Output:
// Subscriber 1 received: Some data
// Subscriber 2 received: Some data
```

## Strategy pattern

The Strategy Pattern is used to define a family of algorithms, encapsulate each one, and make them interchangeable. This allows the algorithm to vary independently from the clients that use it.

Example of `Strategy Pattern` in action:
```javascript
class Context {
  constructor(strategy) {
    this.strategy = strategy;
  }

  setStrategy(strategy) {
    this.strategy = strategy;
  }

  executeStrategy(data) {
    return this.strategy.doAlgorithm(data);
  }
}

class ConcreteStrategyA {
  doAlgorithm(data) {
    return data.sort();
  }
}

class ConcreteStrategyB {
  doAlgorithm(data) {
    return data.reverse();
  }
}

const context = new Context(new ConcreteStrategyA());
console.log(context.executeStrategy([3, 1, 2])); // Output: [1, 2, 3]

context.setStrategy(new ConcreteStrategyB());
console.log(context.executeStrategy([3, 1, 2])); // Output: [2, 1, 3]
```

## Adapter pattern

The Adapter Pattern is used to allow incompatible interfaces to work together. It acts as a bridge between two incompatible interfaces.

Example of `Adapter Pattern` in action:
```javascript
class Target {
  request() {
    return 'Target: The default target\'s behavior.';
  }
}

class Adaptee {
  specificRequest() {
    return '.eetpadA eht fo roivaheb laicepS';
  }
}

class Adapter extends Target {
  constructor(adaptee) {
    super();
    this.adaptee = adaptee;
  }

  request() {
    const result = this.adaptee.specificRequest().split('').reverse().join('');
    return `Adapter: (TRANSLATED) ${result}`;
  }
}

const adaptee = new Adaptee();
const adapter = new Adapter(adaptee);
console.log(adapter.request());
// Output:
// Adapter: (TRANSLATED) Special behavior of the Adaptee.
```

## Decorator pattern

The Decorator Pattern is used to add new functionality to an existing object without altering its structure. It is typically used to extend the behavior of classes in a flexible and reusable way.

Example of `Decorator Pattern` in action:
```javascript
class Component {
  operation() {
    return 'Component';
  }
}

class Decorator {
  constructor(component) {
    this.component = component;
  }

  operation() {
    return this.component.operation();
  }
}

class ConcreteDecoratorA extends Decorator {
  operation() {
    return `ConcreteDecoratorA(${super.operation()})`;
  }
}

class ConcreteDecoratorB extends Decorator {
  operation() {
    return `ConcreteDecoratorB(${super.operation()})`;
  }
}

const component = new Component();
const decoratorA = new ConcreteDecoratorA(component);
const decoratorB = new ConcreteDecoratorB(decoratorA);
console.log(decoratorB.operation());
// Output:
// ConcreteDecoratorB(ConcreteDecoratorA(Component))
```

## Proxy pattern

The Proxy Pattern is used to provide a surrogate or placeholder for another object to control access to it. It is typically used for lazy initialization, access control, logging, or caching.

Example of `Proxy Pattern` in action:
```javascript
class RealSubject {
  request() {
    return 'RealSubject: Handling request.';
  }
}

class Proxy {
  constructor(realSubject) {
    this.realSubject = realSubject;
  }

  request() {
    if (this.checkAccess()) {
      return this.realSubject.request();
    } else {
      return 'Proxy: Access denied.';
    }
  }

  checkAccess() {
    // Simulate access control
    return true;
  }
}

const realSubject = new RealSubject();
const proxy = new Proxy(realSubject);
console.log(proxy.request());
// Output:
// RealSubject: Handling request.
```

## Command pattern

The Command Pattern is used to encapsulate a request as an object, thereby allowing for parameterization of clients with queues, requests, and operations. It is typically used to implement undo/redo functionality, logging, and transactional behavior.

Example of `Command Pattern` in action:
```javascript
class Command {
  execute() {}
}

class Receiver {
  action() {
    return 'Receiver: Executing action.';
  }
}

class ConcreteCommand extends Command {
  constructor(receiver) {
    super();
    this.receiver = receiver;
  }

  execute() {
    return this.receiver.action();
  }
}

class Invoker {
  setCommand(command) {
    this.command = command;
  }

  executeCommand() {
    return this.command.execute();
  }
}

const receiver = new Receiver();
const command = new ConcreteCommand(receiver);
const invoker = new Invoker();
invoker.setCommand(command);
console.log(invoker.executeCommand());
// Output:
// Receiver: Executing action.
```

## Dependency Injection pattern

The Dependency Injection Pattern is used to decouple the creation of an object's dependencies from the object's behavior, allowing for more flexible and testable code. It is typically used to manage dependencies and promote inversion of control.

Example of `Dependency Injection Pattern` in action:
```javascript
class Service {
  serve() {
    return 'Service: Serving...';
  }
}

class Client {
  constructor(service) {
    this.service = service;
  }

  doSomething() {
    return this.service.serve();
  }
}

const service = new Service();
const client = new Client(service);
console.log(client.doSomething());
// Output:
// Service: Serving...
```

## Composition pattern

The Composition Pattern is used to build complex objects by combining simpler ones, promoting code reuse and flexibility. It is typically used to represent part-whole hierarchies and to achieve polymorphic behavior without inheritance.

Example of `Composition Pattern` in action:
```javascript
class Component {
  operation() {
    return 'Component: Operation';
  }
}

class Composite {
  constructor() {
    this.children = [];
  }

  add(component) {
    this.children.push(component);
  }

  operation() {
    return this.children.map(child => child.operation()).join(' + ');
  }
}

const component1 = new Component();
const component2 = new Component();
const composite = new Composite();
composite.add(component1);
composite.add(component2);
console.log(composite.operation());
// Output:
// Component: Operation + Component: Operation
```

# Node.js JavaScript

## What is Node.js?

Node.js is a JavaScript runtime built on Chrome's V8 JavaScript engine. It allows developers to run JavaScript on the server side, enabling the creation of scalable and high-performance web applications. Node.js uses an event-driven, non-blocking I/O model, making it efficient and suitable for real-time applications.

## Key Features of Node.js

- **Asynchronous and Event-Driven:** All APIs of Node.js library are asynchronous, meaning non-blocking. It essentially means a Node.js-based server never waits for an API to return data.
- **Single-Threaded but Highly Scalable:** Node.js uses a single-threaded model with event looping. The event mechanism helps the server respond in a non-blocking way and makes the server highly scalable.
- **Fast Execution:** Built on Chrome's V8 JavaScript engine, Node.js executes code very fast.
- **Cross-Platform:** Node.js can be run on various platforms (Windows, Linux, Unix, Mac OS X, etc.).
- **NPM (Node Package Manager):** Node.js comes with a built-in package manager called NPM, which provides access to thousands of reusable packages.
- **Community Support:** Node.js has a large and active community that contributes to its growth and provides support.

## Node.js runtime

The Node.js runtime provides the environment in which JavaScript code can be executed on the server side. It includes the V8 JavaScript engine, an event loop, and a set of built-in modules for handling various server-side tasks such as file system operations, networking, and HTTP server creation. The runtime is designed to be non-blocking and event-driven, allowing for high concurrency and efficient handling of I/O operations.

## V8 JavaScript Engine

Node.js uses the V8 JavaScript engine developed by Google for Chrome. V8 compiles JavaScript directly to native machine code, resulting in high performance and fast execution. It also provides features like just-in-time (JIT) compilation and efficient memory management, which contribute to the overall speed and efficiency of Node.js applications.

## Node event loop

The Node.js event loop is a core feature that enables non-blocking I/O operations. It allows Node.js to handle multiple operations concurrently without creating multiple threads. The event loop continuously checks the event queue for pending callbacks and executes them one by one. This mechanism ensures that the server remains responsive and can efficiently manage a large number of simultaneous connections. The event loop operates in phases, including timers, I/O callbacks, idle, and poll, each responsible for handling different types of events.

## CommonJS

CommonJS is a module system used in Node.js to organize and structure code into reusable modules. Each file in Node.js is treated as a separate module, and CommonJS provides the `require` function to import modules and the `module.exports` object to export functionality from a module. This system allows developers to break down their code into smaller, manageable pieces and promotes code reuse and maintainability. CommonJS modules are synchronous, meaning the `require` function blocks the execution until the module is fully loaded.

## ES Modules (ESM)

ES Modules (ESM) is a standardized module system in JavaScript that allows for the use of `import` and `export` statements to manage dependencies and organize code. Unlike CommonJS, ESM supports asynchronous loading of modules and is designed to work natively in both browsers and Node.js. In Node.js, ESM can be used by either setting the `"type": "module"` field in the `package.json` file or by using the `.mjs` file extension. ESM promotes better interoperability and is the preferred module system for modern JavaScript development.

## npm

npm (Node Package Manager) is the default package manager for Node.js. It allows developers to easily install, manage, and share reusable code packages (modules) from the npm registry. npm simplifies dependency management by providing a way to specify project dependencies in a `package.json` file and automatically handle their installation and versioning. It also offers scripts and tools for automating common development tasks, making it an essential part of the Node.js ecosystem.

## npx

npx is a package runner tool that comes with npm. It allows developers to execute Node.js packages without globally installing them. This is particularly useful for running one-off commands or using CLI tools that are not needed as permanent dependencies in a project. npx automatically downloads the specified package, runs it, and then removes it, ensuring that the system remains clean and avoiding version conflicts with globally installed packages.

## package.json

The `package.json` file is a crucial component of a Node.js project. It contains metadata about the project, such as its name, version, description, main entry point, scripts, and dependencies. This file allows npm to manage the project's dependencies and provides a standardized way to define project information and configuration. The `package.json` file is essential for sharing and distributing Node.js projects, as it ensures that all necessary dependencies and scripts are properly defined and can be easily installed by other developers.

```json
{
  "name": "my-project",
  "version": "1.0.0",
  "description": "A sample Node.js project",
  "main": "index.js",
  "scripts": {
    "start": "node index.js"
  },
  "dependencies": {
    "express": "^4.17.1"
  }
}
```

## package-lock.json

The `package-lock.json` file is automatically generated by npm when installing dependencies. It records the exact versions of the installed packages and their dependency tree, ensuring that the same versions are installed if the project is set up on a different machine or environment. This file helps maintain consistency and reproducibility of the project's dependencies, preventing potential issues caused by version discrepancies. It should be committed to version control along with the `package.json` file.

```json
{
  "name": "my-project",
  "version": "1.0.0",
  "lockfileVersion": 1,
  "requires": true,
  "dependencies": {
    "express": {
      "version": "4.17.1",
      "resolved": "https://registry.npmjs.org/express/-/express-4.17.1.tgz",
      "integrity": "sha512-...",
      "requires": {
        "accepts": "~1.3.7",
        "array-flatten": "1.1.1",
        "body-parser": "1.19.0",
        "content-disposition": "0.5.3",
        "content-type": "~1.0.4",
        "cookie": "0.4.0",
        "cookie-signature": "1.0.6",
        "debug": "2.6.9",
        "depd": "~1.1.2",
        "encodeurl": "~1.0.2",
        "escape-html": "~1.0.3",
        "etag": "~1.8.1",
        "finalhandler": "1.1.2",
        "fresh": "0.5.2",
        "merge-descriptors": "1.0.1",
        "methods": "~1.1.2",
        "on-finished": "~2.3.0",
        "parseurl": "~1.3.3",
        "path-to-regexp": "0.1.7",
        "proxy-addr": "~2.0.5",
        "qs": "6.7.0",
        "range-parser": "~1.2.1",
        "safe-buffer": "5.1.2",
        "send": "0.17.1",
        "serve-static": "1.14.1",
        "setprototypeof": "1.1.1",
        "statuses": "~1.5.0",
        "type-is": "~1.6.18",
        "utils-merge": "1.0.1",
        "vary": "~1.1.2"
      }
    }
  }
}
```

## npm scripts

Npm scripts are custom commands defined in the `scripts` section of the `package.json` file. They allow you to automate common tasks such as starting the application, running tests, building the project, and more. You can run these scripts using the `npm run <script-name>` command.

Example:

```json
"scripts": {
  "start": "node index.js",
  "test": "mocha",
  "build": "webpack"
}
```

## Installing packages

To install a package using npm, you can use the `npm install <package-name>` command. This will add the package to your `node_modules` directory and update the `package.json` and `package-lock.json` files accordingly.

Example:

```bash
npm install express
```

## fs

The `fs` module in Node.js provides an API for interacting with the file system. It allows you to read, write, update, and delete files and directories. The `fs` module can be used in both synchronous and asynchronous ways.

Example of reading a file asynchronously:

```javascript
const fs = require('fs');

fs.readFile('example.txt', 'utf8', (err, data) => {
  if (err) {
    console.error(err);
    return;
  }
  console.log(data);
});
```

Example of writing to a file asynchronously:

```javascript
const fs = require('fs');

fs.writeFile('example.txt', 'Hello, world!', 'utf8', (err) => {
  if (err) {
    console.error(err);
    return;
  }
  console.log('File has been written');
});
```

Example of reading a file synchronously:

```javascript
const fs = require('fs');

try {
  const data = fs.readFileSync('example.txt', 'utf8');
  console.log(data);
} catch (err) {
  console.error(err);
}
```

Example of writing to a file synchronously:

```javascript
const fs = require('fs');

try {
  fs.writeFileSync('example.txt', 'Hello, world!', 'utf8');
  console.log('File has been written');
} catch (err) {
  console.error(err);
}
```

## fs promises

The `fs.promises` API provides an alternative set of asynchronous file system methods that return promises, allowing you to use `async`/`await` syntax for cleaner and more readable code.

Example of reading a file using `fs.promises`:

```javascript
const fs = require('fs').promises;

async function readFile() {
  try {
    const data = await fs.readFile('example.txt', 'utf8');
    console.log(data);
  } catch (err) {
    console.error(err);
  }
}

readFile();
```

Example of writing to a file using `fs.promises`:

```javascript
const fs = require('fs').promises;

async function writeFile() {
  try {
    await fs.writeFile('example.txt', 'Hello, world!', 'utf8');
    console.log('File has been written');
  } catch (err) {
    console.error(err);
  }
}

writeFile();
```

## Path module

The `path` module in Node.js provides utilities for working with file and directory paths. It helps in handling and transforming file paths in a way that is compatible across different operating systems.

Example of using the `path` module:

```javascript
const path = require('path');

const filePath = path.join(__dirname, 'example.txt');
console.log(filePath);
```

Example of getting the directory name of a file path:

```javascript
const path = require('path');

const filePath = path.join(__dirname, 'example.txt');
const dirName = path.dirname(filePath);
console.log(dirName);
```

Example of getting the file extension of a file path:

```javascript
const path = require('path');

const filePath = path.join(__dirname, 'example.txt');
const fileExt = path.extname(filePath);
console.log(fileExt);
```

Example of getting the base name of a file path:

```javascript
const path = require('path');

const filePath = path.join(__dirname, 'example.txt');
const baseName = path.basename(filePath);
console.log(baseName);
```

Example of getting the file name without the extension:

```javascript
const path = require('path');

const filePath = path.join(__dirname, 'example.txt');
const fileNameWithoutExt = path.basename(filePath, path.extname(filePath));
console.log(fileNameWithoutExt);
```

## URL module

The `url` module in Node.js provides utilities for URL resolution and parsing. It helps in working with URLs in a structured way.

Example of parsing a URL:

```javascript
const url = require('url');

const myURL = new URL('https://example.com:8080/path/name?query=string#hash');
console.log(myURL.hostname); // 'example.com'
console.log(myURL.port);     // '8080'
console.log(myURL.pathname); // '/path/name'
console.log(myURL.search);   // '?query=string'
console.log(myURL.hash);     // '#hash'
```
Example of formatting a URL:

```javascript
const url = require('url');

const myURL = new URL('https://example.com:8080/path/name?query=string#hash');
const formattedURL = url.format({
  protocol: myURL.protocol,
  hostname: myURL.hostname,
  port: myURL.port,
  pathname: myURL.pathname,
  search: myURL.search,
  hash: myURL.hash
});
console.log(formattedURL); // 'https://example.com:8080/path/name?query=string#hash'
```

## http

The `http` module in Node.js allows you to create HTTP servers and make HTTP requests. It is a core module for handling HTTP communication.

Example of creating a simple HTTP server:

```javascript
const http = require('http');

const server = http.createServer((req, res) => {
  res.statusCode = 200;
  res.setHeader('Content-Type', 'text/plain');
  res.end('Hello, World!\n');
});

server.listen(3000, () => {
  console.log('Server running at http://localhost:3000/');
});
```

Example of making an HTTP GET request:

```javascript
const http = require('http');

http.get('http://www.example.com', (res) => {
  let data = '';

  res.on('data', (chunk) => {
    data += chunk;
  });

  res.on('end', () => {
    console.log(data);
  });
}).on('error', (err) => {
  console.error(`Error: ${err.message}`);
});
```

Example of making different-different path requests:

```javascript
const http = require('http');

const paths = ['/path1', '/path2', '/path3'];

paths.forEach((path) => {
  http.get(`http://www.example.com${path}`, (res) => {
    let data = '';

    res.on('data', (chunk) => {
      data += chunk;
    });

    res.on('end', () => {
      console.log(`Response for ${path}:`);
      console.log(data);
    });
  }).on('error', (err) => {
    console.error(`Error for ${path}: ${err.message}`);
  });
});
```

## https

The `https` module in Node.js allows you to create HTTPS servers and make HTTPS requests. It is similar to the `http` module but provides secure communication over SSL/TLS.

Example of making an HTTPS GET request:

```javascript
const https = require('https');

https.get('https://www.example.com', (res) => {
  let data = '';

  res.on('data', (chunk) => {
    data += chunk;
  });

  res.on('end', () => {
    console.log(data);
  });
}).on('error', (err) => {
  console.error(`Error: ${err.message}`);
});
```

Example of making different-different path HTTPS requests:

```javascript
const https = require('https');

const paths = ['/path1', '/path2', '/path3'];

paths.forEach((path) => {
  https.get(`https://www.example.com${path}`, (res) => {
    let data = '';

    res.on('data', (chunk) => {
      data += chunk;
    });

    res.on('end', () => {
      console.log(`Response for ${path}:`);
      console.log(data);
    });
  }).on('error', (err) => {
    console.error(`Error for ${path}: ${err.message}`);
  });
});
```

## events

The `events` module in Node.js allows you to work with events and event-driven programming. You can create an event emitter and listen for events.

Example of using the `events` module:

```javascript
const EventEmitter = require('events');

class MyEmitter extends EventEmitter {}

const myEmitter = new MyEmitter();

myEmitter.on('event', () => {
  console.log('An event occurred!');
});

myEmitter.emit('event');
```

### events methods

Some commonly used methods of the `events` module are:

- `on(event, listener)`: Adds a listener for the specified event.
- `once(event, listener)`: Adds a one-time listener for the event.
- `emit(event, [...args])`: Emits the specified event, optionally with arguments.
- `removeListener(event, listener)`: Removes a specific listener for the event.
- `removeAllListeners([event])`: Removes all listeners for the specified event, or all events if no event is specified.
- `setMaxListeners(n)`: Sets the maximum number of listeners for the event emitter.
- `listenerCount(event)`: Returns the number of listeners for the specified event.
- `prependListener(event, listener)`: Adds a listener to the beginning of the listeners array for the specified event.
- `prependOnceListener(event, listener)`: Adds a one-time listener to the beginning of the listeners array for the specified event.
- `eventNames()`: Returns an array of the event names for which the emitter has registered listeners.

```javascript
const EventEmitter = require('events');
const myEmitter = new EventEmitter();

myEmitter.on('event', () => {
  console.log('An event occurred!');
});

myEmitter.emit('event');
```

## Streams

Streams in Node.js are used to handle reading and writing data efficiently. There are four types of streams: Readable, Writable, Duplex, and Transform.

Example of using a readable stream:

```javascript
const fs = require('fs');

const readableStream = fs.createReadStream('example.txt', 'utf8');

readableStream.on('data', (chunk) => {
  console.log('Received chunk:', chunk);
});

readableStream.on('end', () => {
  console.log('No more data.');
});
```

Example of using a writable stream:

```javascript
const fs = require('fs');

const writableStream = fs.createWriteStream('example.txt', 'utf8');

writableStream.write('Hello, world!\n');
writableStream.write('This is a writable stream example.\n');

writableStream.end(() => {
  console.log('Finished writing.');
});
```

Example of using a duplex stream:

```javascript
const { Duplex } = require('stream');

const duplexStream = new Duplex({
  read(size) {
    this.push('Hello from duplex stream!\n');
    this.push(null);
  },
  write(chunk, encoding, callback) {
    console.log('Received chunk:', chunk.toString());
    callback();
  }
});

duplexStream.on('data', (chunk) => {
  console.log('Read chunk:', chunk.toString());
});

duplexStream.write('Writing to duplex stream.\n');
duplexStream.end();
```

Example of using a transform stream:

```javascript
const { Transform } = require('stream');

const transformStream = new Transform({
  transform(chunk, encoding, callback) {
    this.push(chunk.toString().toUpperCase());
    callback();
  }
});

transformStream.on('data', (chunk) => {
  console.log('Transformed chunk:', chunk.toString());
});

transformStream.write('Hello, world!\n');
transformStream.end();
```

## Buffers

Buffers in Node.js are used to handle binary data. They are similar to arrays of integers but correspond to raw memory allocations outside the V8 heap.

Example of using a buffer:

```javascript
const buffer = Buffer.from('Hello, world!');
console.log('Buffer content:', buffer);
console.log('Buffer as string:', buffer.toString());
```

Example of creating an empty buffer and allocating a buffer of a specific size:

```javascript
const emptyBuffer = Buffer.alloc(10);
console.log('Empty buffer:', emptyBuffer);

const allocatedBuffer = Buffer.allocUnsafe(10);
console.log('Allocated buffer:', allocatedBuffer);
```

Example of concatenating buffers:

```javascript
const buffer1 = Buffer.from('Hello, ');
const buffer2 = Buffer.from('world!');
const concatenatedBuffer = Buffer.concat([buffer1, buffer2]);
console.log('Concatenated buffer:', concatenatedBuffer);
console.log('Concatenated buffer as string:', concatenatedBuffer.toString());
```

Example of slicing a buffer:

```javascript
const buffer = Buffer.from('Hello, world!');
const slicedBuffer = buffer.slice(0, 5);
console.log('Sliced buffer:', slicedBuffer);
console.log('Sliced buffer as string:', slicedBuffer.toString());
```

Example of copying a buffer:

```javascript
const buffer = Buffer.from('Hello, world!');
const copiedBuffer = Buffer.alloc(buffer.length);
buffer.copy(copiedBuffer);
console.log('Copied buffer:', copiedBuffer);
console.log('Copied buffer as string:', copiedBuffer.toString());
```

Example of comparing buffers:

```javascript
const buffer1 = Buffer.from('Hello, world!');
const buffer2 = Buffer.from('Hello, world!');
const buffer3 = Buffer.from('Goodbye, world!');

console.log('Comparing buffer1 and buffer2:', buffer1.compare(buffer2)); // 0 means they are equal
console.log('Comparing buffer1 and buffer3:', buffer1.compare(buffer3)); // < 0 means buffer1 comes before buffer3
```

Example of checking the length of a buffer:

```javascript
const buffer = Buffer.from('Hello, world!');
console.log('Buffer length:', buffer.length);
```

Example of checking if a variable is a buffer:

```javascript
const buffer = Buffer.from('Hello, world!');
console.log('Is buffer:', Buffer.isBuffer(buffer));
console.log('Is buffer (not a buffer):', Buffer.isBuffer('Hello, world!'));
```

Example of converting a buffer to JSON:

```javascript
const buffer = Buffer.from('Hello, world!');
const json = buffer.toJSON();
console.log('Buffer as JSON:', json);
```

Example of filling a buffer with a specific value:

```javascript
const buffer = Buffer.alloc(10);
buffer.fill('A');
console.log('Filled buffer:', buffer);
console.log('Filled buffer as string:', buffer.toString());
```

Example of converting a buffer to a string:

```javascript
const buffer = Buffer.from('Hello, world!');
const str = buffer.toString();
console.log('Buffer as string:', str);
```

Example of creating a buffer from an array of bytes:

```javascript
const buffer = Buffer.from([72, 101, 108, 108, 111, 44, 32, 119, 111, 114, 108, 100, 33]);
console.log('Buffer from array of bytes:', buffer);
console.log('Buffer from array of bytes as string:', buffer.toString());
```

Example of concatenating buffers:

```javascript
const buffer1 = Buffer.from('Hello, ');
const buffer2 = Buffer.from('world!');
const concatenatedBuffer = Buffer.concat([buffer1, buffer2]);
console.log('Concatenated buffer:', concatenatedBuffer);
console.log('Concatenated buffer as string:', concatenatedBuffer.toString());
```

## Environment Variables

Example of accessing environment variables in Node.js:

```javascript
console.log('Node environment:', process.env.NODE_ENV);
console.log('Path environment variable:', process.env.PATH);
```

Example of setting an environment variable in Node.js:

```javascript
process.env.MY_VARIABLE = 'some value';
console.log('My variable:', process.env.MY_VARIABLE);
```

Example of deleting an environment variable in Node.js:

```javascript
delete process.env.MY_VARIABLE;
console.log('My variable after deletion:', process.env.MY_VARIABLE);
```

## Process

Example of accessing process information in Node.js:

```javascript
console.log('Process ID:', process.pid);
console.log('Process title:', process.title);
console.log('Node.js version:', process.version);
console.log('Platform:', process.platform);
```
Example of accessing command-line arguments in Node.js:

```javascript
console.log('Command-line arguments:', process.argv);
```

Example of exiting a Node.js process:

```javascript
console.log('Exiting process with code 0');
process.exit(0);
```

## process.env

Example of listing all environment variables in Node.js:

```javascript
console.log('All environment variables:', process.env);
```

Example of accessing a specific environment variable in Node.js:

```javascript
console.log('Node environment:', process.env.NODE_ENV);
```

## File handling

Example of reading a file in Node.js:

```javascript
const fs = require('fs');
fs.readFile('example.txt', 'utf8', (err, data) => {
  if (err) {
    console.error('Error reading file:', err);
    return;
  }
  console.log('File contents:', data);
});
```

Example of writing to a file in Node.js:

```javascript
const fs = require('fs');
fs.writeFile('example.txt', 'Hello, world!', 'utf8', (err) => {
  if (err) {
    console.error('Error writing file:', err);
    return;
  }
  console.log('File written successfully');
});
```

Example of appending to a file in Node.js:

```javascript
const fs = require('fs');
fs.appendFile('example.txt', '\nAppended content', 'utf8', (err) => {
  if (err) {
    console.error('Error appending to file:', err);
    return;
  }
  console.log('File appended successfully');
});
```

Example of deleting a file in Node.js:

```javascript
const fs = require('fs');
fs.unlink('example.txt', (err) => {
  if (err) {
    console.error('Error deleting file:', err);
    return;
  }
  console.log('File deleted successfully');
});
```

## Async filesystem APIs

Example of reading a file asynchronously in Node.js:

```javascript
const fs = require('fs').promises;

async function readFileAsync() {
  try {
    const data = await fs.readFile('example.txt', 'utf8');
    console.log('File contents:', data);
  } catch (err) {
    console.error('Error reading file:', err);
  }
}

readFileAsync();
```

Example of writing to a file asynchronously in Node.js:

```javascript
const fs = require('fs').promises;

async function writeFileAsync() {
  try {
    await fs.writeFile('example.txt', 'Hello, async world!', 'utf8');
    console.log('File written successfully');
  } catch (err) {
    console.error('Error writing file:', err);
  }
}

writeFileAsync();
```

Example of appending to a file asynchronously in Node.js:

```javascript
const fs = require('fs').promises;

async function appendFileAsync() {
  try {
    await fs.appendFile('example.txt', '\nAppended async content', 'utf8');
    console.log('File appended successfully');
  } catch (err) {
    console.error('Error appending to file:', err);
  }
}

appendFileAsync();
```

Example of deleting a file asynchronously in Node.js:

```javascript
const fs = require('fs').promises;

async function deleteFileAsync() {
  try {
    await fs.unlink('example.txt');
    console.log('File deleted successfully');
  } catch (err) {
    console.error('Error deleting file:', err);
  }
}

deleteFileAsync();
```

# Testing JavaScript

## Why testing?

Testing is crucial in software development because it helps ensure that your code behaves as expected. It allows you to catch bugs early, improve code quality, and maintain confidence when making changes or adding new features. In JavaScript, testing can be done using various frameworks and libraries, such as Jest, Mocha, and Jasmine.

## Unit testing

Unit testing involves testing individual units or components of your code in isolation to ensure they work as expected. In JavaScript, unit tests are commonly written using frameworks like Jest, Mocha, or Jasmine.

Example of a simple unit test using Jest:

```javascript
// sum.js
function sum(a, b) {
  return a + b;
}
module.exports = sum;
```

```javascript
// sum.test.js
const sum = require('./sum');

test('adds 1 + 2 to equal 3', () => {
  expect(sum(1, 2)).toBe(3);
});
```

## Integration testing

Integration testing involves testing how different units or components of your code work together. It helps ensure that the integrated parts of your application function correctly as a whole. In JavaScript, integration tests can also be written using frameworks like Jest, Mocha, or Jasmine.

Example of a simple integration test using Jest:

```javascript
// calculator.js
const sum = require('./sum');

function calculateTotal(a, b, tax) {
  const subtotal = sum(a, b);
  return subtotal + subtotal * tax;
}

module.exports = calculateTotal;
```

```javascript
// calculator.test.js
const calculateTotal = require('./calculator');

test('calculates total with tax', () => {
  expect(calculateTotal(1, 2, 0.1)).toBe(3.3);
});
```

## End-to-End (E2E) testing

End-to-End testing involves testing the entire application flow from start to finish to ensure that all components work together as expected. In JavaScript, E2E tests are commonly written using frameworks like Cypress or Puppeteer.

Example of a simple E2E test using Cypress:

```javascript
// cypress/integration/sample_spec.js
describe('My First Test', () => {
  it('Visits the Kitchen Sink', () => {
    cy.visit('https://example.cypress.io')
    cy.contains('type').click()
    cy.url().should('include', '/commands/actions')
    cy.get('.action-email')
      .type('fake@email.com')
      .should('have.value', 'fake@email.com')
  })
})
```

## Test case

A test case is a set of conditions or variables under which a tester will determine whether a system or one of its components is working correctly. In JavaScript, test cases are typically written using testing frameworks like Jest, Mocha, or Jasmine.

Example of a test case using Jest:

```javascript
// sum.test.js
const sum = require('./sum');

describe('sum function', () => {
  it('should add two numbers correctly', () => {
    expect(sum(1, 2)).toBe(3);
  });

  it('should return 0 when adding 0 and 0', () => {
    expect(sum(0, 0)).toBe(0);
  });
});
```

## Test suite

A test suite is a collection of test cases that are intended to test a specific feature or functionality of your code. In JavaScript, test suites are typically written using testing frameworks like Jest, Mocha, or Jasmine.

Example of a test suite using Jest:

```javascript
// sum.test.js
const sum = require('./sum');

describe('sum function', () => {
  it('should add two numbers correctly', () => {
    expect(sum(1, 2)).toBe(3);
  });

  it('should return 0 when adding 0 and 0', () => {
    expect(sum(0, 0)).toBe(0);
  });
});
```

## Assertions

Assertions are statements that check if a condition is true. In JavaScript testing frameworks like Jest, assertions are used to verify that the code behaves as expected. Common assertion methods include `toBe`, `toEqual`, `toContain`, and `toHaveLength`.

Example of assertions using Jest:

```javascript
// sum.test.js
const sum = require('./sum');

test('adds 1 + 2 to equal 3', () => {
  expect(sum(1, 2)).toBe(3);
});

test('adds 0 + 0 to equal 0', () => {
  expect(sum(0, 0)).toBe(0);
});
```

## Mocking

Mocking is a technique used in testing to simulate the behavior of real objects. In JavaScript, mocking is commonly used to test functions that depend on external services or modules. Jest provides built-in support for mocking.

Example of mocking using Jest:

```javascript
// user.test.js
const fetchUser = require('./fetchUser');

jest.mock('./fetchUser');

test('fetches user data', async () => {
  fetchUser.mockResolvedValue({ id: 1, name: 'John Doe' });
  const user = await fetchUser(1);
  expect(user).toEqual({ id: 1, name: 'John Doe' });
});
```

## Spying

Spying is a technique used in testing to monitor the behavior of functions, such as how many times they were called and with what arguments. Jest provides built-in support for spying using `jest.fn()` and `jest.spyOn()`.

Example of spying using Jest:

```javascript
// calculator.test.js
const calculator = require('./calculator');

test('spy on add method', () => {
  const addSpy = jest.spyOn(calculator, 'add');
  calculator.add(1, 2);
  expect(addSpy).toHaveBeenCalledWith(1, 2);
  addSpy.mockRestore();
});
```

## Stubbing

Stubbing is a technique used in testing to replace a function with a custom implementation that returns predefined values. This is useful for isolating the code under test from external dependencies. In Jest, stubbing can be achieved using `jest.fn()` or `jest.spyOn()`.

Example of stubbing using Jest:

```javascript
// calculator.test.js
const calculator = require('./calculator');

test('stub the add method', () => {
  const addStub = jest.spyOn(calculator, 'add').mockImplementation(() => 42);
  const result = calculator.add(1, 2);
  expect(result).toBe(42);
  addStub.mockRestore();
});
```

## Code coverage

Code coverage is a measure of how much of your code is executed during testing. It helps identify untested parts of your codebase. Jest provides built-in support for generating code coverage reports using the `--coverage` flag.

Example of running tests with code coverage using Jest:

```bash
jest --coverage
```

## Jest

Jest is a popular JavaScript testing framework developed by Facebook. It provides a comprehensive set of features for testing JavaScript code, including assertions, mocking, spying, stubbing, and code coverage. Jest is widely used for testing React applications but can be used with any JavaScript project.

Key features of Jest include:
- Zero configuration: Jest works out of the box with minimal setup.
- Snapshot testing: Capture and compare the rendered output of components.
- Mocking: Easily mock functions, modules, and timers.
- Code coverage: Generate code coverage reports with the `--coverage` flag.
- Parallel test execution: Run tests in parallel to speed up the testing process.

Example of a simple test using Jest:

```javascript
// sum.test.js
const sum = require('./sum');

test('adds 1 + 2 to equal 3', () => {
  expect(sum(1, 2)).toBe(3);
});
```

## Vitest

Vitest is a fast and lightweight JavaScript testing framework inspired by Jest. It is designed to work seamlessly with Vite, a modern frontend build tool. Vitest provides similar features to Jest, including assertions, mocking, spying, stubbing, and code coverage.

Key features of Vitest include:
- Fast test execution: Leverages Vite's fast build system for quick test runs.
- Snapshot testing: Capture and compare the rendered output of components.
- Mocking: Easily mock functions, modules, and timers.
- Code coverage: Generate code coverage reports.
- Parallel test execution: Run tests in parallel to speed up the testing process.

Example of a simple test using Vitest:

```javascript
// sum.test.js
import { describe, it, expect } from 'vitest';
import sum from './sum';

describe('sum', () => {
  it('adds 1 + 2 to equal 3', () => {
    expect(sum(1, 2)).toBe(3);
  });
});
```

## Playwright/Cypress concepts

Playwright and Cypress are popular end-to-end testing frameworks for web applications. They allow you to automate browser interactions and verify that your application behaves as expected from the user's perspective.

Key concepts of Playwright and Cypress include:
- Browser automation: Control browsers programmatically to simulate user interactions.
- Selectors: Locate elements on the page using CSS selectors, XPath, or other strategies.
- Assertions: Verify that the application state matches the expected outcome.
- Test structure: Organize tests using `describe` and `it` blocks (Cypress) or `test` blocks (Playwright).
- Fixtures: Manage test data and application state setup.
- Network interception: Mock or inspect network requests and responses.
- Parallel test execution: Run tests concurrently to speed up the testing process.

Example of a simple test using Playwright:

```javascript
// example.spec.js
const { test, expect } = require('@playwright/test');

test('basic test', async ({ page }) => {
  await page.goto('https://example.com');
  const title = await page.title();
  expect(title).toBe('Example Domain');
});
```

Example of a simple test using Cypress:

```javascript
// example.spec.js
describe('basic test', () => {
  it('visits the example page and checks the title', () => {
    cy.visit('https://example.com');
    cy.title().should('eq', 'Example Domain');
  });
});
```

# Debugging

## Browser DevTools

Browser DevTools are built-in tools available in modern web browsers that help developers inspect and debug web applications. They provide features such as element inspection, console logging, network monitoring, and performance profiling.

Key features of Browser DevTools include:
- Elements panel: Inspect and modify the HTML and CSS of the page.
- Console panel: Log messages, run JavaScript code, and view errors and warnings.
- Network panel: Monitor network requests and responses, including headers and payloads.
- Sources panel: Debug JavaScript code with breakpoints and step-through execution.
- Performance panel: Analyze the performance of your application and identify bottlenecks.
- Application panel: Inspect and manage storage, including cookies, local storage, and session storage.
- Security panel: View security-related information, such as HTTPS status and certificate details.

## Console

The console is a tool within Browser DevTools that allows developers to log messages, run JavaScript code, and view errors and warnings. It is commonly used for debugging and inspecting the behavior of web applications.

Key features of the console include:
- Logging: Use `console.log()`, `console.info()`, `console.warn()`, and `console.error()` to output messages to the console.
- Error reporting: View JavaScript errors and stack traces to identify issues in your code.
- Interactive execution: Run JavaScript code directly in the console to test and debug functionality.
- Filtering: Filter console messages by type (log, error, warning, etc.) to focus on relevant information.
- Grouping: Organize related messages using `console.group()` and `console.groupEnd()`.
- Timing: Measure the time taken for code execution using `console.time()` and `console.timeEnd()`.

## Breakpoints

Breakpoints are markers that you can set in your JavaScript code to pause execution at a specific line. This allows you to inspect the current state of the application, including variable values and the call stack, to help identify and fix issues.

Key features of breakpoints include:
- Line-of-code breakpoints: Pause execution at a specific line in your code.
- Conditional breakpoints: Pause execution only when a specified condition is met.
- DOM breakpoints: Pause execution when a specific DOM element is modified.
- Event listener breakpoints: Pause execution when a specific event is triggered.
- Exception breakpoints: Pause execution when an exception is thrown.

## Conditional breakpoints

Conditional breakpoints are a type of breakpoint that only pause the execution of your code when a specified condition is met. This is useful for debugging scenarios where you only want to stop execution under certain circumstances, such as when a variable reaches a specific value.

Key features of conditional breakpoints include:
- Setting conditions: Specify an expression that must evaluate to `true` for the breakpoint to trigger.
- Dynamic evaluation: The condition is evaluated each time the breakpoint is reached, allowing for flexible debugging.
- Combining with other breakpoints: Use conditional breakpoints alongside line-of-code, DOM, and event listener breakpoints for more precise control over code execution.

## Watch expressions

Watch expressions are used to monitor the values of specific variables or expressions as your code executes. This helps you keep track of how data changes over time and can be particularly useful for debugging complex logic.

Key features of watch expressions include:
- Adding expressions: Specify the variables or expressions you want to watch.
- Real-time updates: The values of watch expressions are updated in real-time as the code executes.
- Integration with breakpoints: Watch expressions can be used in conjunction with breakpoints to inspect values at specific points during execution.

## Call stack inspection

Call stack inspection allows you to examine the sequence of function calls that led to the current point of execution. This is useful for understanding the flow of your program and identifying where errors or unexpected behavior occur.

Key features of call stack inspection include:
- Viewing the call stack: See the list of functions that have been called up to the current point of execution.
- Navigating the stack: Click on stack frames to jump to the corresponding code in the source file.
- Inspecting variables: Examine the values of local variables and function arguments within each stack frame.

## Network tab

The Network tab in browser developer tools allows you to monitor and inspect network requests made by your application. This is useful for debugging issues related to data fetching, API calls, and resource loading.

Key features of the Network tab include:
- Viewing network requests: See a list of all network requests made by your application, including their URLs, methods, and status codes.
- Inspecting request and response details: Examine the headers, payload, and response data for each network request.
- Timing analysis: Analyze the timing of network requests to identify performance bottlenecks.
- Filtering and searching: Filter network requests by type (XHR, Fetch, JS, CSS, etc.) and search for specific requests to focus on relevant information.

## Sources tab

The Sources tab in browser developer tools allows you to view and debug the source code of your application. This is useful for setting breakpoints, stepping through code, and inspecting the execution context.

Key features of the Sources tab include:
- Viewing source files: Browse and open the source files of your application.
- Setting breakpoints: Set breakpoints to pause code execution at specific lines.
- Stepping through code: Step over, into, or out of functions to control the flow of execution.
- Inspecting the execution context: Examine local and global variables, as well as the call stack, while debugging.

## Performance tab

The Performance tab in browser developer tools allows you to analyze the runtime performance of your application. This is useful for identifying performance bottlenecks and optimizing the efficiency of your code.

Key features of the Performance tab include:
- Recording performance profiles: Capture a detailed timeline of your application's execution, including scripting, rendering, and painting activities.
- Analyzing frame rates: Examine the frame rate to identify performance issues related to rendering and animations.
- Inspecting call stacks: View the call stacks associated with performance events to pinpoint the source of slow operations.
- Identifying long tasks: Detect tasks that block the main thread and impact the responsiveness of your application.

## Memory tab

The Memory tab in browser developer tools allows you to analyze the memory usage of your application. This is useful for identifying memory leaks and optimizing memory consumption.

Key features of the Memory tab include:
- Heap snapshots: Capture snapshots of the JavaScript heap to analyze memory allocation and identify memory leaks.
- Allocation instrumentation: Track memory allocations over time to understand how your application uses memory.
- Garbage collection analysis: Examine the behavior of the garbage collector and its impact on memory usage.
- Memory timeline: Visualize memory usage over time to detect patterns and potential issues.

## Debugging async code

The Debugging async code section in browser developer tools helps you understand and troubleshoot asynchronous operations in your application, such as promises, async/await, and callbacks.

Key features of debugging async code include:
- Async call stacks: View the call stack for asynchronous operations to trace the origin of async calls.
- Breakpoints in async code: Set breakpoints within async functions to pause execution and inspect the state.
- Promise inspection: Examine the state and value of promises to understand their behavior.
- Event loop analysis: Analyze the event loop to identify potential issues with asynchronous code execution.

## Reading stack traces

Reading stack traces is an essential skill for debugging JavaScript errors. Stack traces provide information about the sequence of function calls that led to an error, helping you pinpoint the source of the problem.

Key aspects of reading stack traces include:
- Understanding the call stack: Each line in a stack trace represents a function call, with the most recent call at the top.
- Identifying the error location: Look for the file name and line number where the error occurred to quickly locate the problematic code.
- Tracing the sequence of calls: Follow the stack trace from top to bottom to understand the sequence of function calls that led to the error.
- Recognizing common patterns: Familiarize yourself with common stack trace patterns for different types of errors, such as TypeError, ReferenceError, and SyntaxError.

## Common JavaScript errors

Understanding common JavaScript errors can help you quickly identify and fix issues in your code.

Some common JavaScript errors include:
- SyntaxError: Occurs when there is a mistake in the syntax of your code.
- ReferenceError: Happens when you try to access a variable that is not defined.
- TypeError: Raised when a value is not of the expected type.
- RangeError: Triggered when a value is outside the allowed range.
- EvalError: Related to the use of the `eval()` function, though it is rarely encountered in modern JavaScript.

# Advanced JavaScript Topics

## Symbols

Symbols are a unique and immutable primitive data type introduced in ES6. They are often used to create unique property keys for objects, ensuring that property names do not conflict with other keys.

Key characteristics of symbols include:
- Uniqueness: Each symbol is unique, even if they have the same description.
- Immutability: Symbols cannot be changed once created.
- Use as object keys: Symbols can be used as property keys in objects, providing a way to create hidden or non-colliding properties.

Example:
```javascript
const mySymbol = Symbol('description');
const obj = {
  [mySymbol]: 'value'
};
console.log(obj[mySymbol]); // Output: 'value'
```

## Proxy

Proxies are a powerful feature in JavaScript that allow you to create objects with custom behavior for fundamental operations, such as property access, assignment, enumeration, and function invocation.

Key aspects of proxies include:
- Target object: The original object that you want to wrap with a proxy.
- Handler object: An object that defines traps, which are functions that intercept and redefine operations performed on the target object.

Example:
```javascript
const target = {
  message: 'Hello, world!'
};

const handler = {
  get: function(obj, prop) {
    if (prop === 'message') {
      return obj[prop].toUpperCase();
    }
    return obj[prop];
  }
};

const proxy = new Proxy(target, handler);
console.log(proxy.message); // Output: 'HELLO, WORLD!'
```

## Reflect

The `Reflect` object provides methods for interceptable JavaScript operations. It is not a function object, so it cannot be called as a function or constructed as a constructor. `Reflect` is often used in conjunction with proxies to forward operations to the target object.

Key aspects of `Reflect` include:
- Methods corresponding to proxy traps: `Reflect` methods have the same names and behavior as the traps used in proxy handlers, such as `get`, `set`, `has`, `deleteProperty`, and `apply`.
- Return values: `Reflect` methods return a boolean indicating the success of the operation, making it easier to handle errors and control flow.

Example:
```javascript
const obj = {
  message: 'Hello, world!'
};

const handler = {
  get: function(target, prop, receiver) {
    return Reflect.get(target, prop, receiver).toUpperCase();
  }
};

const proxy = new Proxy(obj, handler);
console.log(proxy.message); // Output: 'HELLO, WORLD!'
```

## WeakRef

The `WeakRef` object provides a way to hold a weak reference to another object, allowing the referenced object to be garbage-collected if there are no other strong references to it. This can be useful for caching or managing memory-sensitive resources.

Key aspects of `WeakRef` include:
- Weak reference: The reference held by a `WeakRef` does not prevent the object from being garbage-collected.
- Dereferencing: You can access the referenced object using the `deref()` method, which returns the object if it is still alive or `undefined` if it has been collected.

Example:
```javascript
let obj = { message: 'Hello, world!' };
const weakRef = new WeakRef(obj);

console.log(weakRef.deref().message); // Output: 'Hello, world!'

obj = null; // The object is now eligible for garbage collection
console.log(weakRef.deref()); // Output: undefined (if the object has been collected)
```

## FinalizationRegistry

The `FinalizationRegistry` object allows you to register a callback to be called when an object is garbage-collected. This can be useful for cleaning up resources associated with objects that are no longer needed.

Key aspects of `FinalizationRegistry` include:
- Registration: You register an object along with a cleanup callback using the `register` method.
- Cleanup: The callback is invoked after the object has been garbage-collected, allowing you to perform necessary cleanup tasks.

Example:
```javascript
const registry = new FinalizationRegistry((heldValue) => {
  console.log(`Object with value "${heldValue}" has been garbage-collected`);
});

let obj = { message: 'Hello, world!' };
registry.register(obj, 'some value');

obj = null; // The object is now eligible for garbage collection
// The cleanup callback will be called at some point after garbage collection
```

## BigInt

The `BigInt` type provides a way to represent whole numbers larger than `2^53 - 1`, which is the largest number JavaScript can reliably represent with the `Number` type. `BigInt` allows for safe manipulation of large integers without losing precision.

Key aspects of `BigInt` include:
- Creation: You can create a `BigInt` by appending `n` to the end of an integer literal or by using the `BigInt` constructor.
- Operations: `BigInt` supports standard arithmetic operations like addition, subtraction, multiplication, and division, but it cannot be mixed with `Number` types without explicit conversion.

Example:
```javascript
const bigInt1 = 1234567890123456789012345678901234567890n;
const bigInt2 = BigInt('9876543210987654321098765432109876543210');

console.log(bigInt1 + bigInt2); // Output: 11111111101111111110111111111011111111100n
console.log(bigInt1 * 2n); // Output: 2469135780246913578024691357802469135780n
```

## Tagged template literals

Tagged template literals allow you to parse template literals with a function. The first argument of the tag function contains an array of string literals, and the subsequent arguments are the values of the placeholders.

Example:
```javascript
function tag(strings, ...values) {
  console.log(strings);
  console.log(values);
  return 'Tagged template result';
}

const name = 'Alice';
const age = 30;
const result = tag`My name is ${name} and I am ${age} years old.`;
console.log(result);
```

## Property descriptors

Property descriptors provide detailed information about the properties of an object, such as whether they are writable, enumerable, or configurable. You can use `Object.getOwnPropertyDescriptor` to retrieve a property's descriptor and `Object.defineProperty` to define or modify a property with specific attributes.

Example:
```javascript
const obj = { name: 'Alice' };

// Get the property descriptor
const descriptor = Object.getOwnPropertyDescriptor(obj, 'name');
console.log(descriptor);

// Define a new property with specific attributes
Object.defineProperty(obj, 'age', {
  value: 30,
  writable: false,
  enumerable: true,
  configurable: true
});

console.log(obj);
```

## Getters/setters

Getters and setters allow you to define methods that are executed when a property is accessed or modified. This provides a way to control access to an object's properties and add custom behavior.

Example:
```javascript
const obj = {
  firstName: 'Alice',
  lastName: 'Smith',
  get fullName() {
    return `${this.firstName} ${this.lastName}`;
  },
  set fullName(name) {
    const [first, last] = name.split(' ');
    this.firstName = first;
    this.lastName = last;
  }
};

console.log(obj.fullName); // Output: Alice Smith
obj.fullName = 'Bob Johnson';
console.log(obj.firstName); // Output: Bob
console.log(obj.lastName); // Output: Johnson
```

## Enumerability

Enumerability determines whether a property shows up during property enumeration, such as in a `for...in` loop or `Object.keys` method. By default, properties defined directly on an object are enumerable.

Example:
```javascript
const obj = { name: 'Alice' };

for (const key in obj) {
  console.log(key); // Output: name
}

console.log(Object.keys(obj)); // Output: ['name']

Object.defineProperty(obj, 'age', {
  value: 30,
  enumerable: false
});

for (const key in obj) {
  console.log(key); // Output: name (age is not enumerated)
}

console.log(Object.keys(obj)); // Output: ['name']
```

## Configurable properties

Configurable properties determine whether a property can be deleted or whether its attributes (other than `writable`) can be modified. By default, properties defined directly on an object are configurable.

Example:
```javascript
const obj = { name: 'Alice' };

Object.defineProperty(obj, 'name', {
  configurable: false
});

// Attempting to delete the property will fail
delete obj.name;
console.log(obj.name); // Output: Alice

// Attempting to redefine the property will throw an error
try {
  Object.defineProperty(obj, 'name', {
    enumerable: false
  });
} catch (e) {
  console.log(e); // Output: TypeError: Cannot redefine property: name
}
```

## Writable properties

Writable properties determine whether the value of a property can be changed. By default, properties defined directly on an object are writable.

Example:
```javascript
const obj = { name: 'Alice' };

Object.defineProperty(obj, 'name', {
  writable: false
});

// Attempting to modify the property will fail silently in non-strict mode
obj.name = 'Bob';
console.log(obj.name); // Output: Alice

// In strict mode, attempting to modify the property will throw an error
try {
  'use strict';
  obj.name = 'Bob';
} catch (e) {
  console.log(e); // Output: TypeError: Cannot assign to read only property 'name' of object '#<Object>'
}
```

## Object.defineProperty()

The `Object.defineProperty()` method allows you to define or modify a property on an object with specific attributes such as `enumerable`, `configurable`, and `writable`.

Example:
```javascript
const obj = {};

Object.defineProperty(obj, 'name', {
  value: 'Alice',
  writable: true,
  enumerable: true,
  configurable: true
});

console.log(obj.name); // Output: Alice
```

## Object.getOwnPropertyDescriptor()

The `Object.getOwnPropertyDescriptor()` method returns the descriptor for a property on an object, which includes attributes like `value`, `writable`, `enumerable`, and `configurable`.

Example:
```javascript
const obj = { name: 'Alice' };

const descriptor = Object.getOwnPropertyDescriptor(obj, 'name');
console.log(descriptor);
// Output: { value: 'Alice', writable: true, enumerable: true, configurable: true }
```

## Object.getOwnPropertyDescriptors()

The `Object.getOwnPropertyDescriptors()` method returns all property descriptors for an object, including attributes like `value`, `writable`, `enumerable`, and `configurable`.

Example:
```javascript
const obj = { name: 'Alice', age: 25 };

const descriptors = Object.getOwnPropertyDescriptors(obj);
console.log(descriptors);
// Output:
// {
//   name: { value: 'Alice', writable: true, enumerable: true, configurable: true },
//   age: { value: 25, writable: true, enumerable: true, configurable: true }
// }
```

## Metaprogramming

Metaprogramming in JavaScript refers to the ability to write code that can manipulate other code or itself at runtime. This includes defining, modifying, or intercepting the behavior of objects and their properties.

Example using `Proxy`:
```javascript
const target = { name: 'Alice' };

const handler = {
  get: function(obj, prop) {
    console.log(`Accessing property "${prop}"`);
    return obj[prop];
  },
  set: function(obj, prop, value) {
    console.log(`Setting property "${prop}" to "${value}"`);
    obj[prop] = value;
    return true;
  }
};

const proxy = new Proxy(target, handler);

console.log(proxy.name); // Accessing property "name" \n Alice
proxy.name = 'Bob';      // Setting property "name" to "Bob"
console.log(proxy.name); // Accessing property "name" \n Bob
```

## Tail-call concepts

Tail-call optimization is a feature in JavaScript where the last function call in a function is optimized to avoid adding a new stack frame. This can help prevent stack overflow errors in recursive functions.

Example:
```javascript
function factorial(n, acc = 1) {
  if (n <= 1) return acc;
  return factorial(n - 1, n * acc); // Tail call
}

console.log(factorial(5)); // Output: 120
```

## Structured cloning

Structured cloning in JavaScript refers to the process of creating a deep copy of an object, including its nested structures, without retaining references to the original object. This is useful for safely copying complex data structures.

Example using `structuredClone`:
```javascript
const original = { name: 'Alice', address: { city: 'Wonderland' } };
const copy = structuredClone(original);

console.log(copy);
// Output: { name: 'Alice', address: { city: 'Wonderland' } }

copy.address.city = 'New Wonderland';
console.log(original.address.city); // Output: 'Wonderland' (original remains unchanged)
```

## Transferable objects

Transferable objects in JavaScript are objects that can be transferred from one context to another, such as between the main thread and a Web Worker, without copying the underlying data. This allows for efficient data transfer.

Example using `postMessage` with a `ArrayBuffer`:
```javascript
const worker = new Worker('worker.js');
const buffer = new ArrayBuffer(1024);

worker.postMessage(buffer, [buffer]); // Transfer the buffer to the worker
console.log(buffer.byteLength); // Output: 0 (buffer has been transferred)
```

# Real-World JavaScript Skills

## Form validation

Form validation in JavaScript involves checking user input in forms to ensure it meets certain criteria before being submitted. This helps improve data quality and user experience.

Example:
```javascript
const form = document.querySelector('form');
const emailInput = document.querySelector('#email');

form.addEventListener('submit', function(event) {
  if (!emailInput.value.includes('@')) {
    alert('Please enter a valid email address.');
    event.preventDefault(); // Prevent form submission
  }
});
```

## Search functionality

Search functionality in JavaScript involves allowing users to search for specific content within a webpage or application. This can be implemented using input fields and event listeners to filter and display relevant results.

Example:
```javascript
const searchInput = document.querySelector('#search');
const items = document.querySelectorAll('.item');

searchInput.addEventListener('input', function() {
  const query = searchInput.value.toLowerCase();
  items.forEach(item => {
    const text = item.textContent.toLowerCase();
    item.style.display = text.includes(query) ? '' : 'none';
  });
});
```

## Pagination

Pagination in JavaScript involves dividing content into discrete pages and providing navigation controls to move between them. This improves user experience by preventing long scrolling and making content more manageable.

Example:
```javascript
const items = document.querySelectorAll('.item');
const itemsPerPage = 5;
let currentPage = 1;

function renderPage(page) {
  const start = (page - 1) * itemsPerPage;
  const end = start + itemsPerPage;
  items.forEach((item, index) => {
    item.style.display = index >= start && index < end ? '' : 'none';
  });
}

document.querySelector('#next').addEventListener('click', () => {
  if (currentPage * itemsPerPage < items.length) {
    currentPage++;
    renderPage(currentPage);
  }
});

document.querySelector('#prev').addEventListener('click', () => {
  if (currentPage > 1) {
    currentPage--;
    renderPage(currentPage);
  }
});

renderPage(currentPage);
```

## Infinite scrolling

Infinite scrolling in JavaScript involves automatically loading more content as the user scrolls down the page. This provides a seamless browsing experience without the need for pagination.

Example:
```javascript
const container = document.querySelector('#container');
let page = 1;

function loadMoreContent() {
  // Simulate fetching data from an API
  for (let i = 0; i < 5; i++) {
    const item = document.createElement('div');
    item.className = 'item';
    item.textContent = `Item ${page * 5 + i + 1}`;
    container.appendChild(item);
  }
  page++;
}

window.addEventListener('scroll', () => {
  if (window.innerHeight + window.scrollY >= document.body.offsetHeight) {
    loadMoreContent();
  }
});

loadMoreContent();
```

## Autocomplete

Autocomplete in JavaScript involves providing suggestions to users as they type into an input field. This enhances user experience by helping users quickly find and select options.

Example:
```javascript
const searchInput = document.querySelector('#search');
const suggestions = ['Apple', 'Banana', 'Cherry', 'Date', 'Elderberry'];
const suggestionBox = document.querySelector('#suggestions');

searchInput.addEventListener('input', function() {
  const query = searchInput.value.toLowerCase();
  suggestionBox.innerHTML = '';
  suggestions.forEach(item => {
    if (item.toLowerCase().includes(query)) {
      const div = document.createElement('div');
      div.textContent = item;
      suggestionBox.appendChild(div);
    }
  });
});
```

## Image preview

Image preview in JavaScript involves displaying a preview of an image before it is uploaded. This improves user experience by allowing users to see the selected image.

Example:
```javascript
const fileInput = document.querySelector('#fileInput');
const preview = document.querySelector('#preview');

fileInput.addEventListener('change', function() {
  const file = fileInput.files[0];
  if (file) {
    const reader = new FileReader();
    reader.onload = function(e) {
      preview.src = e.target.result;
    }
    reader.readAsDataURL(file);
  }
});
```

## File upload

File upload in JavaScript involves allowing users to select and upload files to a server. This is commonly used in forms and content management systems.

Example:
```javascript
const uploadInput = document.querySelector('#uploadInput');
const uploadButton = document.querySelector('#uploadButton');

uploadButton.addEventListener('click', function() {
  const file = uploadInput.files[0];
  if (file) {
    const formData = new FormData();
    formData.append('file', file);

    fetch('/upload', {
      method: 'POST',
      body: formData
    })
    .then(response => response.json())
    .then(data => {
      console.log('File uploaded successfully:', data);
    })
    .catch(error => {
      console.error('Error uploading file:', error);
    });
  }
});
```

## Drag and drop

Drag and drop in JavaScript involves allowing users to drag elements and drop them into a designated area. This is commonly used for file uploads and interactive interfaces.

Example:
```javascript
const dropArea = document.querySelector('#dropArea');

dropArea.addEventListener('dragover', function(e) {
  e.preventDefault();
  dropArea.classList.add('highlight');
});

dropArea.addEventListener('dragleave', function() {
  dropArea.classList.remove('highlight');
});

dropArea.addEventListener('drop', function(e) {
  e.preventDefault();
  dropArea.classList.remove('highlight');
  const files = e.dataTransfer.files;
  console.log('Files dropped:', files);
});
```

## Modal systems

Modal systems in JavaScript involve creating and managing modal dialogs, which are pop-up windows that require user interaction before returning to the main content. This is commonly used for alerts, confirmations, and forms.

Example:
```javascript
const openModalButton = document.querySelector('#openModal');
const closeModalButton = document.querySelector('#closeModal');
const modal = document.querySelector('#modal');

openModalButton.addEventListener('click', function() {
  modal.style.display = 'block';
});

closeModalButton.addEventListener('click', function() {
  modal.style.display = 'none';
});

window.addEventListener('click', function(e) {
  if (e.target === modal) {
    modal.style.display = 'none';
  }
});
```

## Tabs

Tabs in JavaScript involve creating a tabbed interface where users can switch between different content panels by clicking on tab headers. This is commonly used for organizing content in a compact and user-friendly manner.

Example:
```javascript
const tabButtons = document.querySelectorAll('.tab-button');
const tabContents = document.querySelectorAll('.tab-content');

tabButtons.forEach((button, index) => {
  button.addEventListener('click', function() {
    tabContents.forEach(content => content.style.display = 'none');
    tabContents[index].style.display = 'block';
  });
});
```

## Accordions

Accordions in JavaScript involve creating collapsible sections of content that expand or collapse when their headers are clicked. This is commonly used for FAQs and content organization.

Example:
```javascript
const accordionHeaders = document.querySelectorAll('.accordion-header');

accordionHeaders.forEach(header => {
  header.addEventListener('click', function() {
    const content = header.nextElementSibling;
    content.style.display = content.style.display === 'block' ? 'none' : 'block';
  });
});
```

## Dropdowns

Dropdowns in JavaScript involve creating a menu that expands to show a list of options when clicked. This is commonly used for navigation menus and selection lists.

Example:
```javascript
const dropdownButton = document.querySelector('.dropdown-button');
const dropdownMenu = document.querySelector('.dropdown-menu');

dropdownButton.addEventListener('click', function() {
  dropdownMenu.style.display = dropdownMenu.style.display === 'block' ? 'none' : 'block';
});

window.addEventListener('click', function(e) {
  if (!dropdownButton.contains(e.target)) {
    dropdownMenu.style.display = 'none';
  }
});
```

## Toast notification

Toast notifications in JavaScript involve creating small, temporary messages that appear on the screen to inform users of certain events or actions. They usually disappear automatically after a short period.

Example:
```javascript
const toastButton = document.querySelector('.toast-button');
const toast = document.querySelector('.toast');

toastButton.addEventListener('click', function() {
  toast.style.display = 'block';
  setTimeout(function() {
    toast.style.display = 'none';
  }, 3000); // Toast disappears after 3 seconds
});
```

## Debounced search

Debounced search in JavaScript involves delaying the execution of a search function until the user has stopped typing for a certain period. This helps reduce the number of search requests and improves performance.

Example:
```javascript
const searchInput = document.querySelector('.search-input');
let debounceTimeout;

searchInput.addEventListener('input', function() {
  clearTimeout(debounceTimeout);
  debounceTimeout = setTimeout(function() {
    console.log('Searching for:', searchInput.value);
    // Perform search operation here
  }, 300); // Delay of 300 milliseconds
});
```

## Throttled scrolling

Throttled scrolling in JavaScript involves limiting the frequency at which a scroll event handler is executed. This helps improve performance by reducing the number of times the handler is called during rapid scrolling.

Example:
```javascript
let lastScrollTime = 0;
const throttleDelay = 200; // Delay of 200 milliseconds

window.addEventListener('scroll', function() {
  const now = Date.now();
  if (now - lastScrollTime >= throttleDelay) {
    console.log('Scroll event at:', window.scrollY);
    lastScrollTime = now;
  }
});
```

## API integration

API integration in JavaScript involves making requests to external APIs to fetch or send data. This is commonly done using the `fetch` API or libraries like Axios.

Example:
```javascript
const apiUrl = 'https://api.example.com/data';

fetch(apiUrl)
  .then(response => response.json())
  .then(data => {
    console.log('Fetched data:', data);
    // Process the fetched data here
  })
  .catch(error => {
    console.error('Error fetching data:', error);
  });
```

## Authentication flow

Authentication flow in JavaScript involves managing user login and logout processes, typically using tokens or session management to maintain user authentication state.

Example:
```javascript
const loginButton = document.querySelector('.login-button');
const logoutButton = document.querySelector('.logout-button');
const status = document.querySelector('.status');

loginButton.addEventListener('click', function() {
  // Simulate login process
  localStorage.setItem('authToken', 'your-auth-token');
  status.textContent = 'Logged in';
});

logoutButton.addEventListener('click', function() {
  // Simulate logout process
  localStorage.removeItem('authToken');
  status.textContent = 'Logged out';
});
```

## Protected routes

Protected routes in JavaScript involve restricting access to certain parts of an application based on the user's authentication status. This is commonly implemented by checking for a valid authentication token before allowing access.

Example:
```javascript
const protectedContent = document.querySelector('.protected-content');

function checkAccess() {
  const authToken = localStorage.getItem('authToken');
  if (authToken) {
    protectedContent.style.display = 'block';
  } else {
    protectedContent.style.display = 'none';
  }
}

// Check access on page load
checkAccess();
```

## Error states

Error states in JavaScript involve handling situations where something goes wrong, such as network errors, invalid user input, or failed API requests. Proper error handling ensures a better user experience and helps in debugging issues.

Example:
```javascript
const errorMessage = document.querySelector('.error-message');

function showError(message) {
  errorMessage.textContent = message;
  errorMessage.style.display = 'block';
}

function hideError() {
  errorMessage.textContent = '';
  errorMessage.style.display = 'none';
}

// Simulate an error
try {
  throw new Error('Something went wrong!');
} catch (error) {
  showError(error.message);
}
```

## Loading states

Loading states in JavaScript involve providing feedback to the user while an operation is in progress, such as fetching data from an API or performing a time-consuming task. This helps improve the user experience by indicating that the application is working.

Example:
```javascript
const loadingIndicator = document.querySelector('.loading-indicator');

function showLoading() {
  loadingIndicator.style.display = 'block';
}

function hideLoading() {
  loadingIndicator.style.display = 'none';
}

// Simulate a loading process
showLoading();
setTimeout(() => {
  hideLoading();
}, 2000);
```

## Optimistic UI

Optimistic UI in JavaScript involves updating the user interface immediately in response to a user's action, assuming that the operation will succeed. If the operation fails, the UI is then reverted to its previous state. This approach provides a more responsive and fluid user experience.

Example:
```javascript
const likeButton = document.querySelector('.like-button');
const likeCount = document.querySelector('.like-count');

function likePost() {
  // Optimistically update the UI
  likeCount.textContent = parseInt(likeCount.textContent) + 1;

  // Simulate an API request
  setTimeout(() => {
    const success = Math.random() > 0.2; // 80% chance of success
    if (!success) {
      // Revert the UI if the request fails
      likeCount.textContent = parseInt(likeCount.textContent) - 1;
      alert('Failed to like the post. Please try again.');
    }
  }, 1000);
}

likeButton.addEventListener('click', likePost);
```

## Caching

Caching in JavaScript involves storing data locally to improve performance and reduce the need for repeated network requests. This can be done using various techniques such as in-memory caching, localStorage, or IndexedDB.

Example:
```javascript
const cache = {};

function fetchData(key) {
  if (cache[key]) {
    return Promise.resolve(cache[key]);
  }

  return fetch(`https://api.example.com/data/${key}`)
    .then(response => response.json())
    .then(data => {
      cache[key] = data;
      return data;
    });
}
```

## Offline handling

Offline handling in JavaScript involves detecting when the user is offline and providing appropriate feedback or functionality. This can help maintain a good user experience even when network connectivity is lost.

Example:
```javascript
function updateOnlineStatus() {
  const statusIndicator = document.querySelector('.status-indicator');
  if (navigator.onLine) {
    statusIndicator.textContent = 'Online';
    statusIndicator.style.color = 'green';
  } else {
    statusIndicator.textContent = 'Offline';
    statusIndicator.style.color = 'red';
  }
}

window.addEventListener('online', updateOnlineStatus);
window.addEventListener('offline', updateOnlineStatus);

// Initial status
updateOnlineStatus();
```
