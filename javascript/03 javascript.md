# Object-Oriented Programming in JavaScript

## Objects vs classes
In JavaScript, objects are collections of key-value pairs, while classes are blueprints for creating objects. Objects can be created using object literals, while classes are defined using the `class` keyword.

## Creating Objects
You can create objects in JavaScript using object literals or the `new` keyword with a constructor function. Here's an example of creating an object using an object literal:

```javascript
const person = {
  name: 'John',
  age: 30,
  greet: function() {
    console.log(`Hello, my name is ${this.name}`);
  }
};
```

## Creating Classes
You can create classes in JavaScript using the `class` keyword. Here's an example of creating a class:

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
```

## Constructors functions
In JavaScript, constructor functions are used to create objects. They are defined using a regular function and are called with the `new` keyword. Here's an example of a constructor function:

```javascript
function Person(name, age) {
  this.name = name;
  this.age = age;
}

Person.prototype.greet = function() {
  console.log(`Hello, my name is ${this.name}`);
};
```

### Example of creating an object using a constructor function:

```javascript
const person1 = new Person('Alice', 25);
person1.greet(); // Output: Hello, my name is Alice
```

## new Keyword
The `new` keyword is used to create an instance of a class or a constructor function.

### Example of using the `new` keyword with a class:

```javascript
const person2 = new Person('Bob', 28);
person2.greet(); // Output: Hello, my name is Bob
```

## Prototypes
In JavaScript, every object has a prototype, which is another object that it inherits properties and methods from. Prototypes allow for inheritance and sharing of methods between objects.

### Example of using prototypes:

```javascript
function Animal(name) {
  this.name = name;
}
Animal.prototype.speak = function() {
  console.log(`${this.name} makes a noise.`);
};

const dog = new Animal('Dog');
dog.speak(); // Output: Dog makes a noise.
```

## Prototype Chain
The prototype chain is a mechanism in JavaScript that allows objects to inherit properties and methods from other objects. When you try to access a property or method on an object, JavaScript will first look for it on the object itself. If it doesn't find it there, it will look up the prototype chain until it finds the property or reaches the end of the chain.

### Example of the prototype chain:

```javascript
function Vehicle(type) {
  this.type = type;
}
Vehicle.prototype.start = function() {
  console.log(`${this.type} is starting.`);
};

const car = new Vehicle('Car');
car.start(); // Output: Car is starting.
```

## __proto__
The `__proto__` property is a reference to the prototype of an object. It allows you to access and modify the prototype of an object directly. However, it is generally recommended to use `Object.getPrototypeOf()` and `Object.setPrototypeOf()` for better compatibility and clarity.

### Example of using `__proto__`:

```javascript
const animal = {
  speak: function() {
    console.log(`${this.name} makes a noise.`);
  }
};

const dog = {
  name: 'Dog'
};

dog.__proto__ = animal;
dog.speak(); // Output: Dog makes a noise.
```

## prototype vs __proto__
- `prototype` is a property of constructor functions that is used to define methods and properties that should be shared among all instances created by that constructor.

- `__proto__` is a property of an object that points to the prototype of the constructor function that created it. It allows you to access and modify the prototype chain of an object.

### Example of `prototype` vs `__proto__`:

```javascript
function Person(name) {
  this.name = name;
}

Person.prototype.greet = function() {
  console.log(`Hello, my name is ${this.name}`);
};

const person3 = new Person('Charlie');
console.log(person3.__proto__ === Person.prototype); // Output: true
```

## Object.getPrototypeOf() and Object.setPrototypeOf()
`Object.getPrototypeOf()` is a method that returns the prototype of a specified object, while `Object.setPrototypeOf()` is a method that sets the prototype of a specified object to another object.

### Example of using `Object.getPrototypeOf()` and `Object.setPrototypeOf()`:

```javascript
const animal = {
  speak: function() {
    console.log(`${this.name} makes a noise.`);
  }
};

const dog = {
  name: 'Dog'
};

Object.setPrototypeOf(dog, animal);
dog.speak(); // Output: Dog makes a noise.

Object.getPrototypeOf(dog); // Returns the animal object
```

## Classes
In JavaScript, classes are a syntactical sugar over the existing prototype-based inheritance. They provide a more familiar and structured way to create objects and deal with inheritance.

### Example of creating a class:

```javascript
class Animal {
  constructor(name) {
    this.name = name;
  }

  speak() {
    console.log(`${this.name} makes a noise.`);
  }
}

const dog = new Animal('Dog');
dog.speak(); // Output: Dog makes a noise.
```

## Constructor
In JavaScript, a constructor is a special method of a class that is called when a new instance of the class is created. It is used to initialize the properties of the object.

### Example of a constructor in a class:

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

const person4 = new Person('David', 35);
person4.greet(); // Output: Hello, my name is David
```

## Instance methods
Instance methods are functions that are defined inside a class and can be called on instances of that class. They have access to the instance's properties and can manipulate them.

### Example of instance methods:

```javascript
class Person {
  constructor(name, age) {
    this.name = name;
    this.age = age;
  }

  greet() {
    console.log(`Hello, my name is ${this.name}`);
  }

  haveBirthday() {
    this.age += 1;
    console.log(`Happy Birthday! I am now ${this.age} years old.`);
  }
}

const person5 = new Person('Eve', 29);
person5.greet(); // Output: Hello, my name is Eve
person5.haveBirthday(); // Output: Happy Birthday! I am now 30 years old.
```

## Static methods
Static methods are functions that are defined on a class itself, rather than on instances of the class. They can be called directly on the class without creating an instance. Static methods are often used for utility functions that are related to the class but do not require access to instance properties.

### Example of static methods:

```javascript
class MathUtils {
  static add(a, b) {
    return a + b;
  }

  static subtract(a, b) {
    return a - b;
  }
}

// Calling static methods
console.log(MathUtils.add(5, 3)); // Output: 8
console.log(MathUtils.subtract(10, 4)); // Output: 6
```

## static properties
Static properties are properties that belong to the class itself, rather than to instances of the class. They can be accessed directly on the class without creating an instance. Static properties are often used to store constants or shared data that is relevant to the class as a whole.

### Example of static properties:

```javascript
class Circle {
  static pi = 3.14159;

  constructor(radius) {
    this.radius = radius;
  }

  area() {
    return Circle.pi * this.radius * this.radius;
  }
}

// Accessing static property
console.log(Circle.pi); // Output: 3.14159

const circle = new Circle(5);
console.log(circle.area()); // Output: 78.53975
```

## Getters and Setters
Getters and setters are special methods in JavaScript classes that allow you to define how to access and modify the properties of an object. Getters are used to retrieve the value of a property, while setters are used to set the value of a property. They provide a way to encapsulate the internal representation of an object and control how its properties are accessed and modified.

### Example of getters and setters:

```javascript
class Person {
  constructor(name, age) {
    this._name = name; // Using underscore to indicate a private property
    this._age = age;
  }

  // Getter for name
  get name() {
    return this._name;
  }

  // Setter for name
  set name(newName) {
    this._name = newName;
  }

  // Getter for age
  get age() {
    return this._age;
  }

  // Setter for age
  set age(newAge) {
    if (newAge >= 0) {
      this._age = newAge;
    } else {
      console.log('Age must be a positive number.');
    }
  }
}

// Example usage
const person6 = new Person('Frank', 40);
console.log(person6.name); // Output: Frank
person6.name = 'George';
console.log(person6.name); // Output: George
person6.age = 45;
console.log(person6.age); // Output: 45
person6.age = -5; // Output: Age must be a positive number.
```

## Private fields
Private fields are a feature in JavaScript classes that allow you to define properties that are only accessible within the class itself. They are declared using a `#` prefix and cannot be accessed or modified from outside the class. This provides encapsulation and helps to protect the internal state of an object.

### Example of private fields:

```javascript
class Person {
  #name; // Private field
  #age;  // Private field

  constructor(name, age) {
    this.#name = name;
    this.#age = age;
  }

  greet() {
    console.log(`Hello, my name is ${this.#name}`);
  }

  getAge() {
    return this.#age;
  }
}

// Example usage
const person7 = new Person('Hannah', 32);
person7.greet(); // Output: Hello, my name is Hannah
console.log(person7.getAge()); // Output: 32
// Trying to access private fields directly will result in an error
// console.log(person7.#name); // SyntaxError: Private field '#name' must be declared in an enclosing class
```

## Public fields
Public fields are properties of a class that can be accessed and modified from outside the class. They are declared without any special prefix and can be freely accessed by instances of the class. Public fields provide a way to store data that is meant to be shared or modified externally.

### Example of public fields:

```javascript
class Person {
  name; // Public field
  age;  // Public field

  constructor(name, age) {
    this.name = name;
    this.age = age;
  }

  greet() {
    console.log(`Hello, my name is ${this.name}`);
  }
}

// Example usage
const person8 = new Person('Ian', 27);
person8.greet(); // Output: Hello, my name is Ian
console.log(person8.name); // Output: Ian
person8.age = 28; // Modifying public field
console.log(person8.age); // Output: 28
```

## Inheritance
Inheritance is a fundamental concept in object-oriented programming that allows one class to inherit properties and methods from another class. In JavaScript, inheritance is achieved using the `extends` keyword. The class that inherits is called the subclass, and the class being inherited from is called the superclass.

### Example of inheritance:

```javascript
class Animal {
  constructor(name) {
    this.name = name;
  }

  speak() {
    console.log(`${this.name} makes a noise.`);
  }
}

class Dog extends Animal {
  constructor(name, breed) {
    super(name); // Call the constructor of the superclass
    this.breed = breed;
  }

  speak() {
    console.log(`${this.name} barks.`);
  }
}

// Example usage
const dog = new Dog('Buddy', 'Golden Retriever');
dog.speak(); // Output: Buddy barks.
```

## extends Keyword
The `extends` keyword in JavaScript is used to create a class that is a child of another class. It allows the child class to inherit properties and methods from the parent class, enabling code reuse and establishing a hierarchical relationship between classes.

### Example of using the `extends` keyword:

```javascript
class Vehicle {
  constructor(type) {
    this.type = type;
  }

  start() {
    console.log(`${this.type} is starting.`);
  }
}

class Car extends Vehicle {
  constructor(type, brand) {
    super(type); // Call the constructor of the parent class
    this.brand = brand;
  }

  start() {
    console.log(`${this.brand} ${this.type} is starting.`);
  }
}

// Example usage
const car = new Car('Car', 'Toyota');
car.start(); // Output: Toyota Car is starting.
```

## super Keyword
The `super` keyword in JavaScript is used to call the constructor or methods of a parent class from a subclass. It allows you to access and invoke the functionality of the parent class, enabling you to extend and customize behavior in the child class.

### Example of using the `super` keyword:

```javascript
class Animal {
  constructor(name) {
    this.name = name;
  }

  speak() {
    console.log(`${this.name} makes a noise.`);
  }
}

class Dog extends Animal {
  constructor(name, breed) {
    super(name); // Call the constructor of the parent class
    this.breed = breed;
  }

  speak() {
    super.speak(); // Call the speak method of the parent class
    console.log(`${this.name} barks.`);
  }
}

// Example usage
const dog = new Dog('Buddy', 'Golden Retriever');
dog.speak();
// Output:
// Buddy makes a noise.
// Buddy barks.
```

## Polymorphism
Polymorphism is a concept in object-oriented programming that allows objects of different classes to be treated as objects of a common superclass. It enables a single interface to represent different underlying forms (data types). In JavaScript, polymorphism is often achieved through method overriding, where a subclass provides a specific implementation of a method that is already defined in its superclass.

### Example of polymorphism:

```javascript
class Animal {
  speak() {
    console.log('Animal makes a noise.');
  }
}

class Dog extends Animal {
  speak() {
    console.log('Dog barks.');
  }
}

class Cat extends Animal {
  speak() {
    console.log('Cat meows.');
  }
}

// Example usage
const animals = [new Dog(), new Cat()];
animals.forEach(animal => animal.speak());
// Output:
// Dog barks.
// Cat meows.
```

## Encapsulation
Encapsulation is a principle of object-oriented programming that restricts direct access to an object's internal state and behavior. It allows you to hide the internal implementation details of a class and expose only the necessary methods and properties to interact with the object. In JavaScript, encapsulation can be achieved using private fields, getters, and setters.

### Example of encapsulation:

```javascript
class BankAccount {
  #balance; // Private field

  constructor(initialBalance) {
    this.#balance = initialBalance;
  }

  deposit(amount) {
    if (amount > 0) {
      this.#balance += amount;
      console.log(`Deposited: $${amount}. New balance: $${this.#balance}`);
    } else {
      console.log('Deposit amount must be positive.');
    }
  }

  withdraw(amount) {
    if (amount > 0 && amount <= this.#balance) {
      this.#balance -= amount;
      console.log(`Withdrew: $${amount}. New balance: $${this.#balance}`);
    } else {
      console.log('Invalid withdrawal amount.');
    }
  }

  getBalance() {
    return this.#balance;
  }
}

