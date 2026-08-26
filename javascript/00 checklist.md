- [ ] Variables and Data Types
    - ```js
      // Variable
        let name = "Rahul";
        const age = 25;
        var isStudent = true;

        // Data Types
        let number = 42; // Number
        let string = "Hello, World!"; // String
        let boolean = false; // Boolean
        let object = { name: "Rahul", age: 25 }; // Object
        let array = [1, 2, 3, 4, 5];
        let nullValue = null; // Null
        let undefinedValue; // Undefined
        let symbolValue = Symbol("unique"); // Symbol
        let bigIntValue = 9007199254740991n; // BigInt
        let functionValue = function() { return "Hello"; }; // Function
      ```
- [ ] Reference types and Value types
    - ```js
      // Value Types
      let num1 = 10;
      let num2 = num1; // Copying value
      num2 = 20;
      console.log(num1); // Output: 10
      console.log(num2); // Output: 20

      // Reference Types
      let obj1 = { name: "Rahul" };
      let obj2 = obj1; // Copying reference
      obj2.name = "Amit";
      console.log(obj1.name); // Output: Amit
      console.log(obj2.name); // Output: Amit
      ```
- [ ] typeof operator
    - ```js
      let num = 42;
      let str = "Hello";
      let bool = true;
      let obj = { name: "Rahul" };
      let arr = [1, 2, 3];
      let func = function() {};
      let nullValue = null;
      let undefinedValue;

      console.log(typeof num); // Output: number
      console.log(typeof str); // Output: string
      console.log(typeof bool); // Output: boolean
      console.log(typeof obj); // Output: object
      console.log(typeof arr); // Output: object
      console.log(typeof func); // Output: function
      console.log(typeof nullValue); // Output: object (this is a known quirk in JavaScript)
      console.log(typeof undefinedValue); // Output: undefined
        ```

- [ ] Dynamic typing
    - ```js
      let variable = 42; // Initially a number
      console.log(typeof variable); // Output: number

      variable = "Hello, World!"; // Now a string
      console.log(typeof variable); // Output: string

      variable = true; // Now a boolean
      console.log(typeof variable); // Output: boolean

      variable = { name: "Rahul" }; // Now an object
      console.log(typeof variable); // Output: object

      variable = [1, 2, 3]; // Now an array (which is also an object)
      console.log(typeof variable); // Output: object

      variable = null; // Now null
      console.log(typeof variable); // Output: object (this is a known quirk in JavaScript)

      variable = undefined; // Now undefined
      console.log(typeof variable); // Output: undefined
        ```

- [ ] Type Coercion
    - ```js
      // Type Coercion Examples
      let num = 5;
      let str = "10";

      // Implicit Coercion
      let result1 = num + str; // Number is coerced to string
      console.log(result1); // Output: "510"

      let result2 = num * str; // String is coerced to number
      console.log(result2); // Output: 50

      let bool = true;
      let result3 = num + bool; // Boolean is coerced to number (true -> 1)
      console.log(result3); // Output: 6

      let nullValue = null;
      let result4 = num + nullValue; // Null is coerced to number (null -> 0)
      console.log(result4); // Output: 5

      let undefinedValue;
      let result5 = num + undefinedValue; // Undefined is coerced to NaN
      console.log(result5); // Output: NaN
        ```

- [ ] Truthy and Falsy values
    - ```js
      // Falsy values
      let falsyValues = [false, 0, -0, 0n, "", null, undefined, NaN];
      falsyValues.forEach(value => {
        if (value) {
          console.log(`${value} is truthy`);
        } else {
          console.log(`${value} is falsy`);
        }
      });

      // Truthy values
      let truthyValues = [true, 1, -1, "non-empty string", [], {}, function() {}];
      truthyValues.forEach(value => {
        if (value) {
          console.log(`${value} is truthy`);
        } else {
          console.log(`${value} is falsy`);
        }
      });
        ```

- [ ] Arithmetic Operators
    - ```js
      let a = 10;
      let b = 3;

      console.log(a + b); // Addition: 13
      console.log(a - b); // Subtraction: 7
      console.log(a * b); // Multiplication: 30
      console.log(a / b); // Division: 3.333...
      console.log(a % b); // Modulus: 1
      console.log(a ** b); // Exponentiation: 1000
        ```

