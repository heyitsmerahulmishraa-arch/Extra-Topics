# ES6+ Modern JavaScript

## Introduction
ES6, also known as ECMAScript 2015, introduced many new features and improvements to JavaScript, making it more powerful and easier to work with. In this guide, we will explore some of the key features of ES6 and beyond, including arrow functions, template literals, destructuring, classes, modules, and more.

## Let and Const
In ES6, `let` and `const` were introduced as new ways to declare variables
. Unlike `var`, which has function scope, `let` and `const` have block scope, meaning they are only accessible within the block they are defined in.
- `let` allows you to declare variables that can be reassigned.
- `const` allows you to declare variables that cannot be reassigned after their initial assignment.

### Example:
```javascript
let name = 'John';
name = 'Doe'; // This is allowed

const age = 30;
age = 31; // This will throw an error
```

## Arrow Functions
Arrow functions provide a more concise syntax for writing functions in JavaScript. They also have a lexical `this` binding, which means they do not have their own `this` context and instead inherit it from the surrounding code.

### Example:
```javascript
const add = (a, b) => a + b;
console.log(add(2, 3)); // Output: 5
```

## Template Literals
Template literals allow you to create strings that can span multiple lines and include embedded expressions. They are defined using backticks (`` ` ``) instead of single or double quotes.

### Example:
```javascript
const name = 'John';
const greeting = `Hello, ${name}!`;
console.log(greeting); // Output: Hello, John!
```

## Destructuring
Destructuring allows you to unpack values from arrays or properties from objects into distinct variables. This makes it easier to work with complex data structures.

### Example:
```javascript
const person = { name: 'John', age: 30 };
const { name, age } = person;
console.log(name); // Output: John
console.log(age); // Output: 30]

const numbers = [1, 2, 3];
const [first, second] = numbers;
console.log(first); // Output: 1
console.log(second); // Output: 2
```

## Default Parameters
Default parameters allow you to specify default values for function parameters. If no value is provided for a parameter, the default value will be used.

### Example:
```javascript
function greet(name = 'Guest') {
    console.log(`Hello, ${name}!`);
}
greet(); // Output: Hello, Guest!
greet('John'); // Output: Hello, John!
```

## Rest and Spread Operators
The rest operator (`...`) allows you to represent an indefinite number of arguments as an array. The spread operator (`...`) allows you to expand an array or object into individual elements.

### Example:
```javascript
function sum(...numbers) {
    return numbers.reduce((acc, curr) => acc + curr, 0);
}

console.log(sum(1, 2, 3)); // Output: 6

const arr1 = [1, 2, 3];
const arr2 = [...arr1, 4, 5];
console.log(arr2); // Output: [1, 2, 3, 4, 5]
```

## Enhanced Object Literals
ES6 introduced enhanced object literals, which allow you to create objects more concisely. You can define properties and methods without having to repeat the key names.

### Example:
```javascript
const name = 'John';
const person = {
    name,
    greet() {
        console.log(`Hello, ${this.name}!`);
    }
};

person.greet(); // Output: Hello, John!
```

## Classes
ES6 introduced classes as a syntactical sugar over JavaScript's existing prototype-based inheritance. Classes provide a clearer and more concise way to create objects and handle inheritance.

### Example:
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

const john = new Person('John', 30);
john.greet(); // Output: Hello, my name is John and I am 30 years old.
```

## Modules
ES6 introduced a native module system, allowing you to split your code into separate files and import/export functionality between them. This helps in organizing code and managing dependencies.

### Example:
```javascript
// math.js
export function add(a, b) {
    return a + b;
}

// main.js
import { add } from './math.js';

console.log(add(2, 3)); // Output: 5
```

## Promises
Promises are a way to handle asynchronous operations in JavaScript. They represent a value that may be available now, or in the future, or never. Promises have three states: pending, fulfilled, and rejected.

### Example:
```javascript
const fetchData = () => {
    return new Promise((resolve, reject) => {
        setTimeout(() => {
            const data = { name: 'John', age: 30 };
            resolve(data);
        }, 1000);
    });
};

fetchData()
    .then(data => {
        console.log(data); // Output: { name: 'John', age: 30 }
    })
    .catch(error => {
        console.error(error);
    });
```

## `for...of`
The `for...of` loop is a new way to iterate over iterable objects such as arrays, strings, maps, and sets. It provides a simpler syntax compared to traditional loops.

### Example:
```javascript
const numbers = [1, 2, 3, 4, 5];
for (const number of numbers) {
    console.log(number); // Output: 1, 2, 3, 4, 5
}
```

## Symbols
Symbols are a new primitive data type introduced in ES6. They are unique and immutable, making them useful for creating unique property keys in objects.

### Example:
```javascript
const uniqueKey = Symbol('unique');
const obj = { [uniqueKey]: 'This is a unique property';
};
console.log(obj[uniqueKey]); // Output: This is a unique property
```

## Iterators
Iterators are objects that allow you to traverse through a collection of data, such as arrays or strings. They provide a standard way to access elements one at a time.

### Example:
```javascript
const numbers = [1, 2, 3];
const iterator = numbers[Symbol.iterator]();
console.log(iterator.next().value); // Output: 1
console.log(iterator.next().value); // Output: 2
console.log(iterator.next().value); // Output: 3
console.log(iterator.next().done); // Output: true
```

## Generators
Generators are special functions that can be paused and resumed, allowing you to control the flow of execution. They are defined using the `function*` syntax and use the `yield` keyword to produce values.

### Example:
```javascript
function* generateNumbers() {
    yield 1;
    yield 2;
    yield 3;
}

const generator = generateNumbers();
console.log(generator.next().value); // Output: 1
console.log(generator.next().value); // Output: 2
console.log(generator.next().value); // Output: 3
console.log(generator.next().done); // Output: true
```

## Map and Set
ES6 introduced two new data structures: `Map` and `Set`. A `Map` is a collection of key-value pairs, while a `Set` is a collection of unique values.

### Example:
```javascript
const map = new Map();
map.set('name', 'John');
map.set('age', 30);
console.log(map.get('name')); // Output: John
const set = new Set();
set.add(1);
set.add(2);
set.add(2); // Duplicate values are ignored
console.log(set.has(2)); // Output: true
```

## WeakMap and WeakSet
WeakMap and WeakSet are similar to Map and Set, but they allow for the garbage collection of keys or values that are no longer referenced elsewhere in the code. This makes them useful for managing memory in certain scenarios.

### Example:
```javascript
const weakMap = new WeakMap();
let obj = {};
weakMap.set(obj, 'This is a weak map value');
console.log(weakMap.get(obj)); // Output: This is a weak map value
obj = null; // The object is no longer referenced
// The value in the weakMap will be garbage collected
const weakSet = new WeakSet();
let obj2 = {};
weakSet.add(obj2);
console.log(weakSet.has(obj2)); // Output: true
obj2 = null; // The object is no longer referenced
// The value in the weakSet will be garbage collected
```

## Optional Chaining
Optional chaining (`?.`) is a feature that allows you to safely access deeply nested properties of an object without having to check for the existence of each property in the chain. If any part of the chain is `null` or `undefined`, the expression short-circuits and returns `undefined`.

### Example:
```javascript
const user = {
    name: 'John',
    address: {
        city: 'New York',
        zip: '10001'
    }
};

console.log(user.address?.city); // Output: New York
console.log(user.contact?.phone); // Output: undefined
```

## Nullish Coalescing Operator
The nullish coalescing operator (`??`) is used to provide a default value when dealing with `null` or `undefined`. It returns the right-hand operand when the left-hand operand is `null` or `undefined`, otherwise it returns the left-hand operand.

### Example:
```javascript
const value = null;
const result = value ?? 'Default Value';
console.log(result); // Output: Default Value
const anotherValue = 0;
const anotherResult = anotherValue ?? 'Default Value';
console.log(anotherResult); // Output: 0
```

## Logical Assignment Operators
Logical assignment operators combine logical operations with assignment. They provide a shorthand way to assign values based on certain conditions.

### Example:
```javascript
let a = true;
a &&= false; // Equivalent to: if (a) { a = false; }
console.log(a); // Output: false

let b = null;
b ||= 'Default'; // Equivalent to: if (!b) { b = 'Default'; }
console.log(b); // Output: Default
```

## Numeric Separators
Numeric separators (`_`) allow you to improve the readability of large numbers by separating groups of digits. They do not affect the actual value of the number.

### Example:
```javascript
const largeNumber = 1_000_000; // One million
console.log(largeNumber); // Output: 1000000

const binaryNumber = 0b1010_1010; // Binary representation
console.log(binaryNumber); // Output: 170
```

## Private class Fields
Private class fields allow you to define properties in a class that are only accessible within the class itself. They are defined using the `#` prefix.

### Example:
```javascript
class Person {
    #name; // Private field

    constructor(name) {
        this.#name = name;
    }

    greet() {
        console.log(`Hello, my name is ${this.#name}.`);
    }
}

