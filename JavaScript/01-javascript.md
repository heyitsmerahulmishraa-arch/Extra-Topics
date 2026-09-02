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



