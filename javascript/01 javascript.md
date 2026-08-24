# What is JavaScript?
JavaScript is a programming language that is commonly used to create interactive effects within web browsers. It is a versatile language that can be used for both client-side and server-side development. JavaScript allows developers to implement complex features on web pages, such as dynamic content updates, form validation, animations, and more.

# JavaScript runtime environments
JavaScript can run in various runtime environments, the most common being web browsers and Node.js.

## Web browsers
Web browsers have built-in JavaScript engines that allow them to execute JavaScript code. Popular browsers like Google Chrome, Mozilla Firefox, Microsoft Edge, and Safari all have their own JavaScript engines (e.g., V8 for Chrome, SpiderMonkey for Firefox). When a user visits a web page, the browser downloads the HTML, CSS, and JavaScript files and executes the JavaScript code to provide interactivity and dynamic content.

## Node.js
Node.js is a runtime environment that allows developers to run JavaScript code on the server side. It is built on the V8 JavaScript engine and provides an event-driven, non-blocking I/O model, making it suitable for building scalable and high-performance applications. With Node.js, developers can use JavaScript to create server-side applications, APIs, and even command-line tools.

# JavaScript engines
JavaScript engines are programs that execute JavaScript code. Each web browser has its own JavaScript engine, and Node.js uses the V8 engine. These engines parse the JavaScript code, compile it to machine code, and execute it, enabling the dynamic behavior of web pages and server-side applications.

# ECMAScript vs JavaScript
ECMAScript is the standardized specification that defines the core features and syntax of the JavaScript language. JavaScript is an implementation of the ECMAScript standard, along with additional features and APIs provided by web browsers and other environments. The terms "JavaScript" and "ECMAScript" are often used interchangeably, but ECMAScript refers specifically to the language specification, while JavaScript refers to the actual programming language used in practice.

|ECMAScript | JavaScript |
|------------|------------|
| A standardized specification for the JavaScript language | An implementation of the ECMAScript standard, along with additional features and APIs |
| Defines the core features and syntax of the language | Provides a programming language that can be used in web browsers and other environments |
| Maintained by the ECMA International organization | Widely used in web development and supported by various runtime environments |
| New versions of ECMAScript are released periodically, introducing new features and improvements | JavaScript implementations may vary across different browsers and environments, but they generally adhere to the ECMAScript standard |
| Examples of ECMAScript versions include ES5, ES6 (also known as ECMAScript 2015), and later versions | JavaScript is the language that developers use to write code for web applications, server-side applications, and more |
| ECMAScript serves as the foundation for JavaScript, providing a standardized set of rules and guidelines for the language | JavaScript is the practical implementation of ECMAScript, allowing developers to create interactive and dynamic web experiences |

# Adding JavaScript to HTML
JavaScript can be added to HTML documents in several ways:
1. **Inline JavaScript**: JavaScript code can be added directly within the HTML elements using the `onclick`, `onchange`, and other event attributes.
```js
<button onclick="alert('Hello, world!')">Click me</button>
```

2. **Internal JavaScript**: JavaScript code can be added within a `<script>` tag inside the HTML document, typically within the `<head>` or `<body>` sections.
```js
<script>
  function greet() {
    alert('Hello, world!');
  }
</script>
```

3. **External JavaScript**: JavaScript code can be placed in a separate `.js` file and linked to the HTML document using the `<script src="path/to/file.js"></script>` tag. This approach promotes code reusability and separation of concerns.
```js
<script src="path/to/file.js"></script>
```

## `<script>` tag
The `<script>` tag is used to include JavaScript code in an HTML document. It can be placed in the `<head>` or `<body>` sections of the HTML. The `src` attribute can be used to link to an external JavaScript file, while inline JavaScript can be written directly within the `<script>` tag.
```html
<script>
  // Inline JavaScript code can be written here
</script>
```

## `defer` and `async` attributes
The `defer` and `async` attributes can be added to the `<script>` tag to control the loading and execution of external JavaScript files.

- `defer`: The script is downloaded in parallel with the HTML parsing but executed only after the HTML parsing is complete. Scripts with the `defer` attribute are executed in the order they appear in the document.
```html
<script src="path/to/file.js" defer></script>
```

- `async`: The script is downloaded in parallel with the HTML parsing and executed as soon as it is available, potentially before the HTML parsing is complete. Scripts with the `async` attribute are not guaranteed to be executed in order.
```html
<script src="path/to/file.js" async></script>
```

## use strict
The `"use strict"` directive is a way to enable strict mode in JavaScript, which helps catch common coding mistakes and "unsafe" actions. When strict mode is enabled, certain behaviors that are normally allowed in JavaScript will throw errors, making it easier to write secure and maintainable code.
To enable strict mode, you can add the `"use strict"` directive at the beginning of a JavaScript file or function:
```js
"use strict";
// Your JavaScript code here
console.log("Strict mode is enabled.");
```

# Variables and Data Types
In JavaScript, variables are used to store data values. You can declare variables using the `var`, `let`, or `const` keywords. JavaScript has several data types, including:

- **var**: Used to declare variables with function scope. It is function-scoped and can be re-declared and updated.
```js
var name = "John";
```

- **let**: Used to declare block-scoped variables. It can be updated but not re-declared within the same scope.
```js
let age = 30;
```

- **const**: Used to declare block-scoped variables that cannot be updated or re-declared. The value assigned to a `const` variable must be initialized at the time of declaration.
```js
const pi = 3.14;
```

## Primitives
JavaScript has several primitive data types, including:

- **String**: Represents a sequence of characters. Strings are enclosed in single quotes, double quotes, or backticks.
```js
let message = "Hello, world!";
```

- **Number**: Represents numeric values, including integers and floating-point numbers.
```js
let age = 25;
```

- **Boolean**: Represents a logical value that can be either `true` or `false`.
```js
let isActive = true;
```

- **Undefined**: Represents a variable that has been declared but has not been assigned a value.
```js
let x;
console.log(x); // Output: undefined
```

- **Null**: Represents the intentional absence of any object value. It is often used to indicate that a variable should have no value.
```js
let y = null;
```

- **Symbol**: Represents a unique and immutable value that can be used as an identifier for object properties.
```js
let sym = Symbol("unique");
```

- **BigInt**: Represents integers with arbitrary precision, allowing for the representation of very large numbers.
```js
let bigIntValue = 1234567890123456789012345678901234567890n;
```

## Non-primitives
Non-primitive data types in JavaScript include:

- **Object**: Represents a collection of key-value pairs. Objects can store various types of data and can be created using object literals or constructors.
```js
let person = {
  name: "Alice",
  age: 28,
  isStudent: false
};
```

- **Array**: Represents an ordered collection of values. Arrays can hold multiple values of different data types and can be created using array literals or constructors.
```js
let numbers = [1, 2, 3, 4, 5];
```

- **Function**: Represents a reusable block of code that can be executed when called. Functions can be defined using function declarations or function expressions.
```js
function greet(name) {
  return "Hello, " + name + "!";
}
```

## what is Reference types and Value Types?
In JavaScript, data types can be categorized into two main categories: **value types** and **reference types**. Understanding the difference between these two is crucial for managing data and memory in your applications.
### Value Types
Value types are data types that store their values directly in memory. When you assign a value type to a variable, a copy of the value is created. Primitive data types such as `string`, `number`, `boolean`, `undefined`, `null`, `symbol`, and `bigint` are value types.
```js
let a = 10; // a holds the value 10
let b = a; // b is assigned a copy of the value of a
a = 20; // Changing a does not affect b
console.log(a); // Output: 20
console.log(b); // Output: 10
```

### Reference Types
Reference types are data types that store a reference (or memory address) to the actual value in memory. When you assign a reference type to a variable, you are assigning a reference to the same object in memory. Objects, arrays, and functions are reference types.
```js
let obj1 = { name: "Alice" }; // obj1 holds a reference to the object
let obj2 = obj1; // obj2 is assigned a reference to the same object as obj1
obj1.name = "Bob"; // Changing the property of the object through obj1
console.log(obj1.name); // Output: Bob
console.log(obj2.name); // Output: Bob (obj2 references the same object)
```

## `typeof` operator
The `typeof` operator in JavaScript is used to determine the type of a variable or value. It returns a string indicating the type of the operand. The `typeof` operator can be used with both primitive and reference types.
```js
let num = 42;
console.log(typeof num); // Output: "number"

let str = "Hello";
console.log(typeof str); // Output: "string"

let bool = true;
console.log(typeof bool); // Output: "boolean"

let obj = { name: "Alice" };
console.log(typeof obj); // Output: "object"

let arr = [1, 2, 3];
console.log(typeof arr); // Output: "object" (arrays are objects)

let func = function() {};
console.log(typeof func); // Output: "function"
```


## What is Dynamic Typing in JavaScript?
Dynamic typing is a feature of JavaScript that allows variables to hold values of different data types at different times during the execution of a program. In dynamically typed languages like JavaScript, you do not need to explicitly declare the data type of a variable when you create it. Instead, the type is determined at runtime based on the value assigned to the variable.
### Example of Dynamic Typing
```js
let variable = 42; // variable is a number
console.log(typeof variable); // Output: "number"

variable = "Hello"; // variable is now a string
console.log(typeof variable); // Output: "string"

variable = true; // variable is now a boolean
console.log(typeof variable); // Output: "boolean"
```