- [ ] Assignment Operators
    - ```js
      let x = 10;
      x += 5; // Equivalent to x = x + 5
      console.log(x); // Output: 15

      x -= 3; // Equivalent to x = x - 3
      console.log(x); // Output: 12

      x *= 2; // Equivalent to x = x * 2
      console.log(x); // Output: 24

      x /= 4; // Equivalent to x = x / 4
      console.log(x); // Output: 6

      x %= 4; // Equivalent to x = x % 4
      console.log(x); // Output: 2

      x **= 3; // Equivalent to x = x ** 3
      console.log(x); // Output: 8
        ```
- [ ] Comparison Operators
    - ```js
      let a = 10;
      let b = 20;

      console.log(a == b); // Equal to: false
      console.log(a != b); // Not equal to: true
      console.log(a === b); // Strict equal to: false
      console.log(a !== b); // Strict not equal to: true
      console.log(a > b); // Greater than: false
      console.log(a < b); // Less than: true
      console.log(a >= b); // Greater than or equal to: false
      console.log(a <= b); // Less than or equal to: true
        ```
- [ ] Logical Operators
    - ```js
      let a = true;
      let b = false;

      console.log(a && b); // Logical AND: false
      console.log(a || b); // Logical OR: true
      console.log(!a); // Logical NOT: false
        ```
- [ ] Nullish Coalescing Operator
    - ```js
      let val1 = null;
      let val2 = "Rahul";

      const result = val1 ?? "Default Value";
      console.log(result); // Output: "Default Value"

      const result2 = val2 ?? "Default Value";
      console.log(result2); // Output: "Rahul"

      const result3 = val1 ?? val2 ?? "Default Value";
      console.log(result3); // Output: "Rahul"

      const result4 = val1 ?? undefined ?? "Default Value";
      console.log(result4); // Output: "Default Value"
        ```

- [ ] Optional Chaining Operator
    - ```js
      const user = {
        name: "Rahul",
        address: {
          city: "New Delhi",
          zip: "110001"
        }
      };

      // Accessing nested properties safely
      const city = user?.address?.city;
      console.log(city); // Output: "New Delhi"

      const country = user?.address?.country;
      console.log(country); // Output: undefined

      const zip = user?.address?.zip;
      console.log(zip); // Output: "110001"

      const phone = user?.contact?.phone ?? "No phone number available";
      console.log(phone); // Output: "No phone number available"
        ```

- [ ] Ternary Operator
    - ```js
      let age = 18;

      // Using ternary operator
      let canVote = (age >= 18) ? "Yes, can vote" : "No, cannot vote";
      console.log(canVote); // Output: "Yes, can vote"

      age = 16;
      canVote = (age >= 18) ? "Yes, can vote" : "No, cannot vote";
      console.log(canVote); // Output: "No, cannot vote"
        ```

- [ ] Unary Operators
    - ```js
      let num = 5;

      // Unary plus operator
      let positiveNum = +num; // Converts to number (if not already)
      console.log(positiveNum); // Output: 5

      // Unary minus operator
      let negativeNum = -num; // Negates the number
      console.log(negativeNum); // Output: -5

      // Increment operator
      num++;
      console.log(num); // Output: 6

      // Decrement operator
      num--;
      console.log(num); // Output: 5

      // Logical NOT operator
      let isTrue = true;
      console.log(!isTrue); // Output: false
        ```

- [ ] Increment and Decrement Operators
    - ```js
      let count = 0;

      // Increment operator
      count++;
      console.log(count); // Output: 1

      // Decrement operator
      count--;
      console.log(count); // Output: 0

      // Pre-increment
      ++count;
      console.log(count); // Output: 1

      // Pre-decrement
      --count;
      console.log(count); // Output: 0
        ```

- [ ] instanceof operator
    - ```js
      class User {
        constructor(name, age) {
          this.name = name;
          this.age = age;
        }
      }

      let user1 = new User("Alice", 30);
      console.log(user1 instanceof User); // Output: true

        let user2 = { name: "Bob", age: 25 };
        console.log(user2 instanceof User); // Output: false
            ```