// Example usage
const account = new BankAccount(1000);
account.deposit(500); // Output: Deposited: $500. New balance: $1500
account.withdraw(200); // Output: Withdrew: $200. New balance: $1300
console.log(account.getBalance()); // Output: 1300
// Trying to access private field directly will result in an error
// console.log(account.#balance); // SyntaxError: Private field '#balance' must be declared in an enclosing class
```

## Abstraction
Abstraction is a principle of object-oriented programming that focuses on exposing only the essential features of an object while hiding the unnecessary details. It allows you to create a simplified interface for interacting with complex systems. In JavaScript, abstraction can be achieved through the use of classes, methods, and interfaces that define the behavior of objects without revealing their internal implementation.

### Example of abstraction:

```javascript
class Shape {
  constructor(name) {
    this.name = name;
  }

  area() {
    throw new Error('Method "area()" must be implemented.');
  }
}

class Circle extends Shape {
  constructor(radius) {
    super('Circle');
    this.radius = radius;
  }

  area() {
    return Math.PI * this.radius * this.radius;
  }
}

class Rectangle extends Shape {
  constructor(width, height) {
    super('Rectangle');
    this.width = width;
    this.height = height;
  }

  area() {
    return this.width * this.height;
  }
}

// Example usage
const shapes = [new Circle(5), new Rectangle(4, 6)];
shapes.forEach(shape => {
  console.log(`The area of the ${shape.name} is: ${shape.area()}`);
});
// Output:
// The area of the Circle is: 78.53981633974483
// The area of the Rectangle is: 24
```

## Composition
Composition is a design principle in object-oriented programming that allows you to build complex objects by combining simpler objects or components. Instead of relying solely on inheritance, composition promotes the idea of creating objects that contain other objects, enabling greater flexibility and reusability. In JavaScript, composition can be achieved by including instances of other classes as properties within a class.

### Example of composition:

```javascript
class Engine {
  start() {
    console.log('Engine started.');
  }
}

class Car {
  constructor(brand) {
    this.brand = brand;
    this.engine = new Engine(); // Composition: Car has an Engine
  }

  start() {
    console.log(`${this.brand} car is starting.`);
    this.engine.start(); // Delegating the start to the Engine
  }
}

// Example usage
const myCar = new Car('Toyota');
myCar.start();
// Output:
// Toyota car is starting.
// Engine started.
```

## Composition vs Inheritance
Composition and inheritance are two different approaches to creating relationships between classes in object-oriented programming.

- Inheritance allows a class to inherit properties and methods from a parent class, creating a hierarchical relationship. It is useful when there is a clear "is-a" relationship between classes (e.g., a Dog is an Animal).

- Composition, on the other hand, allows a class to contain instances of other classes, creating a "has-a" relationship. It is useful when you want to build complex objects by combining simpler components (e.g., a Car has an Engine).

### Example of composition vs inheritance:

```javascript
// Inheritance example
class Animal {
  speak() {
    console.log('Animal makes a noise.');
  }
}

class Dog extends Animal {
  speak() {
    console.log('Dog barks.');
  }
}

// Composition example
class Engine {
  start() {
    console.log('Engine started.');
  }
}

class Car {
  constructor(brand) {
    this.brand = brand;
    this.engine = new Engine(); // Composition: Car has an Engine
  }

  start() {
    console.log(`${this.brand} car is starting.`);
    this.engine.start(); // Delegating the start to the Engine
  }
}
```

# `This` Keyword

## Global `this`
In JavaScript, the value of `this` depends on the context in which it is used. In the global context (outside of any function or class), `this` refers to the global object, which is `window` in browsers and `global` in Node.js.

### Example of global `this`:

```javascript
console.log(this); // In a browser, this will log the Window object
```

## `this` inside functions
When `this` is used inside a regular function, its value depends on how the function is called. If the function is called as a method of an object, `this` refers to that object. If the function is called in the global context, `this` refers to the global object.

### Example of `this` inside functions:

```javascript
function showThis() {
  console.log(this);
}

// Calling the function in the global context
showThis(); // In a browser, this will log the Window object

// Calling the function as a method of an object
const obj = {
  name: 'My Object',
  showThis: function() {
    console.log(this);
  }
};

obj.showThis(); // Logs the obj object
```

## `this` inside methods
When `this` is used inside a method of an object, it refers to the object that the method is called on. This allows methods to access and manipulate the properties of the object they belong to.

### Example of `this` inside methods:

```javascript
const person = {
  name: 'Alice',
  greet: function() {
    console.log(`Hello, my name is ${this.name}`);
  }
};

person.greet(); // Output: Hello, my name is Alice
```

## `this` inside arrow functions
Arrow functions in JavaScript do not have their own `this` context. Instead, they inherit `this` from the surrounding lexical scope. This means that the value of `this` inside an arrow function is determined by where the arrow function is defined, not how it is called.

### Example of `this` inside arrow functions:

```javascript
const person = {
  name: 'Bob',
  greet: function() {
    const arrowFunction = () => {
      console.log(`Hello, my name is ${this.name}`);
    };
    arrowFunction();
  }
};

person.greet(); // Output: Hello, my name is Bob
```

## `this` inside classes
In JavaScript classes, `this` refers to the instance of the class that is created when the class is instantiated. It allows methods within the class to access and manipulate the properties of the instance.

### Example of `this` inside classes:

```javascript
class Person {
  constructor(name) {
    this.name = name;
  }

  greet() {
    console.log(`Hello, my name is ${this.name}`);
  }
}

const person = new Person('Charlie');
person.greet(); // Output: Hello, my name is Charlie
```

## Constructor `this`
In a constructor function or class constructor, `this` refers to the newly created instance of the object. It allows you to set properties and methods on the instance being created.

### Example of `this` inside a constructor:

```javascript
function Person(name) {
  this.name = name;
}

const person = new Person('David');
console.log(person.name); // Output: David
```

## call, apply, and bind
In JavaScript, `call`, `apply`, and `bind` are methods that allow you to explicitly set the value of `this` for a function.

### `call` Method
The `call` method calls a function with a given `this` value and arguments provided individually.

### Example of `call`:

```javascript
function greet(greeting) {
  console.log(`${greeting}, my name is ${this.name}`);
}

const person = { name: 'Eve' };
greet.call(person, 'Hello'); // Output: Hello, my name is Eve
```

### `apply` Method
The `apply` method is similar to `call`, but it takes an array of arguments instead of individual arguments.

### Example of `apply`:

```javascript
function greet(greeting) {
  console.log(`${greeting}, my name is ${this.name}`);
}

const person = { name: 'Frank' };
greet.apply(person, ['Hi']); // Output: Hi, my name is Frank
```

### `bind` Method
The `bind` method creates a new function that, when called, has its `this` keyword set to the provided value. It does not call the function immediately but returns a new function that can be called later.

### Example of `bind`:

```javascript
function greet(greeting) {
  console.log(`${greeting}, my name is ${this.name}`);
}

const person = { name: 'Grace' };
const boundGreet = greet.bind(person);
boundGreet('Hey'); // Output: Hey, my name is Grace
```

## Losing `this`
In JavaScript, it is possible to lose the context of `this` when a function is called in a different context than it was defined. This can happen when passing methods as callbacks or when using them in event handlers.

### Example of losing `this`:

```javascript
const person = {
  name: 'Hannah',
  greet: function() {
    console.log(`Hello, my name is ${this.name}`);
  }
};

const greetFunction = person.greet;
greetFunction(); // Output: Hello, my name is undefined (or an error in strict mode)
```

## Explicit Binding
Explicit binding refers to the practice of explicitly setting the value of `this` for a function using methods like `call`, `apply`, or `bind`. This allows you to control the context in which a function is executed, ensuring that `this` refers to the desired object.

### Example of explicit binding:

```javascript
function greet(greeting) {
  console.log(`${greeting}, my name is ${this.name}`);
}

const person = { name: 'Ian' };
// Using call to explicitly bind `this`
greet.call(person, 'Hello'); // Output: Hello, my name is Ian
// Using apply to explicitly bind `this`
greet.apply(person, ['Hi']); // Output: Hi, my name is Ian
// Using bind to create a new function with `this` bound to person
const boundGreet = greet.bind(person);
boundGreet('Hey'); // Output: Hey, my name is Ian
```

## Implicit Binding
Implicit binding occurs when a function is called as a method of an object. In this case, `this` is automatically bound to the object that the method is called on. This is the most common way that `this` is set in JavaScript.

### Example of implicit binding:

```javascript
const person = {
  name: 'Jack',
  greet: function() {
    console.log(`Hello, my name is ${this.name}`);
  }
};

person.greet(); // Output: Hello, my name is Jack
```

## New Binding
New binding occurs when a function is called with the `new` keyword. In this case, `this` is bound to the newly created object instance. This allows you to create multiple instances of an object with their own properties and methods.

### Example of new binding:

```javascript
function Person(name) {
  this.name = name;
}

const person1 = new Person('Karen');
const person2 = new Person('Leo');
console.log(person1.name); // Output: Karen
console.log(person2.name); // Output: Leo
```

# Advanced Functions

## Closures
A closure is a function that has access to its own scope, the outer function's scope, and the global scope. Closures allow functions to retain access to variables from their outer scope even after the outer function has finished executing. This is useful for creating private variables and functions.

### Example of closures:

```javascript
function outerFunction(outerVariable) {
  return function innerFunction(innerVariable) {
    console.log(`Outer Variable: ${outerVariable}`);
    console.log(`Inner Variable: ${innerVariable}`);
  };
}

const closureFunction = outerFunction('I am from the outer function');
closureFunction('I am from the inner function');
// Output:
// Outer Variable: I am from the outer function
// Inner Variable: I am from the inner function
```

## Higher-Order Functions
Higher-order functions are functions that can take other functions as arguments or return functions as their result. They allow for more abstract and flexible programming patterns, enabling the creation of reusable and composable code.

### Example of higher-order functions:

```javascript
function greet(name) {
  return function(message) {
    console.log(`${message}, ${name}!`);
  };
}

const greetJohn = greet('John');
greetJohn('Hello'); // Output: Hello, John!
```

## Currying
Currying is a functional programming technique where a function is transformed into a sequence of functions, each  taking a single argument. It allows for partial application of functions, enabling you to create specialized functions from more general ones.

### Example of currying:

```javascript
function multiply(a) {
  return function(b) {
    return a * b;
  };
}

const multiplyBy2 = multiply(2);
console.log(multiplyBy2(5)); // Output: 10
```

## Partial Application
Partial application is a technique in functional programming where a function is called with fewer arguments than it expects, returning a new function that takes the remaining arguments. This allows you to create specialized functions by pre-filling some of the arguments.

### Example of partial application:

```javascript
function add(a, b) {
  return a + b;
}

const add5 = add.bind(null, 5); // Partially applying the first argument
console.log(add5(10)); // Output: 15
```

## Function Composition
Function composition is a technique in functional programming where multiple functions are combined to create a new function. The output of one function becomes the input of the next function, allowing for the creation of complex operations from simpler functions.

### Example of function composition:

```javascript
function compose(f, g) {
  return function(x) {
    return f(g(x));
  };
}

const add2 = x => x + 2;
const multiplyBy3 = x => x * 3;

const add2ThenMultiplyBy3 = compose(multiplyBy3, add2);
console.log(add2ThenMultiplyBy3(4)); // Output: 18 ( (4 + 2) * 3 )
```

## Memoization
Memoization is an optimization technique that involves caching the results of expensive function calls and returning the cached result when the same inputs occur again. This can significantly improve performance for functions that are called repeatedly with the same arguments.

### Example of memoization:

```javascript
function memoize(fn) {
  const cache = {};
  return function(...args) {
    const key = JSON.stringify(args);
    if (cache[key]) {
      return cache[key];
    } else {
      const result = fn(...args);
      cache[key] = result;
      return result;
    }
  };
}

// Example usage
const fibonacci = memoize(function(n) {
  if (n <= 1) return n;
  return fibonacci(n - 1) + fibonacci(n - 2);
});

console.log(fibonacci(10)); // Output: 55
console.log(fibonacci(10)); // Output: 55 (retrieved from cache)
```

## IIFE (Immediately Invoked Function Expression)
An IIFE (Immediately Invoked Function Expression) is a JavaScript function that is executed immediately after it is defined. It is often used to create a new scope and avoid polluting the global namespace. IIFEs are typically defined using function expressions and are wrapped in parentheses.

### Example of IIFE:

```javascript
(function() {
  const message = 'Hello, I am an IIFE!';
  console.log(message);
})(); // Output: Hello, I am an IIFE!
```

## Callback patterns
A callback pattern is a programming technique where a function is passed as an argument to another function and is executed after the completion of that function. Callbacks are commonly used for asynchronous operations, such as handling events or making API requests.

### Example of callback patterns:

```javascript
function fetchData(callback) {
  setTimeout(() => {
    const data = { name: 'John', age: 30 };
    callback(data);
  }, 1000);
}

// Example usage
fetchData(function(data) {
  console.log(`Name: ${data.name}, Age: ${data.age}`);
});

// Output after 1 second: Name: John, Age: 30
```

## Factory functions
Factory functions are functions that create and return new objects. They provide a way to encapsulate the creation logic and can be used to create multiple instances of similar objects without using classes. Factory functions can also include private variables and methods, providing a level of encapsulation.

### Example of factory functions:

```javascript
function createPerson(name, age) {
  return {
    name,
    age,
    greet() {
      console.log(`Hello, my name is ${this.name}`);
    }
  };
}