## What is Type Coercion in JavaScript?
Type coercion is the automatic or implicit conversion of values from one data type to another in JavaScript. This can happen when performing operations involving different data types, such as adding a number and a string. JavaScript will attempt to convert one of the values to a compatible type to complete the operation.
### Example of Type Coercion
```js
let num = 5;
let str = "10";
let result = num + str; // The number 5 is coerced to a string, resulting in string concatenation
console.log(result); // Output: "510" (string concatenation)
```

## Truthy and Falsy Values
In JavaScript, values can be classified as either "truthy" or "falsy" based on how they evaluate in a boolean context. A truthy value is any value that evaluates to `true` when used in a conditional statement, while a falsy value evaluates to `false`.
### Falsy Values
```js
let falsyValues = [false, 0, -0, 0n, "", null, undefined, NaN];
falsyValues.forEach(value => {
  if (!value) {
    console.log(`${value} is falsy`);
  }
});
```
### Truthy Values
```js
let truthyValues = [true, 1, -1, "hello", [], {}, function() {}];
truthyValues.forEach(value => {
  if (value) {
    console.log(`${value} is truthy`);
  }
});
```

# JavaScript Operators
JavaScript provides a variety of operators that can be used to perform operations on values and variables.

## Arithmetic Operators
Arithmetic operators are used to perform mathematical operations on numeric values. The common arithmetic operators in JavaScript include:
- Addition (`+`): Adds two numbers or concatenates strings.
- Subtraction (`-`): Subtracts one number from another.
- Multiplication (`*`): Multiplies two numbers.
- Division (`/`): Divides one number by another.
- Modulus (`%`): Returns the remainder of a division operation.
- Exponentiation (`**`): Raises a number to the power of another number.
- Increment (`++`): Increases a number by one.
- Decrement (`--`): Decreases a number by one.
- Example of Arithmetic Operators
```js
let a = 10;
let b = 3;
console.log(a + b); // Output: 13 (Addition)
console.log(a - b); // Output: 7 (Subtraction)
console.log(a * b); // Output: 30 (Multiplication)
console.log(a / b); // Output: 3.3333333333333335 (Division)
console.log(a % b); // Output: 1 (Modulus)
console.log(a ** b); // Output: 1000 (Exponentiation)
a++; // Increment
console.log(a); // Output: 11
b--; // Decrement
console.log(b); // Output: 2
```

## Assignment Operators
Assignment operators are used to assign values to variables. The most common assignment operator is the equal sign (`=`), which assigns the value on the right to the variable on the left. There are also compound assignment operators that combine an arithmetic operation with assignment, such as `+=`, `-=`, `*=`, `/=`, and `%=`.
### Example of Assignment Operators
```js
let x = 5; // Assignment
x += 3; // Equivalent to x = x + 3
console.log(x); // Output: 8
x -= 2; // Equivalent to x = x - 2
console.log(x); // Output: 6
x *= 4; // Equivalent to x = x * 4
console.log(x); // Output: 24
x /= 6; // Equivalent to x = x / 6
console.log(x); // Output: 4
x %= 3; // Equivalent to x = x % 3
console.log(x); // Output: 1
```

## Comparison Operators
Comparison operators are used to compare two values and return a boolean result (`true` or `false`). The common comparison operators in JavaScript include:
- Equal to (`==`): Checks if two values are equal, performing type coercion if necessary.
- Strict equal to (`===`): Checks if two values are equal without type coercion.
- Not equal to (`!=`): Checks if two values are not equal, performing type coercion if necessary.
- Strict not equal to (`!==`): Checks if two values are not equal without type coercion.
- Greater than (`>`): Checks if the left value is greater than the right value.
- Greater than or equal to (`>=`): Checks if the left value is greater than or equal to the right value.
- Less than (`<`): Checks if the left value is less than the right value.
- Less than or equal to (`<=`): Checks if the left value is less than or equal to the right value.
### Example of Comparison Operators
```js
let a = 10;
let b = "10";
console.log(a == b); // Output: true (Equal to, with type coercion)
console.log(a === b); // Output: false (Strict equal to, no type coercion)
console.log(a != b); // Output: false (Not equal to, with type coercion)
console.log(a !== b); // Output: true (Strict not equal to, no type coercion)
console.log(a > 5); // Output: true (Greater than)
console.log(a >= 10); // Output: true (Greater than or equal to)
console.log(a < 15); // Output: true (Less than)
console.log(a <= 10); // Output: true (Less than or equal to)
```