const john = new Person('John');
john.greet(); // Output: Hello, my name is John.

// john.#name; // This will throw an error: Private field '#name' must be declared in an enclosing class
```

## Static class fields
Static class fields allow you to define properties that belong to the class itself rather than to instances of the class. They are defined using the `static` keyword.

### Example:
```javascript
class MathUtils {
    static PI = 3.14159; // Static field

    static calculateCircumference(radius) {
        return 2 * MathUtils.PI * radius;
    }
}

console.log(MathUtils.PI); // Output: 3.14159
console.log(MathUtils.calculateCircumference(5)); // Output: 31.4159
```

## Promise.all()
The `Promise.all()` method takes an array of promises and returns a single promise that resolves when all of the promises in the array have resolved, or rejects if any of the promises reject. This is useful for running multiple asynchronous operations in parallel and waiting for all of them to complete.

### Example:
```javascript
const promise1 = Promise.resolve(3);
const promise2 = new Promise((resolve, reject) => {
    setTimeout(resolve, 1000, 'foo');
});

Promise.all([promise1, promise2]).then(values => {
    console.log(values); // Output: [3, 'foo']
}).catch(error => {
    console.error(error);
});
```

## Promise.allSettled()
The `Promise.allSettled()` method takes an array of promises and returns a single promise that resolves when all of the promises in the array have settled (either fulfilled or rejected). It provides an array of objects that describe the outcome of each promise.

### Example:
```javascript
const promise1 = Promise.resolve(3);
const promise2 = new Promise((resolve, reject) => {
    setTimeout(reject, 1000, 'error');
});

Promise.allSettled([promise1, promise2]).then(results => {
    console.log(results);
    // Output: [
    //   { status: 'fulfilled', value: 3 },
    //   { status: 'rejected', reason: 'error' }
    // ]
});
```

## Promise.race()
The `Promise.race()` method takes an array of promises and returns a single promise that resolves or rejects as soon as one of the promises in the array resolves or rejects. This is useful for scenarios where you want to proceed with the first completed promise.

### Example:
```javascript
const promise1 = new Promise((resolve, reject) => {
    setTimeout(resolve, 500, 'first');
});

const promise2 = new Promise((resolve, reject) => {
    setTimeout(resolve, 1000, 'second');
});

Promise.race([promise1, promise2]).then(value => {
    console.log(value); // Output: 'first'
}).catch(error => {
    console.error(error);
});
```

## Promise.any()
The `Promise.any()` method takes an array of promises and returns a single promise that resolves as soon as any of the promises in the array resolves. If all promises reject, it returns an `AggregateError` containing all rejection reasons.

### Example:
```javascript
const promise1 = Promise.reject('error1');
const promise2 = new Promise((resolve, reject) => {
    setTimeout(resolve, 1000, 'success');
});

Promise.any([promise1, promise2]).then(value => {
    console.log(value); // Output: 'success'
}).catch(error => {
    console.error(error);
});
```

## String.raw()
The `String.raw()` method is a tag function of template literals that allows you to get the raw string form of a template literal, preserving backslashes and other escape sequences. It is useful for creating strings that contain special characters without interpreting them.

### Example:
```javascript
const rawString = String.raw`This is a raw string with a newline character: \n and a tab character: \t.`;
console.log(rawString);
// Output: This is a raw string with a newline character: \n and a tab character: \t.
```

## Modern array methods
ES6 introduced several new array methods that make it easier to work with arrays. Some of the most commonly used methods include `find()`, `findIndex()`, `includes()`, `flat()`, and `flatMap()`.

### Example:
```javascript
const numbers = [1, 2, 3, 4, 5];
const found = numbers.find(num => num > 3);
console.log(found); // Output: 4

const index = numbers.findIndex(num => num === 3);
console.log(index); // Output: 2

const includesThree = numbers.includes(3);
console.log(includesThree); // Output: true

const nestedArray = [1, [2, 3], [4, [5]]];
const flatArray = nestedArray.flat(2);
console.log(flatArray); // Output: [1, 2, 3, 4, 5]