// Example usage
const person1 = createPerson('Alice', 25);
person1.greet(); // Output: Hello, my name is Alice
const person2 = createPerson('Bob', 30);
person2.greet(); // Output: Hello, my name is Bob
```

## Function decorators
Function decorators are a design pattern that allows you to modify or enhance the behavior of a function without changing its source code. In JavaScript, decorators can be implemented using higher-order functions that wrap the original function and add additional functionality.

### Example of function decorators:

```javascript
function logExecutionTime(fn) {
  return function(...args) {
    const start = performance.now();
    const result = fn(...args);
    const end = performance.now();
    console.log(`Execution time: ${end - start} milliseconds`);
    return result;
  };
}

// Example usage
function add(a, b) {
  return a + b;
}

const decoratedAdd = logExecutionTime(add);
console.log(decoratedAdd(5, 10)); // Output: Execution time: X milliseconds
                                   //         15
```

## call, apply, and bind
In JavaScript, `call`, `apply`, and `bind` are methods that allow you to explicitly set the value of `this` for a function.

### `call` Method
The `call` method calls a function with a given `this` value and arguments provided individually.

### Example of `call`:

```javascript
function greet(greeting) {
  console.log(`${greeting}, my name is ${this.name}`);
}

const person = { name: 'Eve' };
greet.call(person, 'Hello'); // Output: Hello, my name is Eve
```

### `apply` Method
The `apply` method is similar to `call`, but it takes an array of arguments instead of individual arguments.

### Example of `apply`:

```javascript
function greet(greeting) {
  console.log(`${greeting}, my name is ${this.name}`);
}

const person = { name: 'Frank' };
greet.apply(person, ['Hi']); // Output: Hi, my name is Frank
```

### `bind` Method
The `bind` method creates a new function that, when called, has its `this` keyword set to the provided value. It does not call the function immediately but returns a new function that can be called later.

### Example of `bind`:

```javascript
function greet(greeting) {
  console.log(`${greeting}, my name is ${this.name}`);
}

const person = { name: 'Grace' };
const boundGreet = greet.bind(person);
boundGreet('Hey'); // Output: Hey, my name is Grace
```

# Debouncing and Throttling

## What is debouncing?
Debouncing is a programming technique used to limit the rate at which a function is executed. It ensures that a function is only called after a certain amount of time has passed since the last time it was invoked. This is particularly useful for optimizing performance in scenarios where a function may be called frequently, such as during window resizing or input events.

### Example of debouncing:

```javascript
function debounce(func, delay) {
  let timeoutId;
  return function(...args) {
    clearTimeout(timeoutId);
    timeoutId = setTimeout(() => {
      func.apply(this, args);
    }, delay);
  };
}

// Example usage
const handleResize = () => {
  console.log('Window resized');
};

const debouncedResize = debounce(handleResize, 300);
window.addEventListener('resize', debouncedResize);
```

## Implement debounce from scratch
Here is a simple implementation of a debounce function from scratch:

```javascript
function debounce(func, delay) {
  let timeoutId;
  return function(...args) {
    clearTimeout(timeoutId);
    timeoutId = setTimeout(() => {
      func.apply(this, args);
    }, delay);
  };
}
```

## Debounce with `setTimeout`
The debounce function can be implemented using `setTimeout` to delay the execution of the provided function until after a specified delay has passed since the last time it was invoked. This prevents the function from being called too frequently.

### Example of debounce with `setTimeout`:

```javascript
function debounce(func, delay) {
  let timeoutId;
  return function(...args) {
    clearTimeout(timeoutId);
    timeoutId = setTimeout(() => {
      func.apply(this, args);
    }, delay);
  };
}

// Example usage
const handleInput = () => {
  console.log('Input event handled');
};

const debouncedInput = debounce(handleInput, 500);
document.getElementById('inputField').addEventListener('input', debouncedInput);
```

## Debounce API search
Debouncing can be particularly useful in scenarios like API search, where you want to limit the number of API calls made as a user types in a search input. By debouncing the search function, you can ensure that the API is only called after the user has stopped typing for a specified amount of time, reducing unnecessary requests and improving performance.

### Example of debounce in API search:

```javascript
function debounce(func, delay) {
  let timeoutId;
  return function(...args) {
    clearTimeout(timeoutId);
    timeoutId = setTimeout(() => {
      func.apply(this, args);
    }, delay);
  };
}

// Simulated API search function
function searchAPI(query) {
  console.log(`Searching for: ${query}`);
  // Here you would typically make an API call
}

// Example usage
const debouncedSearch = debounce(searchAPI, 300);

document.getElementById('searchInput').addEventListener('input', (event) => {
  debouncedSearch(event.target.value);
});
```

## Debounce input events
Debouncing input events is a common use case where you want to limit the number of times a function is called as a user types in an input field. This can help improve performance and reduce unnecessary processing, especially when dealing with expensive operations like API calls or complex calculations.

### Example of debouncing input events:

```javascript
function debounce(func, delay) {
  let timeoutId;
  return function(...args) {
    clearTimeout(timeoutId);
    timeoutId = setTimeout(() => {
      func.apply(this, args);
    }, delay);
  };
}

// Example usage
const handleInput = (event) => {
  console.log(`Input value: ${event.target.value}`);
};

const debouncedInput = debounce(handleInput, 300);
document.getElementById('inputField').addEventListener('input', debouncedInput);
```

## Debounce resize events
Debouncing resize events is a common technique used to optimize performance when handling window resize events. When a user resizes the window, the resize event can fire multiple times in quick succession, leading to performance issues if the event handler performs expensive operations. By debouncing the resize event, you can ensure that the handler is only called after the user has finished resizing the window.

### Example of debouncing resize events:

```javascript
function debounce(func, delay) {
  let timeoutId;
  return function(...args) {
    clearTimeout(timeoutId);
    timeoutId = setTimeout(() => {
      func.apply(this, args);
    }, delay);
  };
}

// Example usage
const handleResize = () => {
  console.log('Window resized');
};

const debouncedResize = debounce(handleResize, 300);
window.addEventListener('resize', debouncedResize);
```

## What is throttling?
Throttling is a programming technique used to limit the rate at which a function is executed. It ensures that a function is called at most once in a specified time interval, regardless of how many times it is triggered. This is particularly useful for optimizing performance in scenarios where a function may be called frequently, such as during scrolling or mouse movement events.

### Example of throttling:

```javascript
function throttle(func, limit) {
  let lastFunc;
  let lastRan;
  return function(...args) {
    if (!lastRan) {
      func.apply(this, args);
      lastRan = Date.now();
    } else {
      clearTimeout(lastFunc);
      lastFunc = setTimeout(() => {
        if ((Date.now() - lastRan) >= limit) {
          func.apply(this, args);
          lastRan = Date.now();
        }
      }, limit - (Date.now() - lastRan));
    }
  };
}

// Example usage
const handleScroll = () => {
  console.log('Scroll event handled');
};

const throttledScroll = throttle(handleScroll, 200);
window.addEventListener('scroll', throttledScroll);
```

## Implement throttle from scratch
Here is a simple implementation of a throttle function from scratch:

```javascript
function throttle(func, limit) {
  let lastFunc;
  let lastRan;
  return function(...args) {
    if (!lastRan) {
      func.apply(this, args);
      lastRan = Date.now();
    } else {
      clearTimeout(lastFunc);
      lastFunc = setTimeout(() => {
        if ((Date.now() - lastRan) >= limit) {
          func.apply(this, args);
          lastRan = Date.now();
        }
      }, limit - (Date.now() - lastRan));
    }
  };
}
```

## Throttle scroll events
Throttling scroll events is a common technique used to optimize performance when handling window scroll events. When a user scrolls the page, the scroll event can fire multiple times in quick succession, leading to performance issues if the event handler performs expensive operations. By throttling the scroll event, you can ensure that the handler is only called at most once in a specified time interval.

### Example of throttling scroll events:

```javascript
function throttle(func, limit) {
  let lastFunc;
  let lastRan;
  return function(...args) {
    if (!lastRan) {
      func.apply(this, args);
      lastRan = Date.now();
    } else {
      clearTimeout(lastFunc);
      lastFunc = setTimeout(() => {
        if ((Date.now() - lastRan) >= limit) {
          func.apply(this, args);
          lastRan = Date.now();
        }
      }, limit - (Date.now() - lastRan));
    }
  };
}

// Example usage
const handleScroll = () => {
  console.log('Scroll event handled');
};

const throttledScroll = throttle(handleScroll, 200);
window.addEventListener('scroll', throttledScroll);
```

## Throttle mouse events
Throttling mouse events is a common technique used to optimize performance when handling mouse events, such as `mousemove`, `mousedown`, or `mouseup`. When a user moves the mouse, the event can fire multiple times in quick succession, leading to performance issues if the event handler performs expensive operations. By throttling the mouse event, you can ensure that the handler is only called at most once in a specified time interval.

### Example of throttling mouse events:

```javascript
function throttle(func, limit) {
  let lastFunc;
  let lastRan;
  return function(...args) {
    if (!lastRan) {
      func.apply(this, args);
      lastRan = Date.now();
    } else {
      clearTimeout(lastFunc);
      lastFunc = setTimeout(() => {
        if ((Date.now() - lastRan) >= limit) {
          func.apply(this, args);
          lastRan = Date.now();
        }
      }, limit - (Date.now() - lastRan));
    }
  };
}

// Example usage
const handleMouseMove = (event) => {
  console.log(`Mouse moved to: (${event.clientX}, ${event.clientY})`);
};

const throttledMouseMove = throttle(handleMouseMove, 100);
document.addEventListener('mousemove', throttledMouseMove);
```

## Debounce vs Throttle
Debouncing and throttling are both techniques used to control the rate at which a function is executed, but they serve different purposes and are used in different scenarios.

- **Debouncing**: Debouncing ensures that a function is only called after a certain amount of time has passed since the last time it was invoked. It is useful for scenarios where you want to wait until the user has stopped performing an action before executing a function, such as when typing in a search input or resizing a window.

- **Throttling**: Throttling ensures that a function is called at most once in a specified time interval, regardless of how many times it is triggered. It is useful for scenarios where you want to limit the rate of execution of a function, such as when handling scroll or mouse movement events.

### Example of debounce vs throttle:

```javascript
// Debounce example
function debounce(func, delay) {
  let timeoutId;
  return function(...args) {
    clearTimeout(timeoutId);
    timeoutId = setTimeout(() => {
      func.apply(this, args);
    }, delay);
  };
}

// Throttle example
function throttle(func, limit) {
  let lastFunc;
  let lastRan;
  return function(...args) {
    if (!lastRan) {
      func.apply(this, args);
      lastRan = Date.now();
    } else {
      clearTimeout(lastFunc);
      lastFunc = setTimeout(() => {
        if ((Date.now() - lastRan) >= limit) {
          func.apply(this, args);
          lastRan = Date.now();
        }
      }, limit - (Date.now() - lastRan));
    }
  };
}
```

## Leading execution
The leading execution in the context of debouncing and throttling refers to the behavior of executing the function immediately on the first call, rather than waiting for the delay or limit to pass. This can be useful in scenarios where you want to ensure that the function is executed at least once at the beginning of a series of rapid calls.

### Example of leading execution in debounce:

```javascript
function debounce(func, delay, leading = false) {
  let timeoutId;
  return function(...args) {
    if (leading && !timeoutId) {
      func.apply(this, args);
    }
    clearTimeout(timeoutId);
    timeoutId = setTimeout(() => {
      if (!leading) {
        func.apply(this, args);
      }
      timeoutId = null;
    }, delay);
  };
}

// Example usage
const handleInput = (event) => {
  console.log(`Input value: ${event.target.value}`);
};

const debouncedInput = debounce(handleInput, 300, true);
document.getElementById('inputField').addEventListener('input', debouncedInput);
```

## Trailing execution
Trailing execution in the context of debouncing and throttling refers to the behavior of executing the function after the specified delay or limit has passed, rather than immediately on the first call. This ensures that the function is executed only once after a series of rapid calls, which can be useful for scenarios where you want to wait until the user has finished performing an action before executing the function.

### Example of trailing execution in debounce:

```javascript
function debounce(func, delay, trailing = true) {
  let timeoutId;
  return function(...args) {
    clearTimeout(timeoutId);
    timeoutId = setTimeout(() => {
      if (trailing) {
        func.apply(this, args);
      }
      timeoutId = null;
    }, delay);
  };
}

// Example usage
const handleInput = (event) => {
  console.log(`Input value: ${event.target.value}`);
};

const debouncedInput = debounce(handleInput, 300, true);
document.getElementById('inputField').addEventListener('input', debouncedInput);
```

## Cancelable debounce
A cancelable debounce is an enhancement of the standard debounce function that allows you to cancel the pending execution of the debounced function. This can be useful in scenarios where you want to provide the ability to stop the function from being called if certain conditions are met, such as when a user navigates away from a page or cancels an action.

### Example of cancelable debounce:

```javascript
function debounce(func, delay) {
  let timeoutId;
  const debouncedFunction = function(...args) {
    clearTimeout(timeoutId);
    timeoutId = setTimeout(() => {
      func.apply(this, args);
    }, delay);
  };

  debouncedFunction.cancel = function() {
    clearTimeout(timeoutId);
    timeoutId = null;
  };

  return debouncedFunction;
}