## Logical Operators
Logical operators are used to combine or invert boolean values. The common logical operators in JavaScript include:
- Logical AND (`&&`): Returns `true` if both operands are `true`, otherwise returns `false`.
- Logical OR (`||`): Returns `true` if at least one of the operands is `true`, otherwise returns `false`.
- Logical NOT (`!`): Inverts the boolean value of the operand, returning `true if the operand is `false` and `false` if the operand is `true`.

### Example of Logical Operators
```js
let x = true;
let y = false;
console.log(x && y); // Output: false (Logical AND)
console.log(x || y); // Output: true (Logical OR)
console.log(!x); // Output: false (Logical NOT)
console.log(!y); // Output: true (Logical NOT)
```

## Nullish Coalescing Operator (`??`)
The nullish coalescing operator (`??`) is a logical operator that returns the right-hand operand when the left-hand operand is `null` or `undefined`. If the left-hand operand is any other value (including falsy values like `0`, `false`, or an empty string), it returns the left-hand operand. This operator is useful for providing default values when dealing with potentially null or undefined variables.

### Example of Nullish Coalescing Operator
```js
let value1 = null;
let value2 = "Hello, world!";
let result1 = value1 ?? "Default value"; // value1 is null, so result1 will be "Default value"
console.log(result1); // Output: "Default value"
let result2 = value2 ?? "Default value"; // value2 is not null or undefined, so result2 will be "Hello, world!"
console.log(result2); // Output: "Hello, world!"
```

## Optional Chaining Operator (`?.`)
The optional chaining operator (`?.`) is a feature in JavaScript that allows you to safely access deeply nested properties of an object without having to check for the existence of each property in the chain. If any part of the chain is `null` or `undefined`, the expression short-circuits and returns `undefined` instead of throwing an error.

### Example of Optional Chaining Operator
```js
let user = {
  name: "Alice",
  address: {
    city: "Wonderland",
    zip: "12345"
  }
};
console.log(user?.name); // Output: "Alice"
console.log(user?.address?.city); // Output: "Wonderland"
console.log(user?.address?.country); // Output: undefined (country does not exist)
console.log(user?.contact?.email); // Output: undefined (contact does not exist)
```

## Ternary Operator (`? :`)
The ternary operator is a conditional operator that provides a shorthand way to write an `if-else` statement. It takes three operands: a condition, an expression to execute if the condition is true, and an expression to execute if the condition is false. The syntax is as follows:
```js
condition ? expressionIfTrue : expressionIfFalse;
```
### Example of Ternary Operator
```js
let age = 18;
let canVote = (age >= 18) ? "Yes, you can vote." : "No, you cannot vote.";
console.log(canVote); // Output: "Yes, you can vote."
```

## Unary Operators
Unary operators are operators that operate on a single operand. They perform various operations such as type conversion, negation, and increment/decrement. Common unary operators in JavaScript include:
- Unary plus (`+`): Converts a value to a number.
- Unary negation (`-`): Negates a numeric value.
- Increment (`++`): Increases a numeric value by one.
- Decrement (`--`): Decreases a numeric value by one.

### Example of Unary Operators
```js
let num = "5";
console.log(+num); // Output: 5 (Unary plus converts string to number)
console.log(-num); // Output: -5 (Unary negation negates the numeric value)
console.log(++num); // Output: 6 (Increment increases the numeric value by one)
console.log(--num); // Output: 5 (Decrement decreases the numeric value by one)
```

## Increment and Decrement Operators
The increment (`++`) and decrement (`--`) operators are unary operators that increase or decrease the value of a variable by one, respectively. They can be used in both prefix and postfix forms, which affects the order of operations when used in expressions.

### Example of Increment and Decrement Operators
```js
let count = 5;
// Prefix increment
console.log(++count); // Output: 6 (Prefix increment increases the value before using it)
// Postfix increment
console.log(count++); // Output: 6 (Postfix increment increases the value after using it)
console.log(count);   // Output: 7 (Value after postfix increment)
// Prefix decrement
console.log(--count); // Output: 6 (Prefix decrement decreases the value before using it)
// Postfix decrement
console.log(count--); // Output: 6 (Postfix decrement decreases the value after using it)
console.log(count);   // Output: 5 (Value after postfix decrement)
```

## instanceof Operator
The `instanceof` operator is used to check whether an object is an instance of a specific constructor or class. It returns `true` if the object is an instance of the specified constructor, and `false` otherwise. This operator is useful for type checking and determining the prototype chain of an object.

### Example of instanceof Operator
```js
class Person {
  constructor(name) {
    this.name = name;
  }
}
let person = new Person("Alice");
console.log(person instanceof Person); // Output: true (person is an instance of Person)
console.log(person instanceof Object); // Output: true (person is also an instance of Object)
console.log(person instanceof Array);  // Output: false (person is not an instance of Array)
```

## Operator Precedence
Operator precedence determines the order in which operators are evaluated in an expression. Operators with higher precedence are evaluated before operators with lower precedence. If operators have the same precedence, their associativity (left-to-right or right-to-left) determines the order of evaluation.

### Example of Operator Precedence
```js
let result = 3 + 4 * 2; // Multiplication has higher precedence than addition
console.log(result); // Output: 11 (4 * 2 is evaluated first, then added to 3)
let result2 = (3 + 4) * 2; // Parentheses change the order of evaluation
console.log(result2); // Output: 14 (3 + 4 is evaluated first, then multiplied by 2)
```

# Control Flow in JavaScript
Control flow in JavaScript refers to the order in which statements and instructions are executed in a program. JavaScript provides various control flow statements that allow developers to make decisions, repeat actions, and control the execution of code based on certain conditions. The main control flow statements in JavaScript include conditional statements, loops, and switch statements.

## if statement
The `if` statement is used to execute a block of code only if a specified condition evaluates to `true`. If the condition is `false`, the code block is skipped.

### Syntax
```js
if (condition) {
  // Code to be executed if the condition is true
}
```

### Example
```js
let age = 18;
if (age >= 18) {
  console.log("You are an adult.");
}
```

## if...else statement
The `if...else` statement allows you to execute one block of code if a condition is true, and another block of code if the condition is false.

### Syntax
```js
if (condition) {
  // Code to be executed if the condition is true
} else {
  // Code to be executed if the condition is false
}
```

### Example
```js
let age = 16;
if (age >= 18) {
  console.log("You are an adult.");
} else {
  console.log("You are a minor.");
}
```

## if...else if...else statement
The `if...else if...else` statement allows you to test multiple conditions in sequence. If one condition is true, its corresponding block of code is executed, and the rest are skipped. If none of the conditions are true, the `else` block is executed.

### Syntax
```js
if (condition1) {
  // Code to be executed if condition1 is true
} else if (condition2) {
  // Code to be executed if condition2 is true
} else {
  // Code to be executed if none of the conditions are true
}
```

### Example
```js
let score = 85;
if (score >= 90) {
  console.log("Grade: A");
} else if (score >= 80) {
  console.log("Grade: B");
} else if (score >= 70) {
  console.log("Grade: C");
} else {
  console.log("Grade: F");
}
```

## Nested if else statements
Nested `if...else` statements are `if` statements placed inside another `if` or `else` block. This allows for more complex decision-making by checking multiple conditions in a hierarchical manner.

### Syntax
```js
if (condition1) {
  // Code to be executed if condition1 is true
  if (condition2) {
    // Code to be executed if condition2 is true
  } else {
    // Code to be executed if condition2 is false
  }
} else {
  // Code to be executed if condition1 is false
}
```

### Example
```js
let age = 20;
if (age >= 18) {
  console.log("You are an adult.");
  if (age >= 21) {
    console.log("You can also drink alcohol in the US.");
  } else {
    console.log("You cannot drink alcohol in the US.");
  }
} else {
  console.log("You are a minor.");
}
```

## switch statement
The `switch` statement is used to perform different actions based on different conditions. It evaluates an expression and matches its value against multiple `case` clauses. If a match is found, the corresponding block of code is executed. The `default` clause can be used to execute code if no matches are found.

### Syntax
```js
switch (expression) {
  case value1:
    // Code to be executed if expression === value1
    break;
  case value2:
    // Code to be executed if expression === value2
    break;
  // Add more cases as needed
  default:
    // Code to be executed if no cases match
}
```

### Example
```js
let day = 3;
switch (day) {
  case 1:
    console.log("Monday");
    break;
  case 2:
    console.log("Tuesday");
    break;
  case 3:
    console.log("Wednesday");
    break;
  case 4:
    console.log("Thursday");
    break;
  case 5:
    console.log("Friday");
    break;
  case 6:
    console.log("Saturday");
    break;
  case 7:
    console.log("Sunday");
    break;
  default:
    console.log("Invalid day");
}
```

## break continue statement
The `break` and `continue` statements are used to control the flow of loops in JavaScript.

### break statement
The `break` statement is used to exit a loop prematurely, terminating the loop's execution and transferring control to the statement immediately following the loop.

### Example of break statement
```js
for (let i = 1; i <= 10; i++) {
  if (i === 5) {
    break; // Exit the loop when i is 5
  }
  console.log(i); // Output: 1, 2, 3, 4
}
```

### continue statement
The `continue` statement is used to skip the current iteration of a loop and move on to the next iteration. It does not terminate the loop but instead skips the remaining code in the current iteration.

### Example of continue statement
```js
for (let i = 1; i <= 10; i++) {
  if (i === 5) {
    continue; // Skip the iteration when i is 5
  }
  console.log(i); // Output: 1, 2, 3, 4, 6, 7, 8, 9, 10
}
```

## for loop
The `for` loop is a control flow statement that allows you to execute a block of code a specific number of times. It consists of three parts: initialization, condition, and increment/decrement. The loop continues to execute as long as the condition evaluates to `true`.

### Syntax
```js
for (initialization; condition; increment/decrement) {
  // Code to be executed in each iteration
}
```

### Example of for loop
```js
for (let i = 1; i <= 5; i++) {
  console.log(i); // Output: 1, 2, 3, 4, 5
}
```

## while loop
The `while` loop is a control flow statement that allows you to execute a block of code repeatedly as long as a specified condition evaluates to `true`. The condition is checked before each iteration, and if it evaluates to `false`, the loop terminates.

### Syntax
```js
while (condition) {
  // Code to be executed in each iteration
}
```

### Example of while loop
```js
let i = 1;
while (i <= 5) {
  console.log(i); // Output: 1, 2, 3, 4, 5
  i++;
}
```

## do...while loop
The `do...while` loop is a control flow statement that allows you to execute a block of code at least once, and then repeatedly as long as a specified condition evaluates to `true`. The condition is checked after each iteration, ensuring that the code block is executed at least once regardless of the condition.

### Syntax
```js
do {
  // Code to be executed in each iteration
} while (condition);
```

### Example of do...while loop
```js
let i = 1;
do {
  console.log(i); // Output: 1, 2, 3, 4, 5
  i++;
} while (i <= 5);
```

## for...in loop
The `for...in` loop is a control flow statement that allows you to iterate over the enumerable properties of an object. It iterates through the keys (property names) of the object, allowing you to access both the keys and their corresponding values.

### Syntax
```js
for (variable in object) {
  // Code to be executed for each property
}
```

### Example of for...in loop
```js
let person = {
  name: "Alice",
  age: 30,
  city: "Wonderland"
};
for (let key in person) {
  console.log(key + ": " + person[key]);
}
// Output:
// name: Alice
// age: 30
// city: Wonderland
```

## for...of loop
The `for...of` loop is a control flow statement that allows you to iterate over iterable objects, such as arrays, strings, maps, sets, and more. It iterates through the values of the iterable object, allowing you to access each value directly.

### Syntax
```js
for (variable of iterable) {
  // Code to be executed for each value
}
```

### Example of for...of loop
```js
let numbers = [1, 2, 3, 4, 5];
for (let number of numbers) {
  console.log(number); // Output: 1, 2, 3, 4, 5
}
```

## Nested Loops
Nested loops are loops that are placed inside another loop. The inner loop is executed completely for each iteration of the outer loop. Nested loops can be used to iterate over multi-dimensional data structures, such as arrays of arrays.

### Example of Nested Loops
```js
let matrix = [
  [1, 2, 3],
  [4, 5, 6],
  [7, 8, 9]
];
for (let i = 0; i < matrix.length; i++) {
  for (let j = 0; j < matrix[i].length; j++) {
    console.log(matrix[i][j]);
  }
}
// Output:
// 1
// 2
// 3
// 4
// 5
// 6
// 7
// 8
// 9
```

# Functions in JavaScript
Functions in JavaScript are reusable blocks of code that perform a specific task. They allow you to encapsulate logic, making your code more organized and easier to maintain. Functions can take input parameters, perform operations, and return values.

## Function Declaration
A function declaration defines a named function that can be called later in the code. It consists of the `function` keyword, followed by the function name, a list of parameters in parentheses, and a block of code enclosed in curly braces.

### Syntax
```js
function functionName(parameters) {
  // Code to be executed
}
```

### Example of Function Declaration
```js
function greet(name) {
  return "Hello, " + name + "!";
}
console.log(greet("Alice")); // Output: Hello, Alice!
```

## Function Expression
A function expression defines a function as part of an expression. It can be anonymous (without a name) or named, and it can be assigned to a variable. Function expressions are not hoisted like function declarations, meaning they cannot be called before they are defined.

### Syntax
```js
let functionName = function(parameters) {
  // Code to be executed
};
```

### Example of Function Expression
```js
let greet = function(name) {
  return "Hello, " + name + "!";
};
console.log(greet("Bob")); // Output: Hello, Bob!
```

## Function Parameters and Arguments
Function parameters are variables that are defined in the function declaration or expression and are used to accept input values when the function is called. Arguments are the actual values passed to the function when it is invoked.

### Example of Function Parameters and Arguments
```js
function add(a, b) { // a and b are parameters
  return a + b;
}
console.log(add(2, 3)); // Output: 5 // 2 and 3 are arguments
```

## Return Values
Functions can return values using the `return` statement. When a function is called, it can perform operations and return a result to the caller. If no `return` statement is specified, the function returns `undefined` by default.

### Example of Return Values
```js
function multiply(a, b) {
  return a * b; // Returns the product of a and b
}
console.log(multiply(4, 5)); // Output: 20
```

## Default Parameters
Default parameters allow you to specify default values for function parameters. If an argument is not provided for a parameter with a default value, the default value will be used instead.

### Syntax
```js
function functionName(parameter = defaultValue) {
  // Code to be executed
}
```

### Example of Default Parameters
```js
function greet(name = "Guest") {
  return "Hello, " + name + "!";
}
console.log(greet()); // Output: Hello, Guest!
console.log(greet("Alice")); // Output: Hello, Alice!
```

## Rest Parameters
Rest parameters allow you to represent an indefinite number of arguments as an array. This is useful when you want to create functions that can accept a variable number of arguments.

### Syntax
```js
function functionName(...restParameter) {
  // Code to be executed
}
```

### Example of Rest Parameters
```js
function sum(...numbers) {
  return numbers.reduce((total, num) => total + num, 0);
}
console.log(sum(1, 2, 3)); // Output: 6
console.log(sum(4, 5, 6, 7)); // Output: 22
```

## Spread Operator
The spread operator (`...`) allows you to expand an iterable (like an array or string) into individual elements. It can be used in function calls, array literals, and object literals. The spread operator is useful for copying arrays, merging arrays, and passing multiple arguments to functions.

### Example of Spread Operator
```js
let numbers = [1, 2, 3];
console.log(...numbers); // Output: 1 2 3
```

## Anonymous Functions
Anonymous functions are functions that do not have a name. They are often used as arguments to other functions, such as in callbacks or event handlers. Anonymous functions can be defined using function expressions or arrow functions.

### Example of Anonymous Functions
```js
let greet = function(name) {
  return "Hello, " + name + "!";
};
console.log(greet("Charlie")); // Output: Hello, Charlie!
```

## Callback Functions
A callback function is a function that is passed as an argument to another function and is executed after some operation has been completed. Callback functions are commonly used in asynchronous programming, event handling, and higher-order functions.

### Example of Callback Functions
```js
function fetchData(callback) {
  setTimeout(() => {
    const data = "Sample data";
    callback(data); // Execute the callback function with the fetched data
  }, 1000);
}
fetchData((data) => {
  console.log(data); // Output: Sample data (after 1 second)
});
```

## Higher-Order Functions
Higher-order functions are functions that can take other functions as arguments or return functions as their result. They allow for more abstract and flexible programming patterns, enabling the creation of reusable and composable code.

### Example of Higher-Order Functions
```js
function greet(name) {
  return function(message) {
    return "Hello, " + name + "! " + message;
  };
}

