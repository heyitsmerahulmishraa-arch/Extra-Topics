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