const flatMappedArray = nestedArray.flatMap(num => (Array.isArray(num) ? num : [num]));
console.log(flatMappedArray); // Output: [1, 2, 3, 4, [5]]
```

# DOM Manipulation

## What is the DOM?
The Document Object Model (DOM) is a programming interface for web documents. It represents the structure of a document as a tree of objects, allowing developers to manipulate the content, structure, and style of web pages dynamically using JavaScript.

## DOM tree
The DOM tree is a hierarchical representation of the elements in an HTML document. Each element, attribute, and piece of text in the document is represented as a node in the tree. The root of the tree is the `document` object, which contains all other nodes.

## document
The `document` object is the entry point to the DOM and provides methods and properties to access and manipulate the elements of a web page. It represents the entire HTML document and allows you to interact with its content.

### Example:
```javascript
console.log(document.title); // Output: The title of the document
console.log(document.body); // Output: The body element of the document
```

## getElementById()
The `getElementById()` method is used to select an element from the DOM by its unique `id` attribute. It returns the first element with the specified `id`, or `null` if no such element exists.

### Example:
```javascript
const element = document.getElementById('myElement');
console.log(element); // Output: The element with id 'myElement'
```

## querySelector()
The `querySelector()` method allows you to select the first element that matches a specified CSS selector. It is a versatile method that can be used to select elements by class, id, tag name, or any valid CSS selector.

### Example:
```javascript
const element = document.querySelector('.myClass');
console.log(element); // Output: The first element with class 'myClass'
```

## querySelectorAll()
The `querySelectorAll()` method returns a static NodeList of all elements that match a specified CSS selector. Unlike `querySelector()`, which returns only the first matching element, `querySelectorAll()` allows you to select multiple elements.

### Example:
```javascript
const elements = document.querySelectorAll('p');
elements.forEach(element => {
    console.log(element); // Output: Each <p> element in the document
});
```

## Creating Elements
You can create new elements in the DOM using the `document.createElement()` method. This method takes the tag name of the element you want to create as an argument and returns a new element node.

### Example:
```javascript
const newDiv = document.createElement('div');
newDiv.textContent = 'Hello, World!';
document.body.appendChild(newDiv); // Adds the new div to the body of the document
```

## Removing Elements
You can remove elements from the DOM using the `remove()` method or by using the `removeChild()` method on the parent element. The `remove()` method is called directly on the element you want to remove, while `removeChild()` is called on the parent node.

### Example:
```javascript
const elementToRemove = document.getElementById('myElement');
// Using remove()
elementToRemove.remove();
// Using removeChild()
const parentElement = document.getElementById('parentElement');
parentElement.removeChild(elementToRemove);
```

## Appending Elements
You can append new elements to the DOM using the `appendChild()` method or the `append()` method. The `appendChild()` method adds a node as the last child of a specified parent node, while the `append()` method can add multiple nodes or strings.

### Example:
```javascript
const newParagraph = document.createElement('p');
newParagraph.textContent = 'This is a new paragraph.';
// Using appendChild()
document.body.appendChild(newParagraph);
// Using append()
const newSpan = document.createElement('span');
newSpan.textContent = 'This is a new span.';
document.body.append(newParagraph, newSpan);
```

## append()
The `append()` method allows you to insert multiple nodes or strings into a parent element. It can take one or more arguments and appends them as the last children of the specified parent node. Unlike `appendChild()`, it can also append text nodes directly.

### Example:
```javascript
const newDiv = document.createElement('div');
newDiv.textContent = 'This is a new div.';
document.body.append(newDiv, ' This is a text node.');
```

## prepend()
The `prepend()` method allows you to insert one or more nodes or strings at the beginning of a parent element. It can take one or more arguments and prepends them as the first children of the specified parent node.

### Example:
```javascript
const newDiv = document.createElement('div');
newDiv.textContent = 'This is a new div.';
document.body.prepend(newDiv, ' This is a text node.');
```

## before()
The `before()` method allows you to insert one or more nodes or strings before a specified element in the DOM. It can take one or more arguments and inserts them as siblings before the target element.

### Example:
```javascript
const targetElement = document.getElementById('targetElement');
const newDiv = document.createElement('div');
newDiv.textContent = 'This is a new div.';
targetElement.before(newDiv, ' This is a text node.');
```

## after()
The `after()` method allows you to insert one or more nodes or strings after a specified element in the DOM. It can take one or more arguments and inserts them as siblings after the target element.

### Example:
```javascript
const targetElement = document.getElementById('targetElement');
const newDiv = document.createElement('div');
newDiv.textContent = 'This is a new div.';
targetElement.after(newDiv, ' This is a text node.');
```

## innerHTML
The `innerHTML` property allows you to get or set the HTML content of an element. When you set `innerHTML`, it replaces the existing content of the element with the new HTML string provided.

### Example:
```javascript
const element = document.getElementById('myElement');
element.innerHTML = '<p>This is a new paragraph.</p>'; // Sets the inner HTML of the element
```

## textContent
The `textContent` property allows you to get or set the text content of an element. Unlike `innerHTML`, it does not parse HTML tags and treats the content as plain text.

### Example:
```javascript
const element = document.getElementById('myElement');
element.textContent = 'This is plain text content.'; // Sets the text content of the element
```

## innerText
The `innerText` property allows you to get or set the visible text content of an element. It takes into account the CSS styles applied to the element, such as `display: none`, and only returns the text that is visible to the user.

### Example:
```javascript
const element = document.getElementById('myElement');
element.innerText = 'This is visible text content.'; // Sets the visible text content of the element
```

## Attributes
Attributes are additional information provided to HTML elements that define their properties or behavior. You can get, set, or remove attributes of an element using JavaScript.

### Example:
```javascript
const element = document.getElementById('myElement');
// Get an attribute
const id = element.getAttribute('id');
console.log(id); // Output: myElement
// Set an attribute
element.setAttribute('data-custom', 'customValue');
// Remove an attribute
element.removeAttribute('data-custom');
```

## classList
The `classList` property provides a convenient way to access and manipulate the classes of an element. It returns a DOMTokenList, which has methods to add, remove, toggle, and check for classes.

### Example:
```javascript
const element = document.getElementById('myElement');
// Add a class
element.classList.add('newClass');
// Remove a class
element.classList.remove('oldClass');
// Toggle a class
element.classList.toggle('activeClass');
// Check if an element has a class
const hasClass = element.classList.contains('newClass');
console.log(hasClass); // Output: true
```

## style
The `style` property allows you to get or set the inline styles of an element. You can access individual CSS properties using camelCase notation.

### Example:
```javascript
const element = document.getElementById('myElement');
// Set inline styles
element.style.backgroundColor = 'blue';
element.style.fontSize = '16px';
// Get inline styles
const bgColor = element.style.backgroundColor;
console.log(bgColor); // Output: blue
```

## DOM traversal
DOM traversal refers to the process of navigating through the nodes of the DOM tree. You can access parent, child, and sibling elements using various properties and methods.

### Example:
```javascript
const element = document.getElementById('myElement');
// Access parent element
const parent = element.parentElement;
console.log(parent); // Output: The parent element of 'myElement'

// Access child elements
const children = element.children;

console.log(children); // Output: HTMLCollection of child elements
// Access next sibling element
const nextSibling = element.nextElementSibling;
console.log(nextSibling); // Output: The next sibling element of 'myElement'
// Access previous sibling element
const previousSibling = element.previousElementSibling;
console.log(previousSibling); // Output: The previous sibling element of 'myElement'
```

## Parent child relationships
In the DOM, elements have parent-child relationships that define the structure of the document. Each element can have one parent element and multiple child elements. You can navigate these relationships using properties like `parentElement`, `children`, `firstElementChild`, and `lastElementChild`.

### Example:
```javascript
const parentElement = document.getElementById('parentElement');
const firstChild = parentElement.firstElementChild;
console.log(firstChild); // Output: The first child element of 'parentElement'
const lastChild = parentElement.lastElementChild;
console.log(lastChild); // Output: The last child element of 'parentElement'
```

## Siblings
Siblings are elements that share the same parent in the DOM tree. You can access sibling elements using properties like `nextElementSibling` and `previousElementSibling`.

### Example:
```javascript
const element = document.getElementById('myElement');
const nextSibling = element.nextElementSibling;