// Example usage
const handleInput = (event) => {
  console.log(`Input value: ${event.target.value}`);
};

const debouncedInput = debounce(handleInput, 300);
document.getElementById('inputField').addEventListener('input', debouncedInput);

// To cancel the debounced function
debouncedInput.cancel();
```

## Cancelable throttle
A cancelable throttle is an enhancement of the standard throttle function that allows you to cancel the pending execution of the throttled function. This can be useful in scenarios where you want to provide the ability to stop the function from being called if certain conditions are met, such as when a user navigates away from a page or cancels an action.

### Example of cancelable throttle:

```javascript
function throttle(func, limit) {
  let lastFunc;
  let lastRan;
  const throttledFunction = function(...args) {
    if (!lastRan) {
      func.apply(this, args);
      lastRan = Date.now();
    } else {
      clearTimeout(lastFunc);
      lastFunc = setTimeout(() => {
        if ((Date.now() - lastRan) >= limit) {
          func.apply(this, args);
          lastRan = Date.now();
        }
      }, limit - (Date.now() - lastRan));
    }
  };

  throttledFunction.cancel = function() {
    clearTimeout(lastFunc);
    lastFunc = null;
    lastRan = null;
  };

  return throttledFunction;
}

// Example usage
const handleScroll = () => {
  console.log('Scroll event handled');
};

const throttledScroll = throttle(handleScroll, 200);
window.addEventListener('scroll', throttledScroll);

// To cancel the throttled function
throttledScroll.cancel();
```

# Execution Context & JavaScript Internals

## Execution Context
In JavaScript, an execution context is an abstract concept that represents the environment in which code is executed. It contains information about the variables, functions, and the value of `this` that are accessible during the execution of a particular piece of code. There are three main types of execution contexts in JavaScript: global, function, and eval.

### Example of execution context:

```javascript
// Global execution context
var globalVar = 'I am a global variable';

function myFunction() {
  // Function execution context
  var localVar = 'I am a local variable';
  console.log(globalVar); // Accessible
  console.log(localVar); // Accessible
}

myFunction();
console.log(globalVar); // Accessible

// console.log(localVar); // Unaccessible, will throw an error
```

## Global Execution Context
The global execution context is the default or base context in which JavaScript code runs. It is created when the JavaScript engine starts executing code and is associated with the global object (e.g., `window` in browsers or `global` in Node.js). The global execution context is created only once during the lifetime of the application and remains active until the program terminates.

### Example of global execution context:

```javascript
var globalVar = 'I am a global variable';
function myFunction() {
  console.log(globalVar); // Accessible
}

myFunction();
console.log(globalVar); // Accessible
```

## Function Execution Context
The function execution context is created whenever a function is invoked. Each time a function is called, a new execution context is created for that function, which contains its own variable environment, scope chain, and `this` value. The function execution context is pushed onto the execution stack and popped off when the function completes execution.

### Example of function execution context:

```javascript
function myFunction() {
  var localVar = 'I am a local variable';
  console.log(localVar); // Accessible
}

myFunction();
// console.log(localVar); // Unaccessible, will throw an error
```

## Creation Phase
The creation phase is the first phase of the execution context lifecycle. During this phase, the JavaScript engine sets up the execution context by creating the variable environment, hoisting function declarations, and determining the value of `this`. In this phase, variables are initialized to `undefined`, and functions are fully hoisted, making them available for use before their actual declaration in the code.

### Example of creation phase:

```javascript
function myFunction() {
  console.log(myVar); // Output: undefined (variable is hoisted)
  var myVar = 'I am a local variable';
  console.log(myVar); // Output: I am a local variable
}

myFunction();
```

## Execution Phase
The execution phase is the second phase of the execution context lifecycle. During this phase, the JavaScript engine executes the code line by line, assigning values to variables and executing functions. The execution phase follows the creation phase, and it is during this phase that the actual logic of the code is carried out.

### Example of execution phase:

```javascript
function myFunction() {
  var myVar = 'I am a local variable';
  console.log(myVar); // Output: I am a local variable
}

myFunction();
```

## Lexical Environment
A lexical environment is a data structure that holds the variable bindings and the scope chain for a particular execution context. It consists of an environment record, which stores the variables and their values, and a reference to the outer lexical environment, allowing for scope resolution. Lexical environments are created during the creation phase of the execution context and are used to determine variable accessibility and scope.

### Example of lexical environment:

```javascript
function outerFunction() {
  var outerVar = 'I am from the outer function';

  function innerFunction() {
    var innerVar = 'I am from the inner function';
    console.log(outerVar); // Accessible due to lexical scoping
    console.log(innerVar); // Accessible
  }

  innerFunction();
  // console.log(innerVar); // Unaccessible, will throw an error
}

outerFunction();
```

## Variable Environment
The variable environment is a component of the lexical environment that specifically holds the variable bindings for a particular execution context. It keeps track of the variables declared within the context, their values, and their scope. The variable environment is created during the creation phase of the execution context and is used to resolve variable references during the execution phase.

### Example of variable environment:

```javascript
function myFunction() {
  var localVar = 'I am a local variable';
  console.log(localVar); // Accessible
}

myFunction();
// console.log(localVar); // Unaccessible, will throw an error
```

## Environment records
An environment record is a data structure that stores the variable bindings and their values for a particular lexical environment. It is part of the lexical environment and is responsible for keeping track of the variables declared within that environment. Environment records can be of different types, such as declarative environment records (for variables and functions) and object environment records (for objects).

### Example of environment records:

```javascript
function myFunction() {
  var localVar = 'I am a local variable';
  console.log(localVar); // Accessible
}

myFunction();
// console.log(localVar); // Unaccessible, will throw an error
```

## Scope Chain
The scope chain is a mechanism in JavaScript that determines the accessibility of variables and functions based on their lexical scope. It is created during the creation phase of the execution context and consists of a chain of lexical environments, starting from the current execution context and extending outward to the global execution context. When a variable is referenced, JavaScript looks for it in the current lexical environment and, if not found, continues searching up the scope chain until it reaches the global scope.

### Example of scope chain:

```javascript
function outerFunction() {
  var outerVar = 'I am from the outer function';

  function innerFunction() {
    var innerVar = 'I am from the inner function';
    console.log(outerVar); // Accessible due to scope chain
    console.log(innerVar); // Accessible
  }

  innerFunction();
  // console.log(innerVar); // Unaccessible, will throw an error
}

outerFunction();
```

## Hoisting
Hoisting is a JavaScript mechanism where variable and function declarations are moved to the top of their containing scope during the creation phase of the execution context. This means that variables and functions can be referenced before they are declared in the code. However, only the declarations are hoisted, not the initializations. Variables declared with `var` are hoisted and initialized to `undefined`, while function declarations are hoisted with their entire definition.

### Example of hoisting:

```javascript
console.log(myVar); // Output: undefined (variable is hoisted)
var myVar = 'I am a variable';

console.log(myFunction()); // Output: I am a function (function is hoisted)
function myFunction() {
  return 'I am a function';
}
```

## Function Hoisting
Function hoisting is a specific aspect of hoisting in JavaScript where function declarations are moved to the top of their containing scope during the creation phase of the execution context. This allows functions to be called before they are defined in the code. Function hoisting applies only to function declarations, not function expressions or arrow functions.

### Example of function hoisting:

```javascript
console.log(myFunction()); // Output: I am a function (function is hoisted)
function myFunction() {
  return 'I am a function';
}

```

## Variable Hoisting
Variable hoisting is a specific aspect of hoisting in JavaScript where variable declarations are moved to the top of their containing scope during the creation phase of the execution context. Variables declared with `var` are hoisted and initialized to `undefined`, while variables declared with `let` and `const` are hoisted but not initialized, resulting in a "temporal dead zone" where they cannot be accessed until they are explicitly initialized.

### Example of variable hoisting:

```javascript
console.log(myVar); // Output: undefined (variable is hoisted)
var myVar = 'I am a variable';

console.log(myLet); // ReferenceError: Cannot access 'myLet' before initialization
let myLet = 'I am a let variable';

console.log(myConst); // ReferenceError: Cannot access 'myConst' before initialization
const myConst = 'I am a const variable';
```

## Temporal Dead Zone (TDZ)
The Temporal Dead Zone (TDZ) is a behavior in JavaScript that occurs when variables declared with `let` or `const` are accessed before they are initialized. During the TDZ, the variables exist in the scope but cannot be accessed, resulting in a `ReferenceError`. The TDZ helps prevent the use of uninitialized variables and encourages better coding practices.

### Example of Temporal Dead Zone (TDZ):

```javascript
console.log(myLet); // ReferenceError: Cannot access 'myLet' before initialization
let myLet = 'I am a let variable';

console.log(myConst); // ReferenceError: Cannot access 'myConst' before initialization
const myConst = 'I am a const variable';
```

## Call Stack
The call stack is a data structure used by the JavaScript engine to keep track of function calls. It operates on a Last In, First Out (LIFO) principle, where the most recently called function is at the top of the stack. When a function is called, it is pushed onto the call stack, and when it returns, it is popped off the stack. The call stack helps manage the execution context and keeps track of the order in which functions are executed.

### Example of call stack:

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
// Output:
// First function called
// Second function called
// Third function called
```

## Heap Memory
Heap memory is a region of memory used for dynamic memory allocation in JavaScript. It is where objects, arrays, and functions are stored. Unlike the call stack, which has a fixed size and operates in a LIFO manner, heap memory is more flexible and allows for the allocation of memory for objects of varying sizes. The JavaScript engine manages heap memory through garbage collection, automatically reclaiming memory that is no longer in use.

### Example of heap memory:

```javascript
// Example of heap memory allocation
const person = {
  name: 'Alice',
  age: 30,
  greet() {
    console.log(`Hello, my name is ${this.name}`);
  }
};

person.greet(); // Output: Hello, my name is Alice
```

## Garbage Collection
Garbage collection is an automatic memory management process in JavaScript that identifies and frees up memory occupied by objects that are no longer reachable or needed by the program. The JavaScript engine uses algorithms to track object references and determine when an object can be safely removed from memory. This helps prevent memory leaks and ensures efficient use of memory resources.

### Example of garbage collection:

```javascript
function createPerson(name) {
  return {
    name,
    greet() {
      console.log(`Hello, my name is ${this.name}`);
    }
  };
}

let person1 = createPerson('Bob');
person1.greet(); // Output: Hello, my name is Bob

// person1 is no longer needed
person1 = null; // The object is now eligible for garbage collection
```

## Memory Management
Memory management in JavaScript involves the allocation and deallocation of memory for variables, objects, and functions. The JavaScript engine automatically handles memory management through garbage collection, which identifies and frees up memory occupied by objects that are no longer reachable. Developers can also optimize memory usage by avoiding unnecessary object creation, using closures wisely, and managing references to large data structures.

### Example of memory management:

```javascript
function createLargeObject() {
  const largeObject = new Array(1000000).fill('data');
  return largeObject;
}

let myObject = createLargeObject();
// Use myObject for some operations

// When done, set it to null to allow garbage collection
myObject = null; // The large object is now eligible for garbage collection
```

## Event Loop
The event loop is a fundamental concept in JavaScript that enables asynchronous programming. It is responsible for managing the execution of code, handling events, and executing queued tasks. The event loop continuously checks the call stack and the task queue, executing tasks from the queue when the call stack is empty. This allows JavaScript to perform non-blocking operations, such as handling user interactions or making API requests, while still maintaining a single-threaded execution model.

### Example of event loop:

```javascript
console.log('Start');

setTimeout(() => {
  console.log('Timeout callback');
}, 0);

console.log('End');
// Output:
// Start
// End
// Timeout callback
```

## Microtasks and Macrotasks
In JavaScript, the event loop manages two types of tasks: microtasks and macrotasks. Microtasks are tasks that are executed after the current operation completes and before the next event loop iteration. They include promises and mutation observers. Macrotasks, on the other hand, are tasks that are executed in the next event loop iteration and include setTimeout, setInterval, and I/O operations.

### Example of microtasks and macrotasks:

```javascript
console.log('Start');

setTimeout(() => {
  console.log('Macrotask: setTimeout');
}, 0);

Promise.resolve().then(() => {
  console.log('Microtask: Promise');
});

console.log('End');
// Output:
// Start
// End
// Microtask: Promise
// Macrotask: setTimeout

```

## Call Stack vs Event Loop
The call stack and the event loop are two fundamental components of JavaScript's execution model, but they serve different purposes. The call stack is a data structure that keeps track of function calls and their execution contexts, operating in a Last In, First Out (LIFO) manner. It manages the synchronous execution of code. The event loop, on the other hand, is responsible for handling asynchronous operations by managing the execution of tasks from the task queue and ensuring that the call stack is empty before executing queued tasks.

### Example of call stack vs event loop:

```javascript
console.log('Start');

setTimeout(() => {
  console.log('Macrotask: setTimeout');
}, 0);

Promise.resolve().then(() => {
  console.log('Microtask: Promise');
});

console.log('End');
// Output:
// Start
// End
// Microtask: Promise
// Macrotask: setTimeout
```

# Event Loop - Deep Dive

## Call Stack
The call stack is a data structure used by the JavaScript engine to keep track of function calls. It operates on a Last In, First Out (LIFO) principle, where the most recently called function is at the top of the stack. When a function is called, it is pushed onto the call stack, and when it returns, it is popped off the stack. The call stack helps manage the execution context and keeps track of the order in which functions are executed.

### Example of call stack:

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
// Output:
// First function called
// Second function called
// Third function called
```

## Web APIs
Web APIs are a set of APIs provided by the browser that allow JavaScript to interact with the browser environment and perform tasks such as making HTTP requests, manipulating the DOM, handling events, and working with multimedia. These APIs are not part of the JavaScript language itself but are accessible through the global `window` object in the browser. Web APIs enable developers to create rich, interactive web applications.

### Example of Web APIs:

```javascript
// Example of using the Fetch API to make an HTTP request
fetch('https://api.example.com/data')
  .then(response => response.json())
  .then(data => {
    console.log('Data received:', data);
  })
  .catch(error => {
    console.error('Error fetching data:', error);
  });
```

## Example of Web APIs Event Loop

```javascript
console.log('Start');

setTimeout(() => {
  console.log('Timeout callback');
}, 0);

Promise.resolve().then(() => {
  console.log('Promise callback');
});

console.log('End');
// Output:
// Start
// End
// Promise callback
// Timeout callback
```

## Macrotasks and Microtasks
In JavaScript, the event loop manages two types of tasks: macrotasks and microtasks. Macrotasks are tasks that are executed in the next event loop iteration and include operations such as `setTimeout`, `setInterval`, and I/O operations. Microtasks, on the other hand, are tasks that are executed after the current operation completes and before the next event loop iteration. They include promises and mutation observers. The event loop ensures that microtasks are executed before macrotasks, allowing for more efficient handling of asynchronous operations.

### Example of macrotasks and microtasks:

```javascript
console.log('Start');

setTimeout(() => {
  console.log('Macrotask: setTimeout');
}, 0);

Promise.resolve().then(() => {
  console.log('Microtask: Promise');
});

console.log('End');
// Output:
// Start
// End
// Microtask: Promise
// Macrotask: setTimeout
```

## `setTimeout` and `setInterval`
`setTimeout` and `setInterval` are two commonly used functions in JavaScript for scheduling tasks to be executed after a specified delay or at regular intervals, respectively. `setTimeout` executes a function once after the specified delay, while `setInterval` executes a function repeatedly at the specified interval until it is cleared.

### Example of `setTimeout` and `setInterval`:

```javascript
// Example of setTimeout
setTimeout(() => {
  console.log('This message is displayed after 2 seconds');
}, 2000);

// Example of setInterval
const intervalId = setInterval(() => {
  console.log('This message is displayed every 1 second');
}, 1000);

// To stop the interval after 5 seconds
setTimeout(() => {
  clearInterval(intervalId);
  console.log('Interval cleared');
}, 5000);
```

## Promises and the Event Loop
Promises are a way to handle asynchronous operations in JavaScript. They represent a value that may be available now, in the future, or never. Promises have three states: pending, fulfilled, and rejected. When a promise is fulfilled or rejected, it triggers the execution of the corresponding `.then()` or `.catch()` handlers. The event loop ensures that promise callbacks are executed as microtasks, allowing them to run before the next macrotask.

### Example of promises and the event loop:

```javascript
console.log('Start');

const promise = new Promise((resolve, reject) => {
  setTimeout(() => {
    resolve('Promise resolved');
  }, 1000);
});

promise.then((message) => {
  console.log(message);
});

console.log('End');
// Output:
// Start
// End
// Promise resolved (after 1 second)
```

## queueMicrotask()
The `queueMicrotask()` function is a method in JavaScript that allows you to schedule a microtask to be executed after the current operation completes and before the next event loop iteration. It is similar to using promises, but it provides a more direct way to queue microtasks without creating a new promise. Microtasks are executed before macrotasks, allowing for efficient handling of asynchronous operations.

### Example of `queueMicrotask()`:

```javascript
console.log('Start');

queueMicrotask(() => {
  console.log('Microtask executed');
});

console.log('End');
// Output:
// Start
// End
// Microtask executed
```

## async/await and the Event Loop
The `async/await` syntax in JavaScript is a way to work with promises in a more synchronous-looking manner. An `async` function returns a promise, and the `await` keyword can be used to pause the execution of the function until the promise is resolved or rejected. The event loop ensures that the code after the `await` statement is executed as a microtask, allowing for efficient handling of asynchronous operations.

### Example of async/await and the event loop:

```javascript
async function fetchData() {
  console.log('Fetching data...');
  const response = await fetch('https://api.example.com/data');
  const data = await response.json();
  console.log('Data received:', data);
}

fetchData();
console.log('End');
// Output:
// Fetching data...
// End
// Data received: { ... } (after the fetch is complete)
```

## Execution Order
The execution order in JavaScript is determined by the call stack, event loop, and the types of tasks (synchronous, macrotasks, and microtasks). Synchronous code is executed first, followed by microtasks (such as promise callbacks), and then macrotasks (such as `setTimeout` callbacks). This order ensures that the JavaScript engine can handle asynchronous operations efficiently while maintaining a single-threaded execution model.

### Example of execution order:

```javascript
console.log('Start');

setTimeout(() => {
  console.log('Macrotask: setTimeout');
}, 0);

Promise.resolve().then(() => {
  console.log('Microtask: Promise');
});

console.log('End');
// Output:
// Start
// End
// Microtask: Promise
// Macrotask: setTimeout
```

## Event loop interview problems
Here are some common interview problems related to the event loop in JavaScript:

### Problem 1: Predict the output

```javascript
console.log('Start');
setTimeout(() => {
  console.log('Timeout callback');
}, 0);

Promise.resolve().then(() => {
  console.log('Promise callback');
});

console.log('End');
```
**Expected Output:**
```
Start
End
Promise callback
Timeout callback
```
### Problem 2: Understanding async/await

```javascript
async function asyncFunction() {
  console.log('Async function start');
  await new Promise(resolve => setTimeout(resolve, 1000));
  console.log('Async function end');
}

asyncFunction();
console.log('After async function');
```
**Expected Output:**
```
Async function start
After async function
Async function end
```

### Problem 3: Event loop with multiple promises

```javascript
console.log('Start');
Promise.resolve().then(() => {
  console.log('Promise 1');
  return Promise.resolve();
}).then(() => {
  console.log('Promise 2');
});

console.log('End');
```
**Expected Output:**
```
Start
End
Promise 1
Promise 2
```

# Prototypes

## Prototype Objects
In JavaScript, every object has an internal property called `[[Prototype]]`, which refers to another object. This prototype object serves as a blueprint for the original object, allowing it to inherit properties and methods from the prototype. The prototype chain is a mechanism that enables objects to share behavior and functionality, promoting code reuse and modularity.

### Example of prototype objects:

```javascript
function Person(name, age) {
  this.name = name;
  this.age = age;
}

Person.prototype.greet = function() {
  console.log(`Hello, my name is ${this.name} and I am ${this.age} years old.`);
};

const person1 = new Person('Alice', 30);
person1.greet(); // Output: Hello, my name is Alice and I am 30 years old.
```

## Prototype inheritance
Prototype inheritance in JavaScript is a mechanism that allows objects to inherit properties and methods from other objects through the prototype chain. When a property or method is accessed on an object, JavaScript first looks for it on the object itself. If it is not found, it traverses up the prototype chain to find the property or method in the prototype objects. This enables objects to share behavior and functionality, promoting code reuse.

### Example of prototype inheritance:

```javascript
function Animal(name) {
  this.name = name;
}

Animal.prototype.speak = function() {
  console.log(`${this.name} makes a sound.`);
};

function Dog(name) {
  Animal.call(this, name);
}

Dog.prototype = Object.create(Animal.prototype);
Dog.prototype.constructor = Dog;

Dog.prototype.bark = function() {
  console.log(`${this.name} barks.`);
};

const dog = new Dog('Buddy');
dog.speak(); // Output: Buddy makes a sound.

dog.bark(); // Output: Buddy barks.
```

## Prototype chain
The prototype chain is a hierarchical structure in JavaScript that allows objects to inherit properties and methods from other objects through their prototypes. When a property or method is accessed on an object, JavaScript first checks if it exists on the object itself. If not, it looks up the prototype chain, checking each prototype in turn until it either finds the property or reaches the end of the chain (the `null` prototype). This mechanism enables inheritance and code reuse in JavaScript.

### Example of prototype chain:

```javascript
function Vehicle(type) {
  this.type = type;
}

Vehicle.prototype.start = function() {
  console.log(`${this.type} is starting.`);
};

function Car(brand) {
  Vehicle.call(this, 'Car');
  this.brand = brand;
}

Car.prototype = Object.create(Vehicle.prototype);
Car.prototype.constructor = Car;

Car.prototype.drive = function() {
  console.log(`${this.brand} is driving.`);
};

const myCar = new Car('Toyota');
myCar.start(); // Output: Car is starting.

myCar.drive(); // Output: Toyota is driving.
```

## Constructor prototype
In JavaScript, every constructor function has a `prototype` property that points to an object. This prototype object is used to define properties and methods that should be shared among all instances created by that constructor. When a new instance is created using the `new` keyword, it inherits properties and methods from the constructor's prototype, allowing for efficient memory usage and code reuse.

### Example of constructor prototype:

```javascript
function Person(name, age) {
  this.name = name;
  this.age = age;
}

Person.prototype.greet = function() {
  console.log(`Hello, my name is ${this.name} and I am ${this.age} years old.`);
};

const person1 = new Person('Alice', 30);
person1.greet(); // Output: Hello, my name is Alice and I am 30 years old.
const person2 = new Person('Bob', 25);
person2.greet(); // Output: Hello, my name is Bob and I am 25 years old.
```

## Instance prototype
In JavaScript, every object instance has an internal property called `[[Prototype]]`, which points to the prototype object of its constructor. This instance prototype allows the object to inherit properties and methods from its constructor's prototype. When a property or method is accessed on an instance, JavaScript first checks the instance itself, and if it doesn't find it, it looks up the prototype chain to find it in the constructor's prototype.

### Example of instance prototype:

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

## prototype
the `prototype` property in JavaScript is a special property of constructor functions that points to an object. This object serves as a blueprint for instances created by the constructor, allowing them to inherit properties and methods defined on the prototype. When a new instance is created using the `new` keyword, it has access to the properties and methods defined on the constructor's prototype through the prototype chain.

### Example of `prototype` property:

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

## __proto__
The `__proto__` property in JavaScript is an internal property of an object that points to the prototype object from which the object inherits properties and methods. It allows access to the prototype chain, enabling objects to share behavior and functionality. The `__proto__` property is not part of the official ECMAScript standard, but it is widely supported in modern browsers. It is often used for debugging and exploring the prototype chain.

### Example of `__proto__` property:

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

## Object.create()
The `Object.create()` method in JavaScript is used to create a new object with the specified prototype object and properties. It allows for the creation of objects that inherit from a given prototype, enabling prototype-based inheritance. The first argument to `Object.create()` is the prototype object, and the second optional argument is an object containing property descriptors for the new object.

### Example of `Object.create()`:

```javascript
const animal = {
  speak() {
    console.log(`${this.name} makes a sound.`);
  }
};

const dog = Object.create(animal);
dog.name = 'Buddy';
dog.speak(); // Output: Buddy makes a sound.
```

## Shadowing
The `shadowing` in JavaScript refers to the situation where a variable declared within a certain scope (e.g., a function or block) has the same name as a variable declared in an outer scope. In such cases, the inner variable "shadows" or overrides the outer variable within its scope, making the outer variable inaccessible until the inner scope is exited.

### Example of shadowing:

```javascript
var outerVar = 'I am an outer variable';

function myFunction() {
  var outerVar = 'I am an inner variable'; // This shadows the outer variable
  console.log(outerVar); // Output: I am an inner variable
}

myFunction();
console.log(outerVar); // Output: I am an outer variable
```

## Property lookup
Property lookup in JavaScript refers to the process of searching for a property on an object. When a property is accessed on an object, JavaScript first checks if the property exists directly on the object. If it does not find the property, it looks up the prototype chain to find the property in the object's prototype or any of its ancestors. This process continues until the property is found or the end of the prototype chain is reached (i.e., `null`).

### Example of property lookup:

```javascript
function Animal(name) {
  this.name = name;
}

Animal.prototype.speak = function() {
  console.log(`${this.name} makes a sound.`);
};

function Dog(name) {
  Animal.call(this, name);
}

Dog.prototype = Object.create(Animal.prototype);
Dog.prototype.constructor = Dog;

Dog.prototype.bark = function() {
  console.log(`${this.name} barks.`);
};