- [ ] Operator Precedence
    - ```js
      let result = 10 + 5 * 2; // Multiplication has higher precedence than addition
      console.log(result); // Output: 20

      result = (10 + 5) * 2; // Parentheses change the order of operations
      console.log(result); // Output: 30

      result = 10 - 5 + 2; // Left-to-right evaluation for operators with the same precedence
      console.log(result); // Output: 7

      result = 10 / 2 * 3; // Division and multiplication have the same precedence, evaluated left to right
      console.log(result); // Output: 15
        ```

# Control Flow

- [ ] if-else if-else statement
    - ```js
      let age = 20;

      if (age < 13) {
        console.log("Child");
      } else if (age >= 13 && age < 20) {
        console.log("Teenager");
      } else {
        console.log("Adult");
      }
        ```

- [ ] nested if-else statement
    - ```js
      let score = 85;

      if (score >= 90) {
        console.log("Grade: A");
      } else {
        if (score >= 80) {
          console.log("Grade: B");
        } else {
          if (score >= 70) {
            console.log("Grade: C");
          } else {
            console.log("Grade: D");
          }
        }
      }
        ```

- [ ] switch statement
    - ```js
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

- [ ] break continue statement
    - ```js
      for (let i = 1; i <= 10; i++) {
        if (i === 5) {
          continue; // Skip the rest of the loop when i is 5
        }
        if (i === 8) {
          break; // Exit the loop when i is 8
        }
        console.log(i);
      }
      // Output: 1, 2, 3, 4, 6, 7
        ```

- [ ] for loop
    - ```js
      for (let i = 0; i < 5; i++) {
        console.log(i);
      }
      // Output: 0, 1, 2, 3, 4
        ```

- [ ] while loop
    - ```js
      let i = 0;
      while (i < 5) {
        console.log(i);
        i++;
      }
      // Output: 0, 1, 2, 3, 4
        ```

- [ ] do while loop
    - ```js
      let i = 0;
      do {
        console.log(i);
        i++;
      } while (i < 5);
      // Output: 0, 1, 2, 3, 4
        ```

- [ ] for...in loop
    - ```js
      const person = { name: "Rahul", age: 25, city: "New Delhi" };

      for (let key in person) {
        console.log(`${key}: ${person[key]}`);
      }
      // Output:
      // name: Rahul
      // age: 25
      // city: New Delhi
        ```

- [ ] for...of loop
    - ```js
      const numbers = [1, 2, 3, 4, 5];

      for (let num of numbers) {
        console.log(num);
      }
      // Output: 1, 2, 3, 4, 5
        ```

- [ ] Nested loops
    - ```js
      for (let i = 1; i <= 3; i++) {
        for (let j = 1; j <= 3; j++) {
          console.log(`i: ${i}, j: ${j}`);
        }
      }
      // Output:
      // i: 1, j: 1
      // i: 1, j: 2
      // i: 1, j: 3
      // i: 2, j: 1
      // i: 2, j: 2
      // i: 2, j: 3
      // i: 3, j: 1
      // i: 3, j: 2
      // i: 3, j: 3
        ```

# Functions

- [ ] Function Declaration
    - ```js
      function greet(name) {
        return `Hello, ${name}!`;
      }

      console.log(greet("Rahul")); // Output: Hello, Rahul!
        ```

- [ ] Function Expression
    - ```js
      const greet = function(name) {
        return `Hello, ${name}!`;
      };

      console.log(greet("Rahul")); // Output: Hello, Rahul!
        ```

- [ ] Function Parameters and Arguments
    - ```js
      function add(a, b) {
        return a + b;
      }

      console.log(add(5, 10)); // Output: 15
        ```

- [ ] Returning Values from Functions
    - ```js
      function multiply(a, b) {
        return a * b;
      }

      let result = multiply(5, 10);
      console.log(result); // Output: 50
        ```

- [ ] Default Parameters
    - ```js
      function greet(name = "Guest") {
        return `Hello, ${name}!`;
      }

      console.log(greet("Rahul")); // Output: Hello, Rahul!
      console.log(greet()); // Output: Hello, Guest!
        ```

- [ ] Rest Parameters
    - ```js
      function sum(...numbers) {
        return numbers.reduce((total, num) => total + num, 0);
      }

      console.log(sum(1, 2, 3)); // Output: 6
      console.log(sum(4, 5, 6, 7)); // Output: 22
        ```

- [ ] Spread Operator
    - ```js
      const arr1 = [1, 2, 3];
      const arr2 = [4, 5, 6];

      const combined = [...arr1, ...arr2];
      console.log(combined); // Output: [1, 2, 3, 4, 5, 6]

      const obj1 = { a: 1, b: 2 };
      const obj2 = { c: 3, d: 4 };

      const mergedObj = { ...obj1, ...obj2 };
      console.log(mergedObj); // Output: { a: 1, b: 2, c: 3, d: 4 }
        ```

- [ ] Anonymous Functions
    - ```js
      const greet = function(name) {
        return `Hello, ${name}!`;
      };

      console.log(greet("Rahul")); // Output: Hello, Rahul!
        ```

- [ ] Callback Functions
    - ```js
      function fetchData(callback) {
        setTimeout(() => {
          const data = { name: "Rahul", age: 25 };
          callback(data);
        }, 1000);
      }

      function displayData(data) {
        console.log(`Name: ${data.name}, Age: ${data.age}`);
      }

      fetchData(displayData); // Output after 1 second: Name: Rahul, Age: 25
        ```

- [ ] Higher-Order Functions
    - ```js
      function operate(a, b, operation) {
        return operation(a, b);
      }

      function add(x, y) {
        return x + y;
      }

      function multiply(x, y) {
        return x * y;
      }

      console.log(operate(5, 10, add)); // Output: 15
      console.log(operate(5, 10, multiply)); // Output: 50
        ```

- [ ] First-Class Functions
    - ```js
      function greet(name) {
        return `Hello, ${name}!`;
      }

      const sayHello = greet; // Assigning function to a variable
      console.log(sayHello("Rahul")); // Output: Hello, Rahul!

      function executeFunction(func, name) {
        return func(name); // Passing function as an argument
      }

      console.log(executeFunction(greet, "Amit")); // Output: Hello, Amit!
        ```

- [ ] Arrow Functions
    - ```js
      const greet = (name) => {
        return `Hello, ${name}!`;
      };

      console.log(greet("Rahul")); // Output: Hello, Rahul!

      // Shorter syntax for single expression
      const add = (a, b) => a + b;
      console.log(add(5, 10)); // Output: 15
        ```

- [ ] Immediately Invoked Function Expressions (IIFE)
    - ```js
      (function() {
        console.log("This is an IIFE!");
      })(); // Output: This is an IIFE!

      // IIFE with parameters
      (function(name) {
        console.log(`Hello, ${name}!`);
      })("Rahul"); // Output: Hello, Rahul!
        ```

- [ ] Pure Functions
    - ```js
      function add(a, b) {
        return a + b; // No side effects, always returns the same output for the same inputs
      }

      console.log(add(5, 10)); // Output: 15
      console.log(add(5, 10)); // Output: 15
        ```

- [ ] Impure Functions
    - ```js
      let counter = 0;

      function incrementCounter() {
        counter++; // Side effect: modifies external variable
        return counter;
      }

      console.log(incrementCounter()); // Output: 1
      console.log(incrementCounter()); // Output: 2
        ```

- [ ] Side Effects
    - ```js
      let globalVar = 0;

      function modifyGlobalVar() {
        globalVar++; // Side effect: modifies external variable
        return globalVar;
      }

      console.log(modifyGlobalVar()); // Output: 1
      console.log(modifyGlobalVar()); // Output: 2
        ```

- [ ] Function Composition
    - ```js
      const add = (a, b) => a + b;
      const multiply = (a, b) => a * b;

      const addThenMultiply = (x, y, z) => multiply(add(x, y), z);

      console.log(addThenMultiply(2, 3, 4)); // Output: 20
        ```

- [ ] Recursion
    - ```js
      function factorial(n) {
        if (n === 0 || n === 1) {
          return 1; // Base case
        }
        return n * factorial(n - 1); // Recursive case
      }

      console.log(factorial(5)); // Output: 120
      console.log(factorial(0)); // Output: 1
        ```

- [ ] Call Stack
    - ```js
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
      // Output:
      // First function
      // Second function
      // Third function
        ```