console.log(nextSibling); // Output: The next sibling element of 'myElement'
const previousSibling = element.previousElementSibling;
console.log(previousSibling); // Output: The previous sibling element of 'myElement'
```

## Creating dynamic UI
Creating a dynamic user interface (UI) involves manipulating the DOM to add, remove, or update elements based on user interactions or data changes. This can be achieved using JavaScript to respond to events and modify the content of the web page in real-time.

### Example:
```javascript
const button = document.getElementById('addButton');
button.addEventListener('click', () => {
    const newItem = document.createElement('li');
    newItem.textContent = 'New Item';
    const list = document.getElementById('itemList');
    list.appendChild(newItem);
});
```

# Events

## What are events?
Events are actions or occurrences that happen in the browser, such as user interactions (clicks, key presses, mouse movements), changes to the DOM, or other system-generated events. JavaScript allows you to listen for these events and respond to them by executing specific functions, enabling dynamic and interactive web applications.

## Event listeners
Event listeners are functions that wait for specific events to occur on a particular element. You can attach an event listener to an element using the `addEventListener()` method, which takes the event type and a callback function as arguments.

### Example:
```javascript
const button = document.getElementById('myButton');
button.addEventListener('click', () => {
    console.log('Button was clicked!');
});
```

## addEventListener()
The `addEventListener()` method is used to attach an event handler to a specified element. It allows you to listen for various types of events, such as clicks, key presses, mouse movements, and more. You can also specify whether the event should be captured during the capturing phase or the bubbling phase.

### Example:
```javascript
const button = document.getElementById('myButton');
button.addEventListener('click', () => {
    console.log('Button was clicked!');
});
```

## Click events
Click events are triggered when a user clicks on an element, such as a button or a link. You can listen for click events using the `click` event type in the `addEventListener()` method.

### Example:
```javascript
const button = document.getElementById('myButton');
button.addEventListener('click', () => {
    console.log('Button was clicked!');
});
```

## Input events
Input events are triggered when the value of an input element changes. This can occur when a user types into a text field, selects an option from a dropdown, or interacts with other form elements. You can listen for input events using the `input` event type in the `addEventListener()` method.

### Example:
```javascript
const inputField = document.getElementById('myInput');
inputField.addEventListener('input', (event) => {
    console.log(`Input value changed to: ${event.target.value}`);
});
```

## Change events
Change events are triggered when the value of an input element changes and the element loses focus. This is commonly used for form elements like text fields, checkboxes, and select dropdowns. You can listen for change events using the `change` event type in the `addEventListener()` method.

### Example:
```javascript
const selectElement = document.getElementById('mySelect');
selectElement.addEventListener('change', (event) => {
    console.log(`Selected value changed to: ${event.target.value}`);
});
```

## Submit events
Submit events are triggered when a form is submitted. You can listen for submit events using the `submit` event type in the `addEventListener()` method. It's common to prevent the default form submission behavior to handle the data with JavaScript instead.

### Example:
```javascript
const form = document.getElementById('myForm');
form.addEventListener('submit', (event) => {
    event.preventDefault(); // Prevent the default form submission
    const formData = new FormData(form);
    console.log(`Form submitted with data: ${formData.get('inputName')}`);
});
```

## Keyboard events
Keyboard events are triggered when a user interacts with the keyboard, such as pressing or releasing keys. The most common keyboard events are `keydown`, `keyup`, and `keypress`. You can listen for these events using the `addEventListener()` method.

### Example:
```javascript
const inputField = document.getElementById('myInput');
inputField.addEventListener('keydown', (event) => {
    console.log(`Key pressed: ${event.key}`);
});
```

## Mouse events
Mouse events are triggered by user interactions with the mouse, such as clicking, moving, or hovering over elements. Common mouse events include `click`, `dblclick`, `mousemove`, `mouseover`, and `mouseout`. You can listen for these events using the `addEventListener()` method.

### Example:
```javascript
const button = document.getElementById('myButton');
button.addEventListener('mouseover', () => {
    console.log('Mouse is over the button!');
});
```

## Touch events
Touch events are triggered by user interactions on touch-enabled devices, such as smartphones and tablets. Common touch events include `touchstart`, `touchmove`, `touchend`, and `touchcancel`. You can listen for these events using the `addEventListener()` method.

### Example:
```javascript
const touchArea = document.getElementById('myTouchArea');
touchArea.addEventListener('touchstart', (event) => {
    console.log('Touch started!');
});
```

## Focus and blur events
Focus and blur events are triggered when an element gains or loses focus, respectively. These events are commonly used with form elements like input fields and textareas. You can listen for these events using the `addEventListener()` method.

### Example:
```javascript
const inputField = document.getElementById('myInput');
inputField.addEventListener('focus', () => {
    console.log('Input field is focused!');
});

inputField.addEventListener('blur', () => {
    console.log('Input field lost focus!');
});
```

## Event object

When an event occurs, an event object is created and passed to the event handler function. This object contains information about the event, such as the type of event, the target element, and other relevant properties. You can access the event object by including a parameter in your event handler function.

### Example:
```javascript
const button = document.getElementById('myButton');
button.addEventListener('click', (event) => {
    console.log(`Event type: ${event.type}`); // Output: Event type: click
    console.log(`Target element: ${event.target.id}`); // Output: Target element: myButton
});
```

## Event bubbling and capturing
When an event occurs in the DOM, it can propagate through the hierarchy of elements in two phases: capturing and bubbling. In the capturing phase, the event starts from the root of the DOM tree and travels down to the target element. In the bubbling phase, the event starts from the target element and travels back up to the root. You can control which phase to listen for by passing a third argument to `addEventListener()`.

### Example:
```javascript
const parentElement = document.getElementById('parent');
const childElement = document.getElementById('child');
parentElement.addEventListener('click', () => {
    console.log('Parent element clicked!');
}, true); // Capturing phase

childElement.addEventListener('click', () => {
    console.log('Child element clicked!');
}, false); // Bubbling phase
```

## Event propagation
Event propagation refers to the way events travel through the DOM tree. When an event occurs, it can propagate in two phases: capturing and bubbling. In the capturing phase, the event travels from the root of the DOM tree down to the target element. In the bubbling phase, the event travels from the target element back up to the root. You can control event propagation using methods like `stopPropagation()` and `stopImmediatePropagation()`.

### Example:
```javascript
const parentElement = document.getElementById('parent');
const childElement = document.getElementById('child');