const dog = new Dog('Buddy');
dog.speak(); // Output: Buddy makes a sound. (property lookup finds speak in Animal prototype)
dog.bark(); // Output: Buddy barks. (property lookup finds bark in Dog prototype)
```

## Built-in Prototypes
In JavaScript, built-in prototypes refer to the prototype objects associated with native JavaScript constructors, such as `Object`, `Array`, `Function`, `String`, and others. These built-in prototypes provide a set of methods and properties that are available to all instances created from the corresponding constructors. For example, the `Array.prototype` provides methods like `push`, `pop`, and `map`, while the `String.prototype` provides methods like `toUpperCase` and `substring`. Built-in prototypes enable developers to work with native JavaScript types more effectively by providing a rich set of functionalities.

### Example of built-in prototypes:

```javascript
const myArray = [1, 2, 3];
// Using built-in prototype methods

myArray.push(4); // Adds 4 to the end of the array
console.log(myArray); // Output: [1, 2, 3, 4]

const myString = 'hello';
// Using built-in prototype methods

console.log(myString.toUpperCase()); // Output: HELLO
```

## Extending Prototypes
In JavaScript, extending prototypes refers to the practice of adding new properties or methods to the prototype of a constructor function or a built-in object. This allows all instances created from that constructor or object to inherit the new properties or methods, enabling code reuse and enhancing functionality. However, extending built-in prototypes is generally discouraged, as it can lead to conflicts and unexpected behavior in the code.

### Example of extending prototypes:

```javascript
function Person(name, age) {
  this.name = name;
  this.age = age;
}

Person.prototype.greet = function() {
  console.log(`Hello, my name is ${this.name} and I am ${this.age} years old.`);
};

const person1 = new Person('Alice', 30);
// Extending the Person prototype

Person.prototype.sayGoodbye = function() {
  console.log(`Goodbye from ${this.name}`);
};

person1.greet(); // Output: Hello, my name is Alice and I am 30 years old.
person1.sayGoodbye(); // Output: Goodbye from Alice
```

## prototype vs class
In JavaScript, both `prototype` and `class` are used to create objects and define their behavior, but they have different syntaxes and underlying mechanisms.

- **Prototype**: The prototype-based approach uses constructor functions and the `prototype` property to define methods and properties that are shared among instances. It relies on the prototype chain for inheritance.

- **Class**: The class-based approach, introduced in ES6, provides a more concise and familiar syntax for creating objects and defining their behavior. Classes are syntactic sugar over the prototype-based inheritance model, making it easier to work with object-oriented programming concepts.

### Example of prototype vs class:

```javascript
// Using prototype
function Person(name, age) {
  this.name = name;
  this.age = age;
}

Person.prototype.greet = function() {
  console.log(`Hello, my name is ${this.name} and I am ${this.age} years old.`);
};

// Using class
class PersonClass {
  constructor(name, age) {
    this.name = name;
    this.age = age;
  }

  greet() {
    console.log(`Hello, my name is ${this.name} and I am ${this.age} years old.`);
  }
}

const person1 = new Person('Alice', 30);
const person2 = new PersonClass('Bob', 25);

person1.greet(); // Output: Hello, my name is Alice and I am 30 years old.
person2.greet(); // Output: Hello, my name is Bob and I am 25 years old.
```

# Iterators & Generators

## Iterable
the `Iterable` in JavaScript is an object that implements the `@@iterator` method, which allows it to be iterated over using constructs like `for...of` loops. An iterable object must have a method with the key `Symbol.iterator`, which returns an iterator object. This iterator object must have a `next()` method that returns an object with two properties: `value` (the next value in the sequence) and `done` (a boolean indicating whether the iteration is complete).

### Example of iterable:

```javascript
const myIterable = {
  [Symbol.iterator]: function() {
    let step = 0;
    return {
      next: function() {
        step++;
        if (step === 1) {
          return { value: 'Hello', done: false };
        } else if (step === 2) {
          return { value: 'World', done: false };
        }
        return { value: undefined, done: true };
      }
    };
  }
};

for (const value of myIterable) {
  console.log(value);
}

// Output:
// Hello
// World
```

## Iterator
An `Iterator` in JavaScript is an object that provides a way to access elements of a collection one at a time. It implements the `next()` method, which returns an object with two properties: `value` (the next value in the sequence) and `done` (a boolean indicating whether the iteration is complete). Iterators are typically used in conjunction with iterable objects, allowing for controlled traversal of data structures.

### Example of iterator:

```javascript
const myIterable = {
  [Symbol.iterator]: function() {
    let step = 0;
    return {
      next: function() {
        step++;
        if (step === 1) {
          return { value: 'Hello', done: false };
        } else if (step === 2) {
          return { value: 'World', done: false };
        }
        return { value: undefined, done: true };
      }
    };
  }
};

for (const value of myIterable) {
  console.log(value);
}

// Output:
// Hello
// World
```

## Iterator protocol
The `Iterator Protocol` in JavaScript defines a standard way for objects to produce a sequence of values. An object that adheres to the iterator protocol must implement a `next()` method that returns an object with two properties: `value` (the next value in the sequence) and `done` (a boolean indicating whether the iteration is complete). This protocol allows for consistent iteration over different data structures, enabling the use of constructs like `for...of` loops.

### Example of iterator protocol:

```javascript
const myIterable = {
  [Symbol.iterator]: function() {
    let step = 0;
    return {
      next: function() {
        step++;
        if (step === 1) {
          return { value: 'Hello', done: false };
        } else if (step === 2) {
          return { value: 'World', done: false };
        }
        return { value: undefined, done: true };
      }
    };
  }
};

for (const value of myIterable) {
  console.log(value);
}

// Output:
// Hello
// World
```

## `Symbol.iterator`
The `Symbol.iterator` is a built-in symbol in JavaScript that specifies the default iterator for an object. It is used to define how an object should be iterated over, allowing it to be compatible with constructs like `for...of` loops and the spread operator. When an object has a method keyed by `Symbol.iterator`, it can produce an iterator that adheres to the iterator protocol, enabling controlled traversal of its elements.

### Example of `Symbol.iterator`:

```javascript
const myIterable = {
  [Symbol.iterator]: function() {
    let step = 0;
    return {
      next: function() {
        step++;
        if (step === 1) {
          return { value: 'Hello', done: false };
        } else if (step === 2) {
          return { value: 'World', done: false };
        }
        return { value: undefined, done: true };
      }
    };
  }
};

for (const value of myIterable) {
  console.log(value);
}

// Output:
// Hello
// World
```

## `next()`
The `next()` method is a fundamental part of the iterator protocol in JavaScript. It is used to retrieve the next value from an iterator object. When called, `next()` returns an object with two properties: `value`, which represents the next value in the sequence, and `done`, a boolean indicating whether the iteration is complete. If `done` is `true`, it means there are no more values to iterate over.

### Example of `next()` method:

```javascript
const myIterable = {
  [Symbol.iterator]: function() {
    let step = 0;
    return {
      next: function() {
        step++;
        if (step === 1) {
          return { value: 'Hello', done: false };
        } else if (step === 2) {
          return { value: 'World', done: false };
        }
        return { value: undefined, done: true };
      }
    };
  }
};

const iterator = myIterable[Symbol.iterator]();
console.log(iterator.next()); // Output: { value: 'Hello', done: false }
console.log(iterator.next()); // Output: { value: 'World', done: false }
console.log(iterator.next()); // Output: { value: undefined, done: true }
```

## Generator fuctions
Generator functions in JavaScript are a special type of function that can be paused and resumed, allowing for the generation of a sequence of values over time. They are defined using the `function*` syntax and use the `yield` keyword to produce values. When a generator function is called, it returns an iterator object that can be used to control the execution of the function and retrieve values one at a time.

### Example of generator functions:

```javascript
function* myGenerator() {
  yield 'Hello';
  yield 'World';
  return 'Done';
}

const generator = myGenerator();
console.log(generator.next()); // Output: { value: 'Hello', done: false }

console.log(generator.next()); // Output: { value: 'World', done: false }

console.log(generator.next()); // Output: { value: 'Done', done: true }
console.log(generator.next()); // Output: { value: undefined, done: true }
```

## `yield`
The `yield` keyword in JavaScript is used within generator functions to pause the execution of the function and produce a value. When a generator function is called, it returns an iterator object, and each call to the `next()` method on that iterator resumes the execution of the generator function until it reaches the next `yield` statement. The value provided to `yield` becomes the value returned by the `next()` method, and the generator can be resumed later to continue execution.

### Example of `yield`:

```javascript
function* myGenerator() {
  yield 'Hello';
  yield 'World';
  return 'Done';
}

const generator = myGenerator();
console.log(generator.next()); // Output: { value: 'Hello', done: false }

console.log(generator.next()); // Output: { value: 'World', done: false }

console.log(generator.next()); // Output: { value: 'Done', done: true }

console.log(generator.next()); // Output: { value: undefined, done: true }
```

## Generator delegation
Generator delegation in JavaScript allows one generator function to delegate part of its iteration process to another generator function. This is achieved using the `yield*` expression, which delegates control to another generator or iterable object. When a generator function uses `yield*`, it will yield all values from the delegated generator or iterable, effectively flattening the iteration process. This feature enables modular and reusable generator functions.

### Example of generator delegation:

```javascript
function* innerGenerator() {
  yield 'Inner 1';
  yield 'Inner 2';
}

function* outerGenerator() {
  yield 'Outer 1';
  yield* innerGenerator(); // Delegating to innerGenerator
  yield 'Outer 2';
}

const generator = outerGenerator();
console.log(generator.next()); // Output: { value: 'Outer 1', done: false }
console.log(generator.next()); // Output: { value: 'Inner 1', done: false }
console.log(generator.next()); // Output: { value: 'Inner 2', done: false }
console.log(generator.next()); // Output: { value: 'Outer 2', done: false }
console.log(generator.next()); // Output: { value: undefined, done: true }
```

## Async Iterators
Async iterators in JavaScript are a type of iterator that allows for asynchronous iteration over a collection of values. They are defined using the `async function*` syntax and use the `for await...of` loop to iterate over asynchronous data sources, such as streams or APIs. Async iterators return promises for each value, allowing for non-blocking operations and enabling developers to work with asynchronous data in a more natural way.

### Example of async iterators:

```javascript
async function* asyncGenerator() {
  yield await Promise.resolve('Hello');
  yield await Promise.resolve('World');
}

(async () => {
  for await (const value of asyncGenerator()) {
    console.log(value);
  }
})();

// Output:
// Hello
// World
```

## `for await...of`
The `for await...of` loop in JavaScript is a control flow statement that allows for asynchronous iteration over an async iterable object. It is used to iterate over values produced by an async iterator, where each value is a promise that resolves to the actual value. The loop automatically waits for each promise to resolve before moving on to the next iteration, making it easier to work with asynchronous data sources.

### Example of `for await...of`:

```javascript
async function* asyncGenerator() {
  yield await Promise.resolve('Hello');
  yield await Promise.resolve('World');
}

(async () => {
  for await (const value of asyncGenerator()) {
    console.log(value);
  }
})();

// Output:
// Hello
// World
```

# Map, Set & Weak Collections

## Map
A `Map` in JavaScript is a collection of key-value pairs where both keys and values can be of any data type. Unlike regular objects, which only allow strings and symbols as keys, a `Map` allows for more flexibility in key types. Maps maintain the order of insertion and provide methods for adding, retrieving, and deleting key-value pairs. They are particularly useful when you need to associate values with unique keys and require efficient lookups.

### Example of Map:

```javascript
const myMap = new Map();
// Adding key-value pairs

myMap.set('name', 'Alice');
myMap.set('age', 30);

// Retrieving values
console.log(myMap.get('name')); // Output: Alice
console.log(myMap.get('age')); // Output: 30

// Checking for existence of a key
console.log(myMap.has('name')); // Output: true

// Deleting a key-value pair
myMap.delete('age');
console.log(myMap.has('age')); // Output: false

// Iterating over a Map
for (const [key, value] of myMap) {
  console.log(`${key}: ${value}`);
}
// Output:
// name: Alice
```

## Map keys
In JavaScript, the keys of a `Map` can be of any data type, including objects, functions, and primitive values. This flexibility allows for more complex key-value associations compared to regular objects, which only allow strings and symbols as keys. The `Map` maintains the order of insertion for its keys, making it suitable for scenarios where the order of elements matters.

### Example of Map keys:

```javascript
const myMap = new Map();
// Using different data types as keys

const objKey = { id: 1 };
myMap.set(objKey, 'Object Key');

const funcKey = function() {};
myMap.set(funcKey, 'Function Key');

const numKey = 42;
myMap.set(numKey, 'Number Key');

console.log(myMap.get(objKey)); // Output: Object Key
console.log(myMap.get(funcKey)); // Output: Function Key

console.log(myMap.get(numKey)); // Output: Number Key
```

## Map methods
In JavaScript, `Map` provides several built-in methods that allow you to manipulate and interact with the collection of key-value pairs. These methods include adding, retrieving, deleting, and checking for the existence of keys, as well as iterating over the entries in the map.

### Common Map methods:
- `set(key, value)`: Adds a new key-value pair to the map or updates the value for an existing key.

- `get(key)`: Retrieves the value associated with the specified key.

- `has(key)`: Checks if the map contains the specified key.

- `delete(key)`: Removes the key-value pair associated with the specified key.

- `clear()`: Removes all key-value pairs from the map.

- `size`: Returns the number of key-value pairs in the map.

### Example of Map methods:

```javascript
const myMap = new Map();
// Adding key-value pairs