let greetAlice = greet("Alice");
console.log(greetAlice("Welcome to the JavaScript world!")); // Output: Hello, Alice! Welcome to the JavaScript world!
```

## First-Class Functions
In JavaScript, functions are first-class citizens, meaning they can be treated like any other value. This allows functions to be assigned to variables, passed as arguments to other functions, and returned from other functions. First-class functions enable powerful programming patterns and functional programming techniques.

### Example of First-Class Functions
```js
function add(a, b) {
  return a + b;
}

let sum = add;
console.log(sum(2, 3)); // Output: 5
```

## Arrow Functions
Arrow functions are a concise way to define functions in JavaScript. They use the `=>` syntax and have a shorter syntax compared to traditional function expressions. Arrow functions also have lexical scoping for the `this` keyword, meaning they do not have their own `this` context but inherit it from the surrounding scope.

### Syntax
```js
let functionName = (parameters) => {
  // Code to be executed
};
```

### Example of Arrow Functions
```js
let greet = (name) => {
  return "Hello, " + name + "!";
};
console.log(greet("David")); // Output: Hello, David!
```

## Immediately Invoked Function Expressions (IIFE)
An Immediately Invoked Function Expression (IIFE) is a function that is defined and executed immediately after its creation. IIFEs are often used to create a new scope, avoid polluting the global namespace, and encapsulate code.

### Syntax
```js
(function() {
  // Code to be executed immediately
})();
```

### Example of IIFE
```js
(function() {
  let message = "Hello from IIFE!";
  console.log(message); // Output: Hello from IIFE!
})();
```

## Pure Functions
A pure function is a function that, given the same input, will always return the same output and does not have any side effects (i.e., it does not modify any external state or variables). Pure functions are predictable, easier to test, and can be memoized for performance optimization.

### Example of Pure Functions
```js
function add(a, b) {
  return a + b; // Always returns the same output for the same inputs
}
console.log(add(2, 3)); // Output: 5
```

## Side Effects
A side effect is any observable change in the state of the program or interaction with the outside world that occurs as a result of executing a function. Side effects can include modifying global variables, changing the value of an object property, performing I/O operations (like logging to the console or writing to a file), or making network requests. Functions that produce side effects are called impure functions.

### Example of Side Effects
```js
let counter = 0; // Global variable
function incrementCounter() {
  counter++; // Modifies the global variable, causing a side effect
}

incrementCounter();
console.log(counter); // Output: 1 (The global variable has been modified)
```

## Function Composition
Function composition is a programming technique where multiple functions are combined to create a new function. The output of one function becomes the input of the next function in the composition chain. This allows for building complex functionality by combining simpler functions, promoting code reusability and modularity.

### Example of Function Composition
```js
function add(a, b) {
  return a + b;
}
function multiply(a, b) {
  return a * b;
}
function compose(f, g) {
  return function(x, y) {
    return f(g(x, y), y);
  };
}
const addThenMultiply = compose(multiply, add);
console.log(addThenMultiply(2, 3)); // Output: 15 (add(2, 3) = 5, then multiply(5, 3) = 15)
```

## Recursion
Recursion is a programming technique where a function calls itself in order to solve a problem. Recursive functions typically have a base case that stops the recursion and one or more recursive cases that break the problem down into smaller subproblems. Recursion can be used to solve problems that can be defined in terms of smaller instances of the same problem.

### Example of Recursion
```js
function factorial(n) {
  if (n === 0 || n === 1) { // Base case
    return 1;
  }
  return n * factorial(n - 1); // Recursive case
}
console.log(factorial(5)); // Output: 120
```

### Simple example of recursion
```js
function countdown(n) {
  if (n <= 0) { // Base case
    console.log("Done!");
    return;
  }
  console.log(n); // Print the current number
  countdown(n - 1); // Recursive call with decremented value
}
console.log(countdown(5)); // Output: 5 4 3 2 1 Done!
```

## Call stack
The call stack is a data structure used by the JavaScript engine to keep track of function calls. It operates on a Last In, First Out (LIFO) principle, meaning that the last function called is the first one to be completed and removed from the stack. When a function is invoked, it is added to the top of the call stack, and when it returns, it is removed from the stack. If a function calls another function, the new function is added to the top of the stack, and this process continues until all functions have completed execution.

### Example of Call Stack
```js
function first() {
  console.log("First function");
  second(); // Call to second function
}
function second() {
  console.log("Second function");
  third(); // Call to third function
}
function third() {
  console.log("Third function");
}
first(); // Start the call stack
// Output:
// First function
// Second function
// Third function
```

# Scope in JavaScript
Scope in JavaScript refers to the accessibility or visibility of variables and functions in different parts of the code. JavaScript has function scope and block scope.

## Global Scope
Global scope refers to variables and functions that are accessible from anywhere in the code. Variables declared outside of any function or block are in the global scope. In a browser environment, global variables are properties of the `window` object.

### Example of Global Scope
```js
let globalVar = "I am a global variable"; // Declared in the global scope
function showGlobalVar() {
  console.log(globalVar); // Accessible inside the function
}
showGlobalVar(); // Output: I am a global variable
```

## Function Scope
Function scope refers to variables and functions that are accessible only within the function in which they are declared. Variables declared with `var` have function scope, meaning they are accessible throughout the entire function, but not outside of it.

### Example of Function Scope
```js
function showLocalVar() {
  var localVar = "I am a local variable"; // Declared in the function scope
  console.log(localVar); // Accessible inside the function
}
showLocalVar(); // Output: I am a local variable
console.log(localVar); // Error: localVar is not defined
```

## Block Scope
Block scope refers to variables that are accessible only within the block (enclosed by `{}`) in which they are declared. Variables declared with `let` and `const` have block scope, meaning they are not accessible outside of the block.

### Example of Block Scope
```js
{
  let blockVar = "I am a block-scoped variable"; // Declared in the block scope
  console.log(blockVar); // Accessible inside the block
}
console.log(blockVar); // Error: blockVar is not defined
```

## Lexical Scope
Lexical scope, also known as static scope, refers to the fact that the accessibility of variables is determined by their physical placement in the source code. In JavaScript, functions are lexically scoped, meaning that a function can access variables from its own scope and from the scopes of its parent functions.

### Example of Lexical Scope
```js
function outerFunction() {
  let outerVar = "I am from the outer function"; // Variable in the outer function's scope
  function innerFunction() {
    console.log(outerVar); // Accessible due to lexical scope
  }
  innerFunction(); // Call the inner function
}
outerFunction(); // Output: I am from the outer function
```

## Scope Chain
The scope chain is a mechanism in JavaScript that determines the order in which variable lookups occur. When a variable is accessed, JavaScript first looks for it in the current scope. If it is not found, it moves up to the parent scope, and continues this process until it reaches the global scope. This chain of scopes is known as the scope chain.

### Example of Scope Chain
```js
function outerFunction() {
  let outerVar = "I am from the outer function"; // Variable in the outer function's scope
  function innerFunction() {
    let innerVar = "I am from the inner function"; // Variable in the inner function's scope
    console.log(innerVar); // Accessible in the inner function
    console.log(outerVar); // Accessible due to scope chain
  }
  innerFunction(); // Call the inner function
}
outerFunction();
// Output:
// I am from the inner function
// I am from the outer function
```

## Variable Shadowing
Variable shadowing occurs when a variable declared in a local scope (e.g., inside a function or block) has the same name as a variable in an outer scope. In such cases, the local variable "shadows" the outer variable, meaning that the local variable takes precedence and is used within its scope.

### Example of Variable Shadowing
```js
let name = "Global Name"; // Variable in the global scope
function showName() {
  let name = "Local Name"; // Variable in the local scope, shadows the global variable
  console.log(name); // Output: Local Name (the local variable is used)
}
showName();
console.log(name); // Output: Global Name (the global variable is still accessible outside the function)
```

## var vs let vs const
In JavaScript, `var`, `let`, and `const` are used to declare variables, but they have different characteristics and behaviors.

### var
- `var` is function-scoped, meaning it is accessible throughout the entire function in which it is declared.
- Variables declared with `var` are hoisted to the top of their scope, meaning they can be used before they are declared, but their value will be `undefined` until the assignment is reached.

### Example of var
```js
var globalVar = "I am a global variable";
function showVar() {
  console.log(globalVar); // Accessible inside the function
  var localVar = "I am a local variable"; // Declared in the function scope
  console.log(localVar); // Accessible inside the function
}
showVar();
console.log(localVar); // Error: localVar is not defined (not accessible outside the function)
```

### let
- `let` is block-scoped, meaning it is accessible only within the block in which it is declared.
- Variables declared with `let` are not hoisted in the same way as `var`, and they cannot be accessed before their declaration (this is known as the "temporal dead zone").

### Example of let
```js
{
  let blockVar = "I am a block-scoped variable"; // Declared in the block scope
  console.log(blockVar); // Accessible inside the block
}