parentElement.addEventListener('click', (event) => {
    console.log('Parent element clicked!');
    event.stopPropagation(); // Stops the event from propagating further
});

childElement.addEventListener('click', () => {
    console.log('Child element clicked!');
});
```

## stopPropagation()
The `stopPropagation()` method is used to prevent an event from propagating further through the DOM tree. When called within an event handler, it stops the event from reaching any other event listeners that may be attached to parent or child elements. This is useful when you want to handle an event at a specific level without triggering other handlers.

### Example:
```javascript
const parentElement = document.getElementById('parent');
const childElement = document.getElementById('child');

parentElement.addEventListener('click', (event) => {
    console.log('Parent element clicked!');
    event.stopPropagation(); // Stops the event from propagating further
});

childElement.addEventListener('click', () => {
    console.log('Child element clicked!');
});
```

## preventDefault()
The `preventDefault()` method is used to prevent the default action associated with an event from occurring. For example, it can be used to prevent a form from submitting when the submit button is clicked or to prevent a link from navigating to a new page. This method is commonly used in event handlers to customize the behavior of elements.

### Example:
```javascript
const form = document.getElementById('myForm');
form.addEventListener('submit', (event) => {
    event.preventDefault(); // Prevents the default form submission
    console.log('Form submission prevented!');
});
```

## Event delegation
Event delegation is a technique in JavaScript where you attach a single event listener to a parent element to handle events for its child elements. This approach takes advantage of event bubbling, allowing you to manage events more efficiently, especially when dealing with dynamically added elements.

### Example:
```javascript
const list = document.getElementById('myList');
list.addEventListener('click', (event) => {
    if (event.target && event.target.nodeName === 'LI') {
        console.log(`List item clicked: ${event.target.textContent}`);
    }
});
```

## Custom events
Custom events allow you to create and dispatch your own events in JavaScript. This is useful for creating more complex interactions and communication between different parts of your application. You can create a custom event using the `CustomEvent` constructor and dispatch it using the `dispatchEvent()` method.

### Example:
```javascript
const myEvent = new CustomEvent('myCustomEvent', { detail: { message: 'Hello, World!' } });

const element = document.getElementById('myElement');
element.addEventListener('myCustomEvent', (event) => {
    console.log(event.detail.message); // Output: Hello, World!
});

element.dispatchEvent(myEvent); // Dispatches the custom event
```

# Browser APIs

## window
The `window` object represents the browser's window and provides methods and properties to interact with the browser environment. It serves as the global object in a web page, allowing you to access various browser features, such as opening new windows, managing timers, and handling events.

### Example:
```javascript
console.log(window.innerWidth); // Output: The width of the browser window
console.log(window.innerHeight); // Output: The height of the browser window
console.log(window.location.href); // Output: The current URL of the page
```

## document
The `document` object is a property of the `window` object and represents the HTML document loaded in the browser. It provides methods and properties to access and manipulate the content, structure, and style of the web page. You can use the `document` object to select elements, create new elements, and handle events.

### Example:
```javascript
const title = document.title; // Get the title of the document
console.log(title); // Output: The title of the document
const body = document.body; // Get the body element of the document
console.log(body); // Output: The body element of the document
console.log(document.getElementById('myElement')); // Output: The element with id 'myElement'
```

## navigator
The `navigator` object provides information about the browser and the user's environment. It contains properties and methods that allow you to access details such as the browser name, version, platform, and user agent string. The `navigator` object is useful for detecting the user's browser and making decisions based on that information.

### Example:
```javascript
console.log(navigator.userAgent); // Output: The user agent string of the browser
console.log(navigator.platform); // Output: The platform of the user's device
console.log(navigator.language); // Output: The preferred language of the user
```

## location
The `location` object provides information about the current URL of the document and allows you to manipulate it. It contains properties and methods that enable you to get the current URL, navigate to a new URL, reload the page, and more. The `location` object is useful for managing navigation and handling URL changes in your web application.

### Example:
```javascript
console.log(location.href); // Output: The current URL of the page
location.href = 'https://www.example.com'; // Navigate to a new URL

console.log(location.pathname); // Output: The path of the current URL
console.log(location.search); // Output: The query string of the current URL
location.reload(); // Reload the current page
location.replace('https://www.example.com'); // Replace the current URL with a new one
```

## history
The `history` object provides access to the browser's session history, allowing you to navigate back and forth through the pages visited in the current session. It contains methods that enable you to manipulate the history stack, such as moving backward or forward, and adding new entries.

### Example:
```javascript
console.log(history.length); // Output: The number of entries in the session history
history.back(); // Navigate to the previous page in the history
history.forward(); // Navigate to the next page in the history
history.go(-1); // Navigate to the previous page (same as history.back())
history.pushState({ page: 1 }, 'Title 1', '?page=1');
history.replaceState({ page: 2 }, 'Title 2', '?page=2'); // Replace the current history entry
```

## screen
The `screen` object provides information about the user's screen, such as its dimensions and color depth. It contains properties that allow you to access details about the screen's width, height, available width and height, and color depth. The `screen` object is useful for creating responsive designs and adapting your web application to different screen sizes.

### Example:
```javascript
console.log(screen.width); // Output: The width of the user's screen
console.log(screen.height); // Output: The height of the user's screen
console.log(screen.availWidth); // Output: The available width of the user's screen
console.log(screen.availHeight); // Output: The available height of the user's screen
console.log(screen.colorDepth); // Output: The color depth of the user's screen
```

## localStorage
The `localStorage` object provides a way to store key-value pairs in the browser that persist even after the browser is closed. It allows you to save data on the client side and retrieve it later, making it useful for storing user preferences, session data, and other information that needs to be retained across page reloads.

### Example:
```javascript
localStorage.setItem('username', 'JohnDoe'); // Store a value
const username = localStorage.getItem('username'); // Retrieve the value

console.log(username); // Output: JohnDoe
localStorage.removeItem('username'); // Remove the value

localStorage.clear(); // Clear all stored values
```

## sessionStorage
The `sessionStorage` object provides a way to store key-value pairs in the browser that persist only for the duration of the page session. Unlike `localStorage`, which retains data even after the browser is closed, `sessionStorage` data is cleared when the page session ends (e.g., when the browser tab is closed). It is useful for storing temporary data that should not persist across sessions.

### Example:
```javascript
sessionStorage.setItem('sessionKey', 'sessionValue'); // Store a value
const sessionValue = sessionStorage.getItem('sessionKey'); // Retrieve the value
console.log(sessionValue); // Output: sessionValue
sessionStorage.removeItem('sessionKey'); // Remove the value
sessionStorage.clear(); // Clear all stored values
sessionStorage.setItem('tempData', 'This is temporary data.'); // Store temporary data
console.log(sessionStorage.getItem('tempData')); // Output: This is temporary data.
```

## Cookies
The `document.cookie` property allows you to create, read, and delete cookies in the browser. Cookies are small pieces of data stored on the client side that can be used for various purposes, such as session management, user preferences, and tracking. You can set cookies with specific attributes like expiration date, path, and domain.

### Example:
```javascript
// Set a cookie
document.cookie = "username=JohnDoe; expires=Fri, 31 Dec 2024 23:59:59 GMT; path=/";
// Read cookies
console.log(document.cookie); // Output: username=JohnDoe
// Delete a cookie by setting its expiration date to a past date
document.cookie = "username=; expires=Thu, 01 Jan 1970 00:00:00 GMT; path=/";
```

## Clipboard API
The Clipboard API provides a way to interact with the system clipboard, allowing you to read from and write to the clipboard. This is useful for implementing copy and paste functionality in web applications. The Clipboard API includes methods like `writeText()` and `readText()` for handling text data.

### Example:
```javascript
const copyButton = document.getElementById('copyButton');
copyButton.addEventListener('click', async () => {
    try {
        await navigator.clipboard.writeText('Hello, World!');
        console.log('Text copied to clipboard!');
    } catch (err) {
        console.error('Failed to copy text: ', err);
    }
});