myMap.set('name', 'Alice');
myMap.set('age', 30);

// Retrieving values
console.log(myMap.get('name')); // Output: Alice
console.log(myMap.get('age')); // Output: 30

// Checking for existence of a key
console.log(myMap.has('name')); // Output: true

// Deleting a key-value pair
myMap.delete('age');
console.log(myMap.has('age')); // Output: false

// Getting the size of the map
console.log(myMap.size); // Output: 1
// Clearing the map
myMap.clear();

console.log(myMap.size); // Output: 0
```

## Set
A `Set` in JavaScript is a collection of unique values, meaning that it cannot contain duplicate elements. Sets can store values of any data type, including primitives and objects. They provide methods for adding, deleting, and checking for the existence of values, as well as iterating over the elements in the set. Sets are particularly useful when you need to maintain a collection of distinct items.

### Example of Set:

```javascript
const mySet = new Set();

// Adding values to the set
mySet.add(1);

mySet.add(2);
mySet.add(3);

// Attempting to add a duplicate value
mySet.add(2); // This will not be added since 2 is already in the set

// Checking for existence of a value
console.log(mySet.has(2)); // Output: true

// Deleting a value from the set
mySet.delete(3);

console.log(mySet.has(3)); // Output: false

// Iterating over a Set
for (const value of mySet) {
  console.log(value);
}

// Output:
// 1
// 2
```

## Set methods
In JavaScript, `Set` provides several built-in methods that allow you to manipulate and interact with the collection of unique values. These methods include adding, deleting, checking for existence, and iterating over the elements in the set.

### Common Set methods:
- `add(value)`: Adds a new value to the set. If the value already exists, it will not be added again.

- `delete(value)`: Removes the specified value from the set.

- `has(value)`: Checks if the set contains the specified value.

- `clear()`: Removes all values from the set.

- `size`: Returns the number of unique values in the set.

### Example of Set methods:

```javascript
const mySet = new Set();

// Adding values to the set
mySet.add(1);
mySet.add(2);
mySet.add(3);

// Checking for existence of a value
console.log(mySet.has(2)); // Output: true

// Deleting a value from the set
mySet.delete(3);

console.log(mySet.has(3)); // Output: false

// Getting the size of the set
console.log(mySet.size); // Output: 2

// Clearing the set
mySet.clear();

console.log(mySet.size); // Output: 0
```

## WeakMap
A `WeakMap` in JavaScript is a collection of key-value pairs where the keys are weakly referenced objects. This means that if there are no other references to a key object, it can be garbage collected, and the corresponding entry in the `WeakMap` will be removed automatically. `WeakMap` is useful for storing private data associated with objects without preventing those objects from being garbage collected.

### Example of WeakMap:

```javascript
const weakMap = new WeakMap();
const objKey = { id: 1 };

// Adding a key-value pair to the WeakMap
weakMap.set(objKey, 'Object Key');

// Retrieving the value associated with the key
console.log(weakMap.get(objKey)); // Output: Object Key

// Deleting the key-value pair
weakMap.delete(objKey);

console.log(weakMap.get(objKey)); // Output: undefined
```

## WeakSet
A `WeakSet` in JavaScript is a collection of unique objects where the objects are weakly referenced. This means that if there are no other references to an object in the `WeakSet`, it can be garbage collected, and the corresponding entry in the `WeakSet` will be removed automatically. `WeakSet` is useful for storing a collection of objects without preventing those objects from being garbage collected.

### Example of WeakSet:

```javascript
const weakSet = new WeakSet();
const obj1 = { id: 1 };

// Adding an object to the WeakSet
weakSet.add(obj1);

// Checking for existence of the object
console.log(weakSet.has(obj1)); // Output: true

// Deleting the object from the WeakSet
weakSet.delete(obj1);

console.log(weakSet.has(obj1)); // Output: false
```

## Map vs Object
In JavaScript, both `Map` and `Object` are used to store key-value pairs, but they have different characteristics and use cases.

### Differences between Map and Object:
1. **Key Types**:
   - `Map`: Allows keys of any data type, including objects, functions, and primitives.
   - `Object`: Only allows strings and symbols as keys.

2. **Order of Elements**:
   - `Map`: Maintains the order of insertion of key-value pairs.
    - `Object`: Does not guarantee the order of properties, especially for non-integer keys.

3. **Size**:
   - `Map`: Has a `size` property that returns the number of key-value pairs.
   - `Object`: Does not have a built-in method to get the number of properties; you need to use `Object.keys(obj).length` to determine the size.

4. **Iteration**:
   - `Map`: Can be iterated using `for...of` loops, `forEach`, and other iterable methods.
   - `Object`: Can be iterated using `for...in` loops, but it requires additional methods like `Object.keys()`, `Object.values()`, or `Object.entries()` for more controlled iteration.

### Example of Map vs Object:
```javascript
// Using Map
const myMap = new Map();
myMap.set('name', 'Alice');
myMap.set(1, 'Number Key');

console.log(myMap.get('name')); // Output: Alice
console.log(myMap.get(1)); // Output: Number Key

// Using Object
const myObject = {};
myObject['name'] = 'Bob';
myObject[1] = 'Number Key';

console.log(myObject['name']); // Output: Bob
console.log(myObject[1]); // Output: Number Key
```

## Set vs Array
In JavaScript, both `Set` and `Array` are used to store collections of values, but they have different characteristics and use cases.

### Differences between Set and Array:
1. **Uniqueness**:
   - `Set`: Ensures that all values are unique; duplicate values are automatically removed.
   - `Array`: Can contain duplicate values; it allows multiple occurrences of the same value.

2. **Order of Elements**:
   - `Set`: Maintains the order of insertion of values.
    - `Array`: Maintains the order of elements based on their index.

3. **Methods**:
   - `Set`: Provides methods like `add()`, `delete()`, `has()`, and `clear()` for managing unique values.
   - `Array`: Provides a wide range of methods for manipulating elements, such as `push()`, `pop()`, `shift()`, `unshift()`, `splice()`, and many others.

4. **Performance**:
   - `Set`: Generally has better performance for checking the existence of values due to its unique value constraint.
   - `Array`: May have slower performance for checking existence, especially for large arrays, as it requires iterating through the elements.

### Example of Set vs Array:
```javascript
// Using Set
const mySet = new Set();
mySet.add(1);
mySet.add(2);
mySet.add(2); // Duplicate value, will not be added
console.log(mySet); // Output: Set { 1, 2 }

// Using Array
const myArray = [1, 2, 2]; // Duplicate value allowed   
console.log(myArray); // Output: [ 1, 2, 2 ]
```

## Weak references
Weak references in JavaScript refer to a mechanism that allows you to hold a reference to an object without preventing it from being garbage collected. This is particularly useful in scenarios where you want to associate data with an object without creating a strong reference that would keep the object in memory indefinitely. Weak references are typically used in conjunction with `WeakMap` and `WeakSet`, which allow for the storage of objects that can be garbage collected when there are no other references to them.

### Example of weak references:

```javascript
const weakMap = new WeakMap();
let obj = { id: 1 };

// Adding a weak reference to the object in the WeakMap
weakMap.set(obj, 'Object Key');

// The object can be garbage collected if there are no other references to it
obj = null; // Remove the strong reference to the object

// At this point, the object may be garbage collected, and the entry in the WeakMap will be removed automatically
console.log(weakMap.get(obj)); // Output: undefined (if the object has been garbage collected)
```

## Garbage collection
Garbage collection in JavaScript is an automatic memory management process that identifies and frees up memory occupied by objects that are no longer reachable or needed by the program. The JavaScript engine uses algorithms to track object references and determine which objects can be safely removed from memory. When an object is no longer referenced by any part of the code, it becomes eligible for garbage collection, allowing the memory it occupied to be reclaimed for future use. This process helps prevent memory leaks and ensures efficient use of system resources.

### Example of garbage collection:

```javascript
let obj = { id: 1 };
// The object is reachable and will not be garbage collected

obj = null; // Remove the reference to the object
// At this point, the object is no longer reachable and may be garbage collected by the JavaScript engine, freeing up memory for future use.
```

## Garbage collection use cases
Garbage collection in JavaScript is essential for managing memory efficiently and preventing memory leaks. Here are some common use cases where garbage collection plays a crucial role:
1. **Dynamic Object Creation**: In applications that create and destroy objects frequently, such as games or interactive web applications, garbage collection ensures that memory used by objects that are no longer needed is reclaimed.
2. **Event Listeners**: When adding event listeners to DOM elements, if the elements are removed from the DOM but the event listeners are not properly cleaned up, it can lead to memory leaks. Garbage collection helps reclaim memory used by these unreferenced event listeners.
3. **Closures**: Closures can capture variables from their outer scope. If these closures are no longer needed, garbage collection can free up the memory used by the captured variables.
4. **Data Structures**: In applications that use complex data structures like trees or graphs, garbage collection helps manage memory by cleaning up nodes or elements that are no longer reachable.

# Modules

## Why Modules?
Modules in JavaScript are a way to organize and encapsulate code into reusable, self-contained units. They allow developers to break down complex applications into smaller, manageable pieces, promoting better code organization, maintainability, and reusability. Modules help avoid global namespace pollution by providing a scope for variables and functions, reducing the risk of naming conflicts. Additionally, they enable the use of import and export statements to share functionality between different parts of an application or even across different projects.

### Benefits of using modules:
1. **Encapsulation**: Modules provide a private scope for variables and functions, preventing them from being accessible in the global scope and reducing the risk of naming conflicts.
2. **Reusability**: Modules can be reused across different parts of an application or even in different projects, promoting code reuse and reducing duplication.
3. **Maintainability**: By breaking down an application into smaller modules, it becomes easier to manage and maintain the codebase, as each module can be developed, tested, and debugged independently.
4. **Dependency Management**: Modules allow developers to explicitly declare dependencies between different parts of the application, making it easier to understand and manage the relationships between components.

### Example of using modules:

```javascript
// math.js (module)
export function add(a, b) {
  return a + b;
}

// main.js (importing the module)
import { add } from './math.js';

console.log(add(2, 3)); // Output: 5
```

## ES Modules
ES Modules (ECMAScript Modules) are a standardized module system introduced in ECMAScript 2015 (ES6) that allows developers to organize and share code in a modular way. ES Modules use the `import` and `export` syntax to define and consume modules, enabling better code organization, encapsulation, and reusability. They are supported natively in modern browsers and Node.js, making it easier to work with modular JavaScript code.

### Example of ES Modules:

```javascript
// math.js (module)
export function add(a, b) {
  return a + b;
}

// main.js (importing the module)
import { add } from './math.js';

console.log(add(2, 3)); // Output: 5
```

## export
In JavaScript, the `export` statement is used to make functions, objects, or primitive values available for use in other modules. By exporting a module's functionality, you can share it with other parts of your application or with other applications. There are two main types of exports: named exports and default exports.

### Example of named exports:

```javascript
// math.js (module)
export function add(a, b) {
  return a + b;
}

export function subtract(a, b) {
  return a - b;
}
```

## export default
In JavaScript, the `export default` statement is used to export a single value or entity from a module, making it the default export. This allows other modules to import the default export without using curly braces and gives the importing module the flexibility to name the imported value as desired. A module can have only one default export, but it can also have multiple named exports alongside it.

### Example of export default:

```javascript
// math.js (module)
export default function add(a, b) {
  return a + b;
}
```

### Example of importing a default export:

```javascript
// main.js (importing the default export)
import add from './math.js';

console.log(add(2, 3)); // Output: 5
```

## import
In JavaScript, the `import` statement is used to bring in functions, objects, or primitive values that have been exported from another module. It allows developers to use the functionality defined in one module within another module, promoting code reuse and modularity. The `import` statement can be used to import named exports, default exports, or a combination of both.

### Example of importing named exports:

```javascript
// math.js (module)
export function add(a, b) {
  return a + b;
}

// main.js (importing named exports)
import { add } from './math.js';

console.log(add(2, 3)); // Output: 5
```

### Example of importing default exports:

```javascript
// math.js (module)
export default function add(a, b) {
  return a + b;
}

// main.js (importing default export)
import add from './math.js';

console.log(add(2, 3)); // Output: 5
```

## Named imports & default imports
In JavaScript, named imports and default imports are two different ways to import functionality from modules.

### Named Imports
Named imports allow you to import specific functions, objects, or values that have been exported with a name from a module. You use curly braces `{}` to specify the names of the exports you want to import. This approach is useful when a module exports multiple values, and you only need a subset of them.

### Example of named imports:

```javascript
// math.js (module)
export function add(a, b) {
  return a + b;
}

export function subtract(a, b) {
  return a - b;
}

// main.js (importing named exports)
import { add, subtract } from './math.js';

console.log(add(2, 3)); // Output: 5
console.log(subtract(5, 2)); // Output: 3
```

### Default Imports
Default imports allow you to import a single value or entity that has been exported as the default from a module. You do not use curly braces for default imports, and you can give the imported value any name you choose. This approach is useful when a module has a primary export that represents its main functionality.

### Example of default imports:

```javascript
// math.js (module)
export default function add(a, b) {
  return a + b;
}