console.log(blockVar); // Error: blockVar is not defined (not accessible outside the block)
```

### const
- `const` is also block-scoped, like `let`, but it is used to declare variables that cannot be reassigned after their initial assignment.
- Variables declared with `const` must be initialized at the time of declaration, and their value cannot be changed. However, if the variable is an object or array, the contents of the object or array can still be modified.

### Example of const
```js
const pi = 3.14159; // Declared as a constant
console.log(pi); // Output: 3.14159

// Attempting to reassign a const variable will result in an error
// pi = 3.14; // Error: Assignment to constant variable
```

## Temporal Dead Zone (TDZ)
The Temporal Dead Zone (TDZ) is a behavior in JavaScript that occurs when variables declared with `let` or `const` are accessed before they are initialized. During the TDZ, the variable exists in the scope but cannot be accessed, and attempting to do so will result in a `ReferenceError`. The TDZ helps prevent the use of uninitialized variables and encourages better coding practices.

### Example of Temporal Dead Zone
```js
{
  // console.log(myVar); // Error: Cannot access 'myVar' before initialization (TDZ)
  let myVar = "I am a block-scoped variable";
  console.log(myVar); // Output: I am a block-scoped variable
}
```

### Another example of Temporal Dead Zone
```js
// TDZ of a variable starts here
// TDZ of b variable starts here

// console.log(a); // Output: 10 (a is hoisted and initialized)

const a = 10; // a is initialized here
// console.log(b); // Error: Cannot access 'b' before initialization (TDZ)

const b = 20; // b is initialized here
```

## Closure
A closure is a feature in JavaScript where an inner function has access to the variables and parameters of its outer function, even after the outer function has finished executing. Closures allow for data encapsulation and can be used to create private variables and functions.

### Example of Closure
```js
function outerFunction(outerVariable) {
  return function innerFunction(innerVariable) {
    console.log("Outer Variable: " + outerVariable); // Accessing outer function's variable
    console.log("Inner Variable: " + innerVariable); // Accessing inner function's variable
  };
}
const closureExample = outerFunction("outer value");
closureExample("inner value");
// Output:
// Outer Variable: outer value
// Inner Variable: inner value
```

## Practical closure patterns

### Example: Private Counter
```js
function createCounter() {
  let count = 0; // Private variable
  return {
    increment: function() {
      count++;
      return count;
    },
    decrement: function() {
      count--;
      return count;
    },
    getCount: function() {
      return count;
    }
  };
}
const counter = createCounter();
console.log(counter.increment()); // Output: 1
console.log(counter.increment()); // Output: 2
console.log(counter.getCount()); // Output: 2
console.log(counter.decrement()); // Output: 1
console.log(counter.getCount()); // Output: 1
```

### Simple example
```js
function outerFunction() {
  let outerVariable = "I am from the outer function"; // Variable in the outer function's scope
  function innerFunction() {
    console.log(outerVariable); // Accessing outer function's variable
  }
  return innerFunction; // Returning the inner function
}
const closureExample = outerFunction(); // outerFunction is executed, returning innerFunction
closureExample(); // Output: I am from the outer function (innerFunction has access to outerVariable)
```

# Arrays in JavaScript
Arrays in JavaScript are ordered collections of values that can hold multiple data types, including numbers, strings, objects, and even other arrays. Arrays are zero-indexed, meaning the first element is at index 0. They provide various methods for adding, removing, and manipulating elements.

## Creating Arrays
There are several ways to create arrays in JavaScript:

### Using Array Literals
```js
const fruits = ["Apple", "Banana", "Cherry"];
console.log(fruits); // Output: ["Apple", "Banana", "Cherry"]
```

### Using the Array Constructor
```js
const numbers = new Array(1, 2, 3, 4, 5);
console.log(numbers); // Output: [1, 2, 3, 4, 5]
```

### Using Array.of
```js
const colors = Array.of("Red", "Green", "Blue");
console.log(colors); // Output: ["Red", "Green", "Blue"]
```

## Accessing Elements
You can access elements in an array using their index. The index starts at 0 for the first element.

### Example of Accessing Elements
```js
const fruits = ["Apple", "Banana", "Cherry"];
console.log(fruits[0]); // Output: Apple (first element)
console.log(fruits[1]); // Output: Banana (second element)
console.log(fruits[2]); // Output: Cherry (third element)
```

## Updating Elements
You can update elements in an array by assigning a new value to a specific index.

### Example of Updating Elements
```js
const fruits = ["Apple", "Banana", "Cherry"];
fruits[1] = "Blueberry"; // Updating the second element
console.log(fruits); // Output: ["Apple", "Blueberry", "Cherry"]
```

## Array Length
The `length` property of an array returns the number of elements in the array. It can also be used to set the length of the array, which can truncate or expand the array.

### Example of Array Length
```js
const fruits = ["Apple", "Banana", "Cherry"];
console.log(fruits.length); // Output: 3 (number of elements in the array)
```

## Nested Arrays
Nested arrays, also known as multidimensional arrays, are arrays that contain other arrays as their elements. They can be used to represent more complex data structures, such as matrices or grids.

### Example of Nested Arrays
```js
const matrix = [
  [1, 2, 3],
  [4, 5, 6],
  [7, 8, 9]
];
console.log(matrix[0][1]); // Output: 2 (accessing the second element of the first array)
console.log(matrix[2][0]); // Output: 7 (accessing the first element of the third array)
```

## Destructuring Arrays
Array destructuring is a feature in JavaScript that allows you to unpack values from arrays into distinct variables. This provides a concise and readable way to extract elements from an array.

### Syntax
```js
const [var1, var2, ...rest] = array;
```

### Example of Destructuring Arrays
```js
const fruits = ["Apple", "Banana", "Cherry"];
const [firstFruit, secondFruit] = fruits; // Destructuring the first two elements
console.log(firstFruit); // Output: Apple
console.log(secondFruit); // Output: Banana
```

## Array Methods
JavaScript provides a variety of built-in methods for working with arrays. These methods allow you to manipulate, transform, and access array elements in different ways. Some commonly used array methods include:

### Array Methods
- `push()`
- `pop()`
- `shift()`
- `unshift()`
- `slice()`
- `splice()`
- `concat()`
- `join()`
- `includes()`
- `indexOf()`
- `find()`
- `findIndex()`
- `findLast()`
- `findLastIndex()`
- `filter()`
- `map()`
- `reduce()`
- `reduceRight()`
- `some()`
- `every()`
- `sort()`
- `reverse()`
- `flat()`
- `flatMap()`
- `forEach()`
- Array-like objects
- `Array.from()`
- `Array.isArray()`

```js
const fruits = ["Apple", "Banana", "Cherry"];