const pasteButton = document.getElementById('pasteButton');
pasteButton.addEventListener('click', async () => {
    try {
        const text = await navigator.clipboard.readText();
        console.log('Text pasted from clipboard: ', text);
    } catch (err) {
        console.error('Failed to read text from clipboard: ', err);
    }
});
```

## Geolocation API
The Geolocation API allows web applications to access the geographical location of a user's device. It provides methods to retrieve the current position, watch for changes in position, and handle errors. The API can be used for location-based services, mapping applications, and other features that require location information.

### Example:
```javascript
if (navigator.geolocation) {
    navigator.geolocation.getCurrentPosition(
        (position) => {
            console.log(`Latitude: ${position.coords.latitude}, Longitude: ${position.coords.longitude}`);
        },
        (error) => {
            console.error('Error getting location: ', error);
        }
    );
} else {
    console.error('Geolocation is not supported by this browser.');
}
```

## Notification API
The Notification API allows web applications to display notifications to the user, even when the web page is not in focus. This can be useful for alerting users about important events, updates, or messages. To use the Notification API, you need to request permission from the user and then create and display notifications.

### Example:
```javascript
if ('Notification' in window) {
    Notification.requestPermission().then((permission) => {
        if (permission === 'granted') {
            const notification = new Notification('Hello!', {
                body: 'This is a notification from your web application.',
                icon: 'icon.png'
            });
        }
    });
} else {
    console.error('Notifications are not supported by this browser.');
}
```

## Web Workers
The Web Workers API allows you to run JavaScript code in the background, separate from the main execution thread of a web page. This enables you to perform computationally intensive tasks without blocking the user interface, improving the responsiveness of your web application. Web Workers communicate with the main thread using messages.

### Example:
```javascript
// main.js
const worker = new Worker('worker.js');

worker.postMessage('Hello, Worker!');

worker.onmessage = (event) => {
    console.log(`Message from worker: ${event.data}`);
};

// worker.js
self.onmessage = (event) => {
    console.log(`Message from main thread: ${event.data}`);
    self.postMessage('Hello, Main Thread!');
};
```

## Intersection Observer
The Intersection Observer API provides a way to asynchronously observe changes in the intersection of a target element with an ancestor element or the viewport. It is useful for implementing features like lazy loading images, infinite scrolling, and triggering animations when elements come into view.

### Example:
```javascript
const target = document.getElementById('targetElement');
const observer = new IntersectionObserver((entries, observer) => {
    entries.forEach(entry => {
        if (entry.isIntersecting) {
            console.log('Target element is in view!');
            observer.unobserve(entry.target); // Stop observing after the first intersection
        }
    });
}, { threshold: 0.5 }); // Trigger when 50% of the target is visible

observer.observe(target);
```

## Mutation Observer
The Mutation Observer API provides a way to watch for changes in the DOM tree. It allows you to observe modifications to elements, attributes, and text content, enabling you to respond to dynamic changes in the document. This is useful for implementing features like live updates, monitoring user interactions, and reacting to changes in the DOM.

### Example:
```javascript
const targetNode = document.getElementById('targetElement');
const observer = new MutationObserver((mutationsList, observer) => {
    for (const mutation of mutationsList) {
        if (mutation.type === 'childList') {
            console.log('A child node has been added or removed.');
        } else if (mutation.type === 'attributes') {
            console.log(`The ${mutation.attributeName} attribute was modified.`);
        }
    }
});

observer.observe(targetNode, { attributes: true, childList: true, subtree: true });
```

## Resize Observer
The Resize Observer API provides a way to observe changes in the size of an element. It allows you to monitor when an element's dimensions change, enabling you to respond to layout changes and implement responsive designs. This is useful for adjusting content, triggering animations, or updating UI elements based on size changes.

### Example:
```javascript
const targetElement = document.getElementById('targetElement');
const resizeObserver = new ResizeObserver((entries) => {
    for (const entry of entries) {
        console.log(`Element resized: ${entry.contentRect.width}x${entry.contentRect.height}`);
    }
});

resizeObserver.observe(targetElement);
```

## requestAnimationFrame()
The `requestAnimationFrame()` method is used to schedule a function to be called before the next repaint of the browser. It is commonly used for creating smooth animations and improving performance by synchronizing updates with the browser's refresh rate. This method provides a more efficient way to perform animations compared to using `setTimeout()` or `setInterval()`.

### Example:
```javascript
let start = null;
function step(timestamp) {
    if (!start) start = timestamp;
    const progress = timestamp - start;
    const element = document.getElementById('animatedElement');
    element.style.transform = `translateX(${Math.min(progress / 10, 200)}px)`;
    if (progress < 2000) { // Stop after 2 seconds
        requestAnimationFrame(step);
    }
}

requestAnimationFrame(step);
```

## setTimeout() and setInterval()
The `setTimeout()` and `setInterval()` methods are used to schedule the execution of functions after a specified delay or at regular intervals, respectively. `setTimeout()` executes a function once after the specified delay, while `setInterval()` repeatedly executes a function at the specified interval until it is cleared.

### Example:
```javascript
// setTimeout example
setTimeout(() => {
    console.log('This message is displayed after 2 seconds.');
}, 2000);

// setInterval example
const intervalId = setInterval(() => {
    console.log('This message is displayed every 1 second.');
}, 1000);

// To stop the interval after 5 seconds
setTimeout(() => {
    clearInterval(intervalId);
    console.log('Interval cleared.');
}, 5000);
```

# Asynchronous JavaScript

## Synchronous vs Asynchronous
Synchronous JavaScript executes code sequentially, meaning each operation must complete before the next one begins. In contrast, asynchronous JavaScript allows certain operations to run in the background, enabling the program to continue executing other code without waiting for the asynchronous operation to complete. This is particularly useful for tasks like network requests, file reading, or timers.

### Example of Synchronous Code:
```javascript
console.log('Start');
function synchronousTask() {
    console.log('Synchronous task completed');
}