// main.js (importing default export)
import add from './math.js';

console.log(add(2, 3)); // Output: 5
```

## Namespace imports
In JavaScript, namespace imports allow you to import all the exported members of a module as a single object. This is done using the `* as` syntax, which creates a namespace object that contains all the named exports from the module. Namespace imports are useful when you want to access multiple exports from a module without having to import each one individually.

### Example of namespace imports:

```javascript
// math.js (module)
export function add(a, b) {
  return a + b;
}

export function subtract(a, b) {
  return a - b;
}

// main.js (importing all exports as a namespace)
import * as math from './math.js';

console.log(math.add(2, 3)); // Output: 5
console.log(math.subtract(5, 2)); // Output: 3
```

## Re-exporting
Re-exporting in JavaScript allows you to take exports from one module and export them again from another module. This is useful for creating a centralized module that aggregates exports from multiple modules, making it easier to manage and import them in other parts of your application. Re-exporting can be done using the `export` statement along with the `from` keyword.

### Example of re-exporting:

```javascript
// math.js (module)
export function add(a, b) {
  return a + b;
}

// utils.js (module)
export { add } from './math.js'; // Re-exporting the add function
// main.js (importing from utils.js)
import { add } from './utils.js';

console.log(add(2, 3)); // Output: 5
```

## Dynamic imports
Dynamic imports in JavaScript allow you to load modules asynchronously at runtime, rather than statically at the beginning of the script. This is done using the `import()` function, which returns a promise that resolves to the module object. Dynamic imports are useful for code splitting, lazy loading, and improving performance by loading modules only when they are needed.

### Example of dynamic imports:

```javascript
// main.js
async function loadModule() {
  const module = await import('./math.js'); // Dynamically importing the math module
  console.log(module.add(2, 3)); // Output: 5
}

loadModule();
```

## CommonJS
CommonJS is a module system used primarily in Node.js for organizing and sharing code. It allows developers to create modules that can be imported and exported using the `require` and `module.exports` syntax. CommonJS modules are synchronous, meaning that they are loaded and executed in a blocking manner. This module system is widely used in server-side JavaScript development.

### Example of CommonJS:

```javascript
// math.js (module)
function add(a, b) {
  return a + b;
}

module.exports = { add }; // Exporting the add function

// main.js (importing the module)
const math = require('./math.js'); // Importing the math module

console.log(math.add(2, 3)); // Output: 5
```

## require()
In JavaScript, particularly in the CommonJS module system used in Node.js, the `require()` function is used to import modules. It allows you to include and use functionality from other files or built-in modules in your application. The `require()` function takes a module identifier (usually a file path or module name) as an argument and returns the exported content of that module.

### Example of require():

```javascript
// math.js (module)
function add(a, b) {
  return a + b;
}

module.exports = { add }; // Exporting the add function

// main.js (importing the module)
const math = require('./math.js'); // Importing the math module

console.log(math.add(2, 3)); // Output: 5
```

## module.exports
In JavaScript, particularly in the CommonJS module system used in Node.js, `module.exports` is an object that is used to define what a module exports and makes available for use in other files. By assigning values, functions, or objects to `module.exports`, you can control what is exposed when the module is imported using `require()`. This allows for encapsulation and modularity in your code.

### Example of module.exports:

```javascript
// math.js (module)
function add(a, b) {
  return a + b;
}

module.exports = { add }; // Exporting the add function

// main.js (importing the module)
const math = require('./math.js'); // Importing the math module

console.log(math.add(2, 3)); // Output: 5
```

## ES Modules vs CommonJS
ES Modules (ECMAScript Modules) and CommonJS are two different module systems in JavaScript, each with its own syntax and use cases. ES Modules are the standardized module system introduced in ECMAScript 2015 (ES6), while CommonJS is primarily used in Node.js for server-side development.

### Differences between ES Modules and CommonJS:
1. **Syntax**:
   - ES Modules: Use `import` and `export` statements for importing and exporting functionality.
   - CommonJS: Use `require()` for importing and `module.exports` for exporting functionality.

2. **Loading**:
   - ES Modules: Support static and dynamic imports, allowing for asynchronous loading of modules.
    - CommonJS: Modules are loaded synchronously, which can block execution until the module is fully loaded.

3. **Scope**:
   - ES Modules: Each module has its own scope, and variables declared in a module are not accessible outside of it unless explicitly exported.
    - CommonJS: Modules also have their own scope, but the exported values are accessible through `require()`.

4. **Default Exports**:
   - ES Modules: Support default exports, allowing a module to export a single value or entity.
   - CommonJS: Does not have a built-in concept of default exports; instead, you can export a single value by assigning it to `module.exports`.

### Example of ES Modules vs CommonJS:
```javascript
// ES Modules (math.js)
export function add(a, b) {
  return a + b;
}

// CommonJS (math.js)
function add(a, b) {
  return a + b;
}

module.exports = { add }; // Exporting the add function
```

## Module resolution
Module resolution in JavaScript refers to the process by which the JavaScript engine determines the location of and loads the appropriate module when an `import` or `require()` statement is encountered. The resolution process involves searching for the module in various locations, such as local files, node_modules directories, or built-in modules, based on the specified module identifier. Different environments (e.g., browsers, Node.js) may have different resolution strategies.

### Example of module resolution:

```javascript
// main.js
import { add } from './math.js'; // The engine resolves the path to math.js and loads the module
console.log(add(2, 3)); // Output: 5
```

## Circular dependencies
Circular dependencies in JavaScript occur when two or more modules depend on each other, either directly or indirectly, creating a cycle in the dependency graph. This can lead to issues such as incomplete module loading, unexpected behavior, or runtime errors. Circular dependencies can be problematic because they can make it difficult to reason about the code and can lead to hard-to-debug issues.

### Example of circular dependencies:

```javascript
// moduleA.js
import { functionB } from './moduleB.js';

export function functionA() {
  console.log('Function A');
  functionB();
}

// moduleB.js
import { functionA } from './moduleA.js';

export function functionB() {
  console.log('Function B');
  functionA();
}
```

# JSON & Data Handling

## JSON syntax
JSON (JavaScript Object Notation) is a lightweight data interchange format that is easy for humans to read and write, and easy for machines to parse and generate. It is based on a subset of the JavaScript programming language and is commonly used for transmitting data between a server and a web application. JSON syntax consists of key-value pairs, arrays, and nested objects, making it a versatile format for representing structured data.

### JSON syntax rules:
1. **Objects**: Represented by curly braces `{}` and contain key-value pairs.
2. **Arrays**: Represented by square brackets `[]` and contain ordered lists of values.
3. **Keys**: Must be strings enclosed in double quotes.
4. **Values**: Can be strings, numbers, booleans, null, objects, or arrays.

### Example of JSON syntax:

```json
{
  "name": "Alice",
  "age": 30,
  "isStudent": false,
  "courses": ["Math", "Science"],
  "address": {
    "street": "123 Main St",
    "city": "Anytown",
    "zipCode": "12345"
  }
}
```

## JSON.parse()
In JavaScript, the `JSON.parse()` method is used to convert a JSON-formatted string into a JavaScript object. This method takes a JSON string as input and returns the corresponding JavaScript object, allowing developers to work with the data in a more convenient format. It is commonly used when receiving JSON data from APIs or external sources.

### Example of JSON.parse():

```javascript
const jsonString = '{"name": "Alice", "age": 30, "isStudent": false}';
const jsonObject = JSON.parse(jsonString);
console.log(jsonObject.name); // Output: Alice
console.log(jsonObject.age); // Output: 30
console.log(jsonObject.isStudent); // Output: false
```

## JSON.stringify()
In JavaScript, the `JSON.stringify()` method is used to convert a JavaScript object or value into a JSON-formatted string. This method takes an object as input and returns a string representation of that object in JSON format. It is commonly used when sending data to APIs or storing data in a format that can be easily transmitted or saved.

### Example of JSON.stringify():

```javascript
const jsonObject = {
  name: "Alice",
  age: 30,
  isStudent: false
};

const jsonString = JSON.stringify(jsonObject);
console.log(jsonString); // Output: '{"name":"Alice","age":30,"isStudent":false}'
```

## Serialization and Deserialization
Serialization in JavaScript refers to the process of converting a JavaScript object or value into a format that can be easily stored or transmitted, such as a JSON string. Deserialization is the reverse process, where a serialized format (like a JSON string) is converted back into a JavaScript object or value. These processes are essential for data exchange between different systems, such as client-server communication in web applications.

### Example of Serialization and Deserialization:

```javascript
// Serialization
const jsonObject = {
  name: "Alice",
  age: 30,
  isStudent: false
};

const jsonString = JSON.stringify(jsonObject);
console.log(jsonString); // Output: '{"name":"Alice","age":30,"isStudent":false}'

// Deserialization
const parsedObject = JSON.parse(jsonString);
console.log(parsedObject.name); // Output: Alice
console.log(parsedObject.age); // Output: 30
console.log(parsedObject.isStudent); // Output: false
```

## Deep cloning concepts
Deep cloning in JavaScript refers to the process of creating a new object that is a complete copy of an existing object, including all nested objects and arrays. This means that changes made to the cloned object do not affect the original object, and vice versa. Deep cloning is important when you want to create independent copies of complex data structures without sharing references.

### Example of deep cloning using JSON methods:

```javascript
const originalObject = {
  name: "Alice",
  age: 30,
  address: {
    street: "123 Main St",
    city: "Anytown"
  }
};

const deepClonedObject = JSON.parse(JSON.stringify(originalObject));
deepClonedObject.address.city = "New City";

console.log(originalObject.address.city); // Output: Anytown
console.log(deepClonedObject.address.city); // Output: New City
```

## Structured cloning
Structured cloning in JavaScript is a method of creating a deep copy of complex data structures, including objects, arrays, and other types of data, while preserving their structure and references. Unlike shallow cloning, which only copies the top-level properties, structured cloning ensures that all nested objects and arrays are also copied, resulting in a completely independent copy of the original data. This is particularly useful when working with complex data structures that need to be duplicated without sharing references.

### Example of structured cloning using the `structuredClone()` method:

```javascript
const originalObject = {
  name: "Alice",
  age: 30,
  address: {
    street: "123 Main St",
    city: "Anytown"
  }
};

const structuredClonedObject = structuredClone(originalObject);
structuredClonedObject.address.city = "New City";

console.log(originalObject.address.city); // Output: Anytown
console.log(structuredClonedObject.address.city); // Output: New City
```

## structuredClone() method
The `structuredClone()` method in JavaScript is a built-in function that allows you to create a deep copy of complex data structures, including objects, arrays, and other types of data. It preserves the structure and references of the original data, ensuring that changes made to the cloned object do not affect the original object. The `structuredClone()` method is particularly useful for duplicating data without sharing references, making it ideal for scenarios where you need independent copies of complex objects.

### Example of using the `structuredClone()` method:

```javascript
const originalObject = {
  name: "Alice",
  age: 30,
  address: {
    street: "123 Main St",
    city: "Anytown"
  }
};

const structuredClonedObject = structuredClone(originalObject);
structuredClonedObject.address.city = "New City";

console.log(originalObject.address.city); // Output: Anytown
console.log(structuredClonedObject.address.city); // Output: New City
```

## Handling API data
When working with APIs in JavaScript, handling API data involves making HTTP requests to retrieve or send data, processing the response, and managing any errors that may occur. This typically includes using methods like `fetch()` or libraries like Axios to make requests, parsing the JSON response, and updating the application state or UI based on the received data.

### Example of handling API data using the `fetch()` method:

```javascript
const apiUrl = 'https://api.example.com/data';

fetch(apiUrl)
  .then(response => {
    if (!response.ok) {
      throw new Error('Network response was not ok');
    }
    return response.json(); // Parse the JSON data from the response
  })
  .then(data => {
    console.log(data); // Handle the API data (e.g., update UI or state)
  })
  .catch(error => {
    console.error('There was a problem with the fetch operation:', error); // Handle any errors
  });
```

## Transforming nested data
Transforming nested data in JavaScript involves manipulating and restructuring complex data structures, such as objects and arrays, to achieve a desired format or representation. This can include flattening nested objects, mapping over arrays, filtering data, or aggregating values. Transforming nested data is often necessary when working with API responses or when preparing data for rendering in a user interface.

### Example of transforming nested data:

```javascript
const nestedData = {
  users: [
    { id: 1, name: 'Alice', address: { city: 'New York', zip: '10001' } },
    { id: 2, name: 'Bob', address: { city: 'Los Angeles', zip: '90001' } },
    { id: 3, name: 'Charlie', address: { city: 'Chicago', zip: '60601' } }
  ]
};

// Transforming nested data to extract user names and cities
const transformedData = nestedData.users.map(user => ({
  name: user.name,
  city: user.address.city
}));

console.log(transformedData);
// Output:
// [
//   { name: 'Alice', city: 'New York' },
//   { name: 'Bob', city: 'Los Angeles' },
//   { name: 'Charlie', city: 'Chicago' }
//  ]
```