console.log(fruits.push("Date")); // Adds "Date" to the end of the array

console.log(fruits.pop()); // Removes the last element ("Date") from the array

console.log(fruits.shift()); // Removes the first element ("Apple") from the array

console.log(fruits.unshift("Apricot")); // Adds "Apricot" to the beginning of the array

console.log(fruits.slice(1, 3)); // Returns a new array with elements from index 1 to 2

console.log(fruits.splice(1, 1, "Blueberry")); // Removes 1 element at index 1 and adds "Blueberry"

console.log(fruits.concat(["Elderberry", "Fig"])); // Returns a new array by merging two arrays

console.log(fruits.join(", ")); // Joins all elements into a string separated by ", "

console.log(fruits.includes("Cherry")); // Checks if "Cherry" is in the array

console.log(fruits.indexOf("Banana")); // Returns the index of "Banana" in the array

console.log(fruits.find(fruit => fruit.startsWith("B"))); // Finds the first element that starts with "B"

console.log(fruits.findIndex(fruit => fruit.startsWith("C"))); // Finds the index of the first element that starts with "C"

console.log(fruits.findLast(fruit => fruit.startsWith("B"))); // Finds the last element that starts with "B"

console.log(fruits.findLastIndex(fruit => fruit.startsWith("B"))); // Finds the index of the last element that starts with "B"

console.log(fruits.filter(fruit => fruit.length > 5)); // Returns a new array with elements that have length greater than 5

console.log(fruits.map(fruit => fruit.toUpperCase())); // Returns a new array with all elements in uppercase

console.log(fruits.reduce((acc, fruit) => acc + ", " + fruit)); // Reduces the array to a single string

console.log(fruits.reduceRight((acc, fruit) => acc + ", " + fruit)); // Reduces the array to a single string from right to left

console.log(fruits.some(fruit => fruit.startsWith("A"))); // Checks if any element starts with "A"

console.log(fruits.every(fruit => fruit.length > 3)); // Checks if all elements have length greater than 3

console.log(fruits.sort()); // Sorts the array in ascending order

console.log(fruits.reverse()); // Reverses the array

console.log(fruits.flat()); // Flattens a nested array into a single array

console.log(fruits.flatMap(fruit => [fruit, fruit.length])); // Maps each element to an array and flattens the result

console.log(fruits.forEach(fruit => console.log(fruit))); // Executes a function for each element in the array

console.log(Array.from("Hello")); // Creates an array from a string 

console.log(Array.isArray(fruits)); // Checks if fruits is an array

console.log(Array.of(1, 2, 3)); // Creates a new array with the provided elements

console.log(Array.from([1, 2, 3], x => x * 2)); // Creates a new array by mapping each element to its double

console.log(fruits.findLast(fruit => fruit.startsWith("B"))); // Finds the last element that starts with "B"

console.log(fruits.findLastIndex(fruit => fruit.startsWith("B"))); // Finds the index of the last element that starts with "B"
```

## Objects in JavaScript
Objects in JavaScript are collections of key-value pairs, where each key (also called a property) is a string (or symbol) and each value can be of any data type, including other objects. Objects are used to represent real-world entities and their attributes, making them a fundamental part of JavaScript programming.

## Object Creation

### Syntax Example
```js
const objectName = {
  key1: value1,
  key2: value2,
  // ...
};
```

### Example of Object Creation
```js
const person = {
  name: "Alice",
  age: 30,
  city: "Wonderland"
};
console.log(person.name); // Output: Alice
console.log(person.age); // Output: 30
console.log(person.city); // Output: Wonderland
```

## Properties and Values
In JavaScript, objects consist of properties (keys) and their corresponding values. Properties can be accessed and modified using dot notation or bracket notation.

### Example of Properties and Values
```js
const person = {
  name: "Bob",
  age: 25,
  city: "New York"
};

// Accessing properties using dot notation
console.log(person.name); // Output: Bob
console.log(person["name"]); // Output: Bob
console.log(person["age"]); // Output: 25
console.log(person["city"]); // Output: New York

// Modifying properties
person.age = 26; // Using dot notation
person["city"] = "Los Angeles"; // Using bracket notation
console.log(person.age); // Output: 26
console.log(person.city); // Output: Los Angeles
```

## Methods
In JavaScript, methods are functions that are defined as properties of an object. They allow you to define behavior associated with the object and can be called using dot notation or bracket notation.

### Example of Methods
```js
const person = {
  name: "Charlie",
  age: 28,
  greet: function() { // Method defined as a property
    console.log("Hello, my name is " + this.name);
  }
};

person.greet(); // Output: Hello, my name is Charlie

```

## Accessing Properties
In JavaScript, properties of an object can be accessed using dot notation or bracket notation. Dot notation is more concise and commonly used, while bracket notation is useful when the property name is dynamic or contains special characters.

### Example of Accessing Properties
```js
const person = {
  name: "David",
  age: 32,
  city: "Chicago"
};

// Accessing properties using dot notation
console.log(person.name); // Output: David
console.log(person["name"]); // Output: David
console.log(person["age"]); // Output: 32
console.log(person["city"]); // Output: Chicago
```

## Dot notation
Dot notation is a way to access the properties of an object using a period (`.`) followed by the property name. It is the most common and straightforward method for accessing object properties.

### Example of Dot Notation
```js
const person = {
  name: "Eve",
  age: 29,
  city: "San Francisco"
};

console.log(person.name); // Output: Eve
console.log(person.age); // Output: 29
console.log(person.city); // Output: San Francisco
```

## Bracket notation
Bracket notation is a way to access the properties of an object using square brackets (`[]`) and a string representing the property name. It is useful when the property name is dynamic, contains special characters, or is not a valid identifier.

### Example of Bracket Notation
```js
const person = {
  name: "Frank",
  age: 35,
  city: "Seattle"
};

console.log(person["name"]); // Output: Frank
console.log(person["age"]); // Output: 35
console.log(person["city"]); // Output: Seattle
```

## Adding Properties
You can add new properties to an object in JavaScript using either dot notation or bracket notation. This allows you to dynamically extend the object with additional key-value pairs.

### Example of Adding Properties
```js
const person = {
  name: "Grace",
  age: 27
};

// Adding properties using dot notation
person.city = "Boston";
// Adding properties using bracket notation
person["country"] = "USA";
console.log(person); // Output: { name: "Grace", age: 27, city: "Boston", country: "USA" }
```

## Updating Properties
You can update the values of existing properties in an object using either dot notation or bracket notation.

### Example of Updating Properties
```js
const person = {
  name: "Hannah",
  age: 31,
  city: "Denver"
};

// Updating properties using dot notation
person.age = 32;
// Updating properties using bracket notation
person["city"] = "Austin";
console.log(person); // Output: { name: "Hannah", age: 32, city: "Austin" }
```

## Deleting Properties
You can delete properties from an object in JavaScript using the `delete` operator. This removes the specified property and its value from the object.

### Example of Deleting Properties
```js
const person = {
  name: "Ian",
  age: 29,
  city: "Miami"
};

// Deleting properties using the delete operator
delete person.age; // Removes the 'age' property
console.log(person); // Output: { name: "Ian", city: "Miami" }
```

## Nested Objects
Nested objects are objects that contain other objects as their properties. This allows for the representation of more complex data structures and relationships between entities.

### Example of Nested Objects
```js
const person = {
  name: "Jack",
  age: 34,
  address: {
    street: "123 Main St",
    city: "Los Angeles",
    state: "CA"
  }
};

console.log(person.address.street); // Output: 123 Main St
console.log(person.address.city); // Output: Los Angeles
console.log(person.address.state); // Output: CA
```

## Object destructuring
Object destructuring is a feature in JavaScript that allows you to unpack values from objects into distinct variables. This provides a concise and readable way to extract properties from an object.

### Syntax
```js
const { property1, property2, ...rest } = object;
```

### Example of Object Destructuring
```js
const person = {
  name: "Karen",
  age: 28,
  city: "San Diego"
};
const { name, age, city } = person;
console.log(name); // Output: Karen
console.log(age); // Output: 28
console.log(city); // Output: San Diego
```

## Property Shorthand
Property shorthand is a feature in JavaScript that allows you to create object properties using variable names without explicitly specifying the key-value pairs. When the property name and variable name are the same, you can use shorthand syntax to simplify object creation.

### Example of Property Shorthand
```js
const name = "Liam";
const age = 30;
const person = { name, age }; // Property shorthand
console.log(person); // Output: { name: "Liam", age: 30 }
```

## Computed Property Names
Computed property names allow you to use expressions as property names when creating objects. This feature enables dynamic property names based on variables or expressions, making it easier to create objects with keys that are determined at runtime.

### Syntax
```js
const objectName = {
  [expression]: value,
  // ...
};
```

### Example of Computed Property Names
```js
const key = "dynamicKey";
const object = { [key]: "This is a dynamic property value" }; console.log(object.dynamicKey); // Output: This is a dynamic property value
```

## Method Shorthand
Method shorthand is a feature in JavaScript that allows you to define methods in an object using a more concise syntax. Instead of using the `function` keyword, you can define methods directly within the object literal.

### Example of Method Shorthand
```js
const person = {
  name: "Mia",
  age: 26,
  greet() { // Method shorthand
    console.log("Hello, my name is " + this.name);
  }
};