synchronousTask();
console.log('End');
```

### Example of Asynchronous Code:
```javascript
console.log('Start');
function asynchronousTask() {
    setTimeout(() => {
        console.log('Asynchronous task completed');
    }, 2000);
}
asynchronousTask();
console.log('End');
```

## Blocking vs Non-blocking
Blocking code stops the execution of subsequent code until the current operation is completed, which can lead to delays and unresponsive behavior. Non-blocking code allows other operations to continue executing while waiting for the current operation to finish, improving performance and responsiveness.

### Example of Blocking Code:
```javascript
console.log('Start');
function blockingTask() {
    const start = Date.now();
    while (Date.now() - start < 2000) {
        // Simulating a blocking operation for 2 seconds
    }
    console.log('Blocking task completed');
}

blockingTask();
console.log('End');
```

### Example of Non-blocking Code:
```javascript
console.log('Start');
function nonBlockingTask() {
    setTimeout(() => {
        console.log('Non-blocking task completed');
    }, 2000);
}
nonBlockingTask();
console.log('End');
```

## Call stack
The call stack is a data structure that keeps track of the function calls in a program. It operates on a Last In, First Out (LIFO) principle, meaning the last function called is the first one to be completed. When a function is invoked, it is added to the top of the call stack, and when it returns, it is removed from the stack. If the call stack becomes too deep (e.g., due to excessive recursion), it can lead to a "stack overflow" error.

### Example:
```javascript
function firstFunction() {
    console.log('First function called');
    secondFunction();
}

function secondFunction() {
    console.log('Second function called');
    thirdFunction();
}

function thirdFunction() {
    console.log('Third function called');
}

firstFunction();
```

## Web APIs
Web APIs are a set of interfaces provided by the browser that allow JavaScript to interact with the browser and perform various tasks, such as making network requests, manipulating the DOM, handling events, and accessing device features. These APIs enable developers to create rich and interactive web applications.

### Example:
```javascript
// Using the Fetch API to make a network request
fetch('https://api.example.com/data')
    .then(response => response.json())
    .then(data => {
        console.log('Data received:', data);
    })
    .catch(error => {
        console.error('Error fetching data:', error);
    });
```

## Callback queue
The callback queue is a data structure that holds functions (callbacks) that are waiting to be executed after the current execution context is completed. When an asynchronous operation (like a network request or a timer) finishes, its callback function is placed in the callback queue. The event loop continuously checks the call stack and the callback queue, and when the call stack is empty, it takes the first function from the callback queue and pushes it onto the call stack for execution.

### Example:
```javascript
console.log('Start');
setTimeout(() => {
    console.log('Callback from setTimeout');
}, 2000);
console.log('End');
```

## Microtask queue
The microtask queue is a special queue that holds tasks that need to be executed after the current execution context and before the next event loop iteration. Microtasks are typically created by promises and other asynchronous operations. The microtask queue has a higher priority than the callback queue, meaning that all microtasks will be executed before any tasks in the callback queue.

### Example:
```javascript
console.log('Start');
Promise.resolve().then(() => {
    console.log('Microtask from Promise');
});

console.log('End');
```

## Event loop
The event loop is a fundamental concept in JavaScript that manages the execution of code, handling of events, and execution of asynchronous tasks. It continuously checks the call stack and the callback queue, ensuring that the JavaScript runtime remains responsive. When the call stack is empty, the event loop takes the first task from the callback queue and pushes it onto the call stack for execution. This process allows JavaScript to handle asynchronous operations without blocking the main thread.

### Example:
```javascript
console.log('Start');
setTimeout(() => {
    console.log('Callback from setTimeout');
}, 2000);

Promise.resolve().then(() => {
    console.log('Microtask from Promise');
});

console.log('End');
```

## Task queue
The task queue, also known as the callback queue, is a data structure that holds tasks (callbacks) that are waiting to be executed after the current execution context is completed. When an asynchronous operation (like a network request or a timer) finishes, its callback function is placed in the task queue. The event loop continuously checks the call stack and the task queue, and when the call stack is empty, it takes the first task from the task queue and pushes it onto the call stack for execution.

### Example:
```javascript
console.log('Start');
setTimeout(() => {
    console.log('Task from setTimeout');
}, 2000);

console.log('End');
```

## Callback functions
A callback function is a function that is passed as an argument to another function and is executed after a certain event or operation has completed. Callback functions are commonly used in asynchronous programming to handle the results of operations like network requests, timers, or user interactions. They allow you to define what should happen once the asynchronous task is finished.

### Example:
```javascript
function fetchData(callback) {
    setTimeout(() => {
        console.log('Data fetched');
        callback();
    }, 1000);
}

fetchData(() => {
    console.log('Callback executed after data is fetched');
});
```

## Callback hell
The term "callback hell" refers to a situation in JavaScript where multiple nested callbacks are used, leading to code that is difficult to read, maintain, and debug. This often occurs when dealing with asynchronous operations that depend on the results of previous operations. The deeply nested structure can make it challenging to follow the flow of the code and handle errors effectively.

### Example of Callback Hell:
```javascript
function fetchData(callback) {
    setTimeout(() => {
        console.log('Data fetched');
        callback();
    }, 1000);
}

fetchData(() => {
    setTimeout(() => {
        console.log('Processing data');
        setTimeout(() => {
            console.log('Data processed');
            setTimeout(() => {
                console.log('Finalizing');
            }, 1000);
        }, 1000);
    }, 1000);
});
```

## Promises
A Promise is an object that represents the eventual completion (or failure) of an asynchronous operation and its resulting value. Promises provide a cleaner and more manageable way to handle asynchronous operations compared to traditional callbacks. A Promise can be in one of three states: pending, fulfilled, or rejected. You can use the `then()` method to handle the fulfilled state and the `catch()` method to handle the rejected state.

### Example:
```javascript
function fetchData() {
    return new Promise((resolve, reject) => {
        setTimeout(() => {
            const success = true; // Simulate success or failure
            if (success) {
                resolve('Data fetched successfully');
            } else {
                reject('Error fetching data');
            }
        }, 1000);
    });
}

fetchData()
    .then((message) => {
        console.log(message); // Output: Data fetched successfully
    })
    .catch((error) => {
        console.error(error); // Output: Error fetching data
    });
```

## Promise states
A Promise can be in one of three states:
1. **Pending**: The initial state of a Promise, indicating that the asynchronous operation is still in progress and has not yet completed.
2. **Fulfilled**: The state of a Promise when the asynchronous operation has completed successfully, and the resulting value is available. The `then()` method is used to handle the fulfilled state.
3. **Rejected**: The state of a Promise when the asynchronous operation has failed, and an error or reason for the failure is available. The `catch()` method is used to handle the rejected state.

### Example:
```javascript
function fetchData() {
    return new Promise((resolve, reject) => {
        setTimeout(() => {
            const success = true; // Simulate success or failure
            if (success) {
                resolve('Data fetched successfully');
            } else {
                reject('Error fetching data');
            }
        }, 1000);
    });
}

fetchData()
    .then((message) => {
        console.log(message); // Output: Data fetched successfully
    })
    .catch((error) => {
        console.error(error); // Output: Error fetching data
    });
```

## Promise Chaining
Promise chaining is a technique that allows you to perform a series of asynchronous operations in a sequential manner by returning a new Promise from each `then()` method. This enables you to handle the results of one operation and pass them to the next operation in the chain. Promise chaining helps to avoid callback hell and makes the code more readable and maintainable.

### Example:
```javascript
function fetchData() {
    return new Promise((resolve, reject) => {
        setTimeout(() => {
            const success = true; // Simulate success or failure
            if (success) {
                resolve('Data fetched successfully');
            } else {
                reject('Error fetching data');
            }
        }, 1000);
    });
}

fetchData()
    .then((message) => {
        console.log(message); // Output: Data fetched successfully
        return 'Processing data...';
    })
    .then((processingMessage) => {
        console.log(processingMessage); // Output: Processing data...
        return 'Data processed successfully';
    })
    .then((finalMessage) => {
        console.log(finalMessage); // Output: Data processed successfully
    })
    .catch((error) => {
        console.error(error); // Handle any errors that occur in the chain
    });
```

## Async/Await
`async` and `await` are syntactic features in JavaScript that provide a more readable and convenient way to work with Promises. An `async` function always returns a Promise, and the `await` keyword can be used inside an `async` function to pause the execution of the function until the Promise is resolved or rejected. This allows you to write asynchronous code that looks and behaves like synchronous code, making it easier to read and maintain.

### Example:
```javascript
async function fetchData() {
    return new Promise((resolve, reject) => {
        setTimeout(() => {
            const success = true; // Simulate success or failure
            if (success) {
                resolve('Data fetched successfully');
            } else {
                reject('Error fetching data');
            }
        }, 1000);
    });
}

async function processData() {
    try {
        const message = await fetchData();
        console.log(message); // Output: Data fetched successfully
        console.log('Processing data...');
        // Simulate processing
        await new Promise(resolve => setTimeout(resolve, 1000));
        console.log('Data processed successfully');
    } catch (error) {
        console.error(error); // Handle any errors that occur
    }
}

processData();
```

## Error handling with async/await
When using `async` and `await`, error handling can be done using `try...catch` blocks. If an awaited Promise is rejected, the control flow will jump to the `catch` block, allowing you to handle the error gracefully. This approach makes it easier to manage errors in asynchronous code compared to traditional Promise chaining.

### Example:
```javascript
async function fetchData() {
    return new Promise((resolve, reject) => {
        setTimeout(() => {
            const success = false; // Simulate success or failure
            if (success) {
                resolve('Data fetched successfully');
            } else {
                reject('Error fetching data');
            }
        }, 1000);
    });
}

async function processData() {
    try {
        const message = await fetchData();
        console.log(message); // This line will not execute if fetchData rejects
        console.log('Processing data...');
    } catch (error) {
        console.error(error); // Output: Error fetching data
    }
}

processData();
```

## Parallel promises
When you have multiple asynchronous operations that can be executed concurrently, you can use `Promise.all()` to run them in parallel. `Promise.all()` takes an array of Promises and returns a new Promise that resolves when all of the input Promises have resolved, or rejects if any of the input Promises reject. This is useful for optimizing performance when multiple independent tasks need to be completed.

### Example:
```javascript
async function fetchData1() {
    return new Promise((resolve) => {
        setTimeout(() => {
            resolve('Data 1 fetched');
        }, 1000);
    });
}

async function fetchData2() {
    return new Promise((resolve) => {
        setTimeout(() => {
            resolve('Data 2 fetched');
        }, 1500);
    });
}

async function fetchData3() {
    return new Promise((resolve) => {
        setTimeout(() => {
            resolve('Data 3 fetched');
        }, 500);
    });
}

async function fetchAllData() {
    try {
        const results = await Promise.all([fetchData1(), fetchData2(), fetchData3()]);
        console.log(results); // Output: ['Data 1 fetched', 'Data 2 fetched', 'Data 3 fetched']
    } catch (error) {
        console.error('Error fetching data:', error);
    }
}

fetchAllData();
```

## Sequential promises
When you have multiple asynchronous operations that need to be executed in a specific order, you can chain Promises sequentially. Each Promise in the chain will wait for the previous one to resolve before executing. This is useful when the result of one operation is needed for the next operation.

### Example:
```javascript
async function fetchData1() {
    return new Promise((resolve) => {
        setTimeout(() => {
            resolve('Data 1 fetched');
        }, 1000);
    });
}

async function fetchData2() {
    return new Promise((resolve) => {
        setTimeout(() => {
            resolve('Data 2 fetched');
        }, 1500);
    });
} 

async function fetchData3() {
    return new Promise((resolve) => {
        setTimeout(() => {
            resolve('Data 3 fetched');
        }, 500);
    });
}

async function fetchAllDataSequentially() {
    try {
        const result1 = await fetchData1();
        console.log(result1); // Output: Data 1 fetched

        const result2 = await fetchData2();
        console.log(result2); // Output: Data 2 fetched

        const result3 = await fetchData3();
        console.log(result3); // Output: Data 3 fetched
    } catch (error) {
        console.error('Error fetching data:', error);
    }
}

fetchAllDataSequentially();
```

## Promise cancellation concepts
The concept of Promise cancellation refers to the ability to stop or cancel an ongoing asynchronous operation represented by a Promise. However, native JavaScript Promises do not support cancellation directly. Instead, developers can implement cancellation patterns using techniques such as using flags, AbortController, or third-party libraries.

### Example using AbortController:
```javascript
const controller = new AbortController();
const signal = controller.signal;

fetch('https://api.example.com/data', { signal })
    .then(response => response.json())
    .then(data => {
        console.log('Data fetched:', data);
    })
    .catch(error => {
        if (error.name === 'AbortError') {
            console.log('Fetch aborted');
        } else {
            console.error('Error fetching data:', error);
        }
    });

// Cancel the fetch request after 1 second
setTimeout(() => {
    controller.abort();
}, 1000);
```

## AbortController
The `AbortController` is a web API that allows you to abort or cancel ongoing asynchronous operations, such as fetch requests. It provides a way to create a signal that can be passed to the operation, and when the signal is triggered, the operation is aborted. This is particularly useful for managing long-running requests or when the user navigates away from a page.

### Example:
```javascript
const controller = new AbortController();
const signal = controller.signal;
fetch('https://api.example.com/data', { signal })
    .then(response => response.json())
    .then(data => {
        console.log('Data fetched:', data);
    })
    .catch(error => {
        if (error.name === 'AbortError') {
            console.log('Fetch aborted');
        } else {
            console.error('Error fetching data:', error);
        }
    });

// Cancel the fetch request after 1 second
setTimeout(() => {
    controller.abort();
}, 1000);
```