person.greet(); // Output: Hello, my name is Mia
```

## Object immutability concepts
Object immutability refers to the concept of preventing modifications to objects after they are created. JavaScript provides several methods to achieve object immutability, such as `Object.freeze()`, `Object.seal()`, and using libraries like Immutable.js.

### Example of Object.freeze()
```js
const person = {
  name: "Noah",
  age: 29
};

Object.freeze(person); // Freezes the object, preventing modifications
person.name = "Oliver"; // Attempt to modify the frozen object
console.log(person.name); // Output: Noah (modification is ignored)
```

### Example of Object.seal()
```js
const person = {
  name: "Olivia",
  age: 27
};
Object.seal(person); // Seals the object, preventing new properties from being added
person.city = "New York"; // Attempt to add a new property
console.log(person.city); // Output: undefined (new property is not added)
person.age = 28; // Modifying existing property is allowed
console.log(person.age); // Output: 28 (existing property is modified)
```

## Object Methods
- `Object.keys()`
- `Object.values()`
- `Object.entries()`
- `Object.assign()`
- `Object.create()`
- `Object.freeze()`
- `Object.seal()`
- `Object.is()`
- `Object.hasOwn()`
- `hasOwnProperty()`

### Example of Object Methods
```js
const person = {
  name: "Paul",
  age: 31,
  city: "Houston"
};

console.log(Object.keys(person)); // Output: ["name", "age", "city"] (returns an array of property names)

console.log(Object.values(person)); // Output: ["Paul", 31, "Houston"] (returns an array of property values)

console.log(Object.entries(person)); // Output: [["name", "Paul"], ["age", 31], ["city", "Houston"]] (returns an array of key-value pairs)

const newPerson = Object.assign({}, person, { country: "USA" }); // Merges properties into a new object

console.log(newPerson); // Output: { name: "Paul", age: 31, city: "Houston", country: "USA" }

const anotherPerson = Object.create(person); // Creates a new object with person as its prototype

console.log(anotherPerson.name); // Output: Paul (inherited from the prototype)

const frozenPerson = Object.freeze(person); // Freezes the object, preventing modifications

frozenPerson.age = 32; // Attempt to modify the frozen object

console.log(frozenPerson.age); // Output: 31 (modification is ignored)

const sealedPerson = Object.seal(person); // Seals the object, preventing new properties from being added

sealedPerson.city = "Dallas"; // Attempt to add a new property

console.log(sealedPerson.city); // Output: Houston (new property is not added)

const isSame = Object.is(person, newPerson); // Checks if two objects are the same

console.log(isSame); // Output: false (they are different objects)

const hasOwn = Object.hasOwn(person, "name"); // Checks if the object has the specified property

console.log(hasOwn); // Output: true (the object has the specified property)

const hasOwnProp = person.hasOwnProperty("age"); // Checks if the object has the specified property

console.log(hasOwnProp); // Output: true (the object has the specified property)
```

# Strings in JavaScript
Strings in JavaScript are sequences of characters used to represent text. They can be created using single quotes, double quotes, or backticks (for template literals). Strings are immutable, meaning that once they are created, their values cannot be changed. JavaScript provides a variety of methods for manipulating and working with strings.

## String Creation
There are several ways to create strings in JavaScript:

- Using single quotes:
```js
const singleQuoteString = 'Hello';
```

- Using double quotes:
```js
const doubleQuoteString = "Hello";
```

- Using backticks (template literals):
```js
const templateLiteralString = `Hello`;
```

## String indexing
String characters can be accessed using bracket notation with zero-based indices:

### Example of String Indexing
```js
const str = "Hello";
console.log(str[0]); // Output: H (first character)
console.log(str[1]); // Output: e (second character)
console.log(str[4]); // Output: o (fifth character)
```

## Template Literals
Template literals are a feature in JavaScript that allows for easier string interpolation and multi-line strings. They are created using backticks (`` ` ``) instead of single or double quotes. Template literals support embedded expressions, which can be evaluated and included in the string.

### Example of Template Literals
```js
const name = "Alice";
const greeting = `Hello, ${name}!`; // Using template literals for string interpolation
console.log(greeting); // Output: Hello, Alice!
```

## Escape Characters
Escape characters are special characters in strings that allow you to represent characters that are otherwise difficult to include directly. They are preceded by a backslash (`\`) and can be used to insert special characters, such as newlines, tabs, or quotes, into a string.

### Common Escape Characters
| Escape Character | Description |
|------------------|-------------|
| `\'`             | Single quote |
| `\"`             | Double quote |
| `\\`             | Backslash |
| `\n`             | Newline |
| `\t`             | Tab |
| `\r`             | Carriage return |
| `\b`             | Backspace |

### Example of Escape Characters
```js
const str = "This is a string with a newline character.\nAnd this is the second line.";
console.log(str);

const quote = "He said, \"Hello!\""; // Using escape characters to include double quotes
console.log(quote);

const backslash = "This is a backslash: \\"; // Using escape characters to include a backslash
console.log(backslash);
```

## String Immutability
Strings in JavaScript are immutable, meaning that once a string is created, its value cannot be changed. Any operation that appears to modify a string actually creates a new string. This behavior is important to understand when working with strings, as it can affect performance and memory usage.

### Example of String Immutability
```js
const str = "Hello";
const newStr = str.toUpperCase(); // Creates a new string with uppercase letters
console.log(newStr); // Output: HELLO

console.log(str); // Output: Hello (original string remains unchanged)
```

## String Methods
JavaScript provides a variety of built-in methods for working with strings. These methods allow you to manipulate, transform, and access string values in different ways. Some commonly used string methods include:
| Method | Description |
|--------|-------------|
| `length` | Returns the length of the string |
| `charAt()` | Returns the character at a specified index |
| `includes()` | Checks if the string contains a specified substring |
| `startsWith()` | Checks if the string starts with a specified substring |
| `endsWith()` | Checks if the string ends with a specified substring |
| `indexOf()` | Returns the index of the first occurrence of a specified substring |
| `slice()` | Extracts a section of the string and returns it as a new string |
| `substring()` | Returns a substring between two specified indices |
| `replace()` | Replaces a specified substring with another substring |
| `replaceAll()` | Replaces all occurrences of a specified substring with another substring |
| `split()` | Splits the string into an array of substrings based on a specified separator |
| `trim()` | Removes whitespace from both ends of the string |
| `toUpperCase()` | Converts the string to uppercase |
| `toLowerCase()` | Converts the string to lowercase |

### Example of String Methods
```js
const str = "Hello, World!";
console.log(str.length); // Output: 13 (length of the string)

console.log(str.charAt(0)); // Output: H (character at index 0)

console.log(str.includes("World")); // Output: true (checks if "World" is in the string)

console.log(str.startsWith("Hello")); // Output: true (checks if the string starts with "Hello")

console.log(str.endsWith("!")); // Output: true (checks if the string ends with "!")

console.log(str.indexOf("o")); // Output: 4 (index of the first occurrence of "o")

console.log(str.slice(7, 12)); // Output: World (extracts a section of the string)

console.log(str.substring(7, 12)); // Output: World (returns a substring between two indices)

console.log(str.replace("World", "JavaScript")); // Output: Hello, JavaScript! (replaces "World" with "JavaScript")

console.log(str.replaceAll("o", "0")); // Output: Hell0, W0rld! (replaces all occurrences of "o" with "0")

console.log(str.split(", ")); // Output: ["Hello", "World!"] (splits the string into an array)

console.log(str.trim()); // Output: Hello, World! (removes whitespace from both ends of the string)

console.log(str.toUpperCase()); // Output: HELLO, WORLD! (converts the string to uppercase)

console.log(str.toLowerCase()); // Output: hello, world! (converts the string to lowercase)
```

## String Interpolation
String interpolation is a feature in JavaScript that allows you to embed expressions within string literals. This is typically done using template literals, which are enclosed in backticks (`` ` ``). Interpolation makes it easier to construct strings that include dynamic values.

### Example of String Interpolation
```js
const name = "Alice";
const age = 30;
console.log(`My name is ${name} and I am ${age} years old.`); // Output: My name is Alice and I am 30 years old.
```

# Numbers & Math in JavaScript
Numbers in JavaScript are used to represent both integer and floating-point values. JavaScript provides a variety of built-in methods and properties for performing mathematical operations, as well as the `Math` object, which contains constants and functions for advanced mathematical calculations.

## Number Types
JavaScript has a single number type, which is a double-precision 64-bit binary format IEEE 754 value. This means that all numbers in JavaScript are treated as floating-point values, even if they are whole numbers (integers). However, JavaScript also provides the `BigInt` type for representing integers larger than the maximum safe integer value.

### Example of Number Types
```js
const integer = 42; // Integer
const floatingPoint = 3.14; // Floating-point number
const bigInt = 9007199254740991n; // BigInt (note the 'n' at the end)
console.log(typeof integer); // Output: number
console.log(typeof floatingPoint); // Output: number
console.log(typeof bigInt); // Output: bigint
```

## NaN (Not-a-Number)
`NaN` stands for "Not-a-Number" and represents a value that is not a legal number. It is typically the result of an invalid mathematical operation.

### Example of NaN
```js
const result = "Hello" / 2; // Invalid operation
console.log(result); // Output: NaN
console.log(Number.isNaN(result)); // Output: true (checks if the value is NaN)
```

## Infinity and -Infinity
`Infinity` and `-Infinity` are special numeric values in JavaScript that represent positive and negative infinity, respectively. They can result from mathematical operations that exceed the largest representable number or from division by zero.

### Example of Infinity and -Infinity
```js
const positiveInfinity = 1 / 0; // Division by zero
const negativeInfinity = -1 / 0; // Division by zero with a negative numerator
console.log(positiveInfinity); // Output: Infinity
console.log(negativeInfinity); // Output: -Infinity
```

## Number.isNaN()
The `Number.isNaN()` method is used to determine whether a value is `NaN` (Not-a-Number). It is a more reliable way to check for `NaN` compared to the global `isNaN()` function, as it does not coerce the value to a number before checking.

### Example of Number.isNaN()
```js
const value1 = NaN;
const value2 = "Hello";
console.log(Number.isNaN(value1)); // Output: true (value1 is NaN)
console.log(Number.isNaN(value2)); // Output: false (value2 is not NaN)
```

## Number.isFinite()
The `Number.isFinite()` method is used to determine whether a value is a finite number. It returns `true` if the value is a finite number and `false` if it is `NaN`, `Infinity`, or `-Infinity`. This method does not coerce the value to a number before checking, making it more reliable than the global `isFinite()` function.

### Example of Number.isFinite()
```js
const finiteValue = 42;
const infiniteValue = Infinity;
const notANumber = NaN;
console.log(Number.isFinite(finiteValue)); // Output: true (finiteValue is a finite number)
console.log(Number.isFinite(infiniteValue)); // Output: false (infiniteValue is not finite)
console.log(Number.isFinite(notANumber)); // Output: false (notANumber is not finite)
```

## Number.isInteger()
The `Number.isInteger()` method is used to determine whether a value is an integer. It returns `true` if the value is an integer and `false` if it is not. This method does not coerce the value to a number before checking, making it more reliable than the global `isInteger()` function.

### Example of Number.isInteger()
```js
const integerValue = 42;
const floatingPointValue = 3.14;
console.log(Number.isInteger(integerValue)); // Output: true (integerValue is an integer)
console.log(Number.isInteger(floatingPointValue)); // Output: false (floatingPointValue is not an integer)
```

## parseInt()
The `parseInt()` function in JavaScript is used to convert a string into an integer. It parses the string until it encounters a character that is not a valid digit, and then returns the integer value. The function can also take an optional second argument called the radix, which specifies the base of the numeral system to be used (e.g., base 10 for decimal, base 16 for hexadecimal).

### Syntax
```js
parseInt(string, radix);
```

### Example of parseInt()
```js
const decimalString = "42";
const hexadecimalString = "2A";

console.log(parseInt(decimalString, 10)); // Output: 42 (decimal)
console.log(parseInt(hexadecimalString, 16)); // Output: 42 (hexadecimal)
```

## parseFloat()
The `parseFloat()` function in JavaScript is used to convert a string into a floating-point number. It parses the string until it encounters a character that is not a valid digit or decimal point, and then returns the floating-point value.

### Syntax
```js
parseFloat(string);
```

### Example of parseFloat()
```js
const floatString = "3.14";
console.log(parseFloat(floatString)); // Output: 3.14 (floating-point number)
```

## toFixed()
The `toFixed()` method in JavaScript is used to format a number to a specified number of decimal places and returns the result as a string. It is particularly useful for displaying numbers in a more readable format, especially when dealing with currency or percentages.

### Syntax
```js
number.toFixed(digits);
```

### Example of toFixed()
```js
const num = 3.14159;
console.log(num.toFixed(2)); // Output: "3.14" (formatted to 2 decimal places)
console.log(num.toFixed(4)); // Output: "3.1416" (formatted to 4 decimal places)
console.log(num.toFixed(0)); // Output: "3" (formatted to 0 decimal places)
```

## Math.round()
The `Math.round()` function in JavaScript is used to round a number to the nearest integer. If the fractional part of the number is 0.5 or greater, the argument is rounded to the next higher integer. If the fractional part is less than 0.5, the argument is rounded to the next lower integer.

### Syntax
```js
Math.round(x);
```

### Example of Math.round()
```js
const num1 = 3.2;
const num2 = 3.5;
const num3 = 3.8;
console.log(Math.round(num1)); // Output: 3 (rounded down)
console.log(Math.round(num2)); // Output: 4 (rounded up)
console.log(Math.round(num3)); // Output: 4 (rounded up)
```

## Math.floor()
The `Math.floor()` function in JavaScript is used to round a number down to the nearest integer. It always rounds towards negative infinity, meaning it will return the largest integer less than or equal to the given number.

### Syntax
```js
Math.floor(x);
```

### Example of Math.floor()
```js
const num1 = 3.7;
const num2 = -3.7;
console.log(Math.floor(num1)); // Output: 3 (rounded down)
console.log(Math.floor(num2)); // Output: -4 (rounded down)
```

## Math.ceil()
The `Math.ceil()` function in JavaScript is used to round a number up to the nearest integer. It always rounds towards positive infinity, meaning it will return the smallest integer greater than or equal to the given number.

### Syntax
```js
Math.ceil(x);
```

### Example of Math.ceil()
```js
const num1 = 3.2;
const num2 = -3.2;
console.log(Math.ceil(num1)); // Output: 4 (rounded up)
console.log(Math.ceil(num2)); // Output: -3 (rounded up)
```

## Math.random()
The `Math.random()` function in JavaScript is used to generate a pseudo-random floating-point number between 0 (inclusive) and 1 (exclusive). This means that the generated number can be 0 but will always be less than 1. It is commonly used for generating random values, such as for games, simulations, or random sampling.

### Syntax
```js
Math.random();
```

### Example of Math.random()
```js
const randomNum = Math.random();
console.log(randomNum); // Output: A random number between 0 (inclusive) and 1 (exclusive), e.g., 0.123456789
```

## Math.max() and Math.min()
The `Math.max()` and `Math.min()` functions in JavaScript are used to find the maximum and minimum values from a set of numbers, respectively. They can take any number of arguments and return the largest or smallest value among them.

### Syntax
```js
Math.max(value1, value2, ...);
Math.min(value1, value2, ...);
```

### Example of Math.max() and Math.min()
```js
const maxNum = Math.max(10, 20, 5, 15);
const minNum = Math.min(10, 20, 5, 15);
console.log(maxNum); // Output: 20 (the maximum value)
console.log(minNum); // Output: 5 (the minimum value)
```

## Math.abs()
The `Math.abs()` function in JavaScript is used to return the absolute value of a number. The absolute value of a number is its distance from zero on the number line, regardless of whether it is positive or negative. This means that `Math.abs()` will always return a non-negative number.

### Syntax
```js
Math.abs(x);
```

### Example of Math.abs()
```js
const positiveNum = 5;
const negativeNum = -5;
console.log(Math.abs(positiveNum)); // Output: 5 (absolute value of 5)
console.log(Math.abs(negativeNum)); // Output: 5 (absolute value of -5)
```

## Math.pow()
The `Math.pow()` function in JavaScript is used to calculate the power of a number. It takes two arguments: the base and the exponent, and returns the result of raising the base to the power of the exponent.

### Syntax
```js
Math.pow(base, exponent);
```

### Example of Math.pow()
```js
const base = 2;
const exponent = 3;
console.log(Math.pow(base, exponent)); // Output: 8 (2 raised to the power of 3)
```

## BigInt
The `BigInt` type in JavaScript is used to represent integers that are larger than the maximum safe integer value for the `Number` type. It allows you to work with arbitrarily large integers without losing precision. BigInt values are created by appending an "n" to the end of an integer literal or by using the `BigInt()` constructor.

### Example of BigInt
```js
const bigIntValue = 9007199254740991n; // BigInt literal
const anotherBigInt = BigInt("9007199254740992"); // BigInt using constructor
console.log(bigIntValue); // Output: 9007199254740991n
console.log(anotherBigInt); // Output: 9007199254740992n
```


