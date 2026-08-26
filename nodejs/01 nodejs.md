# Node.js Fundamentals

## What is Node.js?
Node.js is an open-source, cross-platform JavaScript runtime environment that allows developers to run JavaScript code on the server side. It is built on Chrome's V8 JavaScript engine and enables the development of scalable and high-performance applications, particularly for web servers and networking applications.

## Why Node.js exists?
Node.js was created to address the limitations of traditional server-side technologies, which often struggled with handling a large number of concurrent connections efficiently. Traditional web servers, like Apache or Nginx, use a multi-threaded approach, where each connection requires a separate thread. This can lead to high memory usage and performance bottlenecks under heavy load.

Node.js, on the other hand, uses an event-driven, non-blocking I/O model that allows it to handle many connections simultaneously with a single thread. This makes it particularly well-suited for real-time applications, such as chat applications, online gaming, and collaborative tools.

## Node.js vs browser JavaScript
While both Node.js and browser JavaScript use the same core language, there are significant differences between the two environments:
1. **Execution Environment**: Browser JavaScript runs in the context of a web browser, while Node.js runs on the server side.
2. **APIs**: Node.js provides a rich set of built-in modules for server-side development, such as file system access, networking, and process management. Browser JavaScript has access to the Document Object Model (DOM) and browser-specific APIs.
3. **Global Objects**: In Node.js, the global object is `global`, while in browser JavaScript, it is `window`. This affects how variables and functions are scoped and accessed.
4. **Modules**: Node.js uses the CommonJS module system, allowing developers to import and export modules using `require` and `module.exports`. Browser JavaScript typically uses ES6 modules with `import` and `export` statements.
5. **Event Loop**: Both environments use an event loop to handle asynchronous operations, but the implementation and behavior can differ due to the underlying architecture and available APIs.

## Node.js Architecture
Node.js follows a single-threaded, event-driven architecture that allows it to handle multiple concurrent connections efficiently. The core components of Node.js architecture include:
1. **Event Loop**: The event loop is the heart of Node.js, responsible for managing asynchronous operations and callbacks. It continuously checks for events and executes the corresponding callback functions when events occur.
2. **Non-blocking I/O**: Node.js uses non-blocking I/O operations, allowing it to perform tasks like reading files or making network requests without blocking the execution of other code. This enables Node.js to handle many connections simultaneously.
3. **Libuv**: Node.js relies on the libuv library to provide an abstraction layer for asynchronous I/O operations, including file system access, networking, and timers. Libuv handles the underlying system calls and provides a consistent API across different platforms.
4. **V8 Engine**: Node.js is built on the V8 JavaScript engine, which compiles JavaScript code into machine code for fast execution. The V8 engine also provides features like Just-In-Time (JIT) compilation and garbage collection to optimize performance.
5. **Modules**: Node.js has a modular architecture, allowing developers to create reusable code in the form of modules. The built-in module system enables easy management of dependencies and promotes code organization.

## Single-threaded JavaScript execution
Node.js operates on a single-threaded event loop, which means that it can handle multiple concurrent connections without creating new threads for each connection. This is achieved through non-blocking I/O operations and asynchronous programming techniques, such as callbacks, promises, and async/await.

When a Node.js application receives a request, it processes the request in the event loop. If the request involves an I/O operation (e.g., reading from a database or file system), Node.js offloads the operation to the underlying system and continues processing other requests. Once the I/O operation is complete, the event loop picks up the result and executes the corresponding callback function.

## Non-blocking I/O
Non-blocking I/O is a key feature of Node.js that allows it to perform input/output operations without blocking the execution of other code. In traditional blocking I/O, when a request is made to read data from a file or database, the execution of the program is paused until the operation is complete. This can lead to performance bottlenecks, especially when handling multiple concurrent requests.

In contrast, non-blocking I/O allows Node.js to initiate an I/O operation and continue executing other code while waiting for the operation to complete. When the operation is finished, a callback function is invoked to handle the result. This approach enables Node.js to efficiently manage a large number of concurrent connections and maintain high performance.

## Event-driven architecture
Node.js follows an event-driven architecture, which means that it relies on events and callbacks to handle asynchronous operations. In this model, the application listens for events (such as incoming requests or completed I/O operations) and responds to them by executing the appropriate callback functions.

### Example of event-driven architecture in Node.js:
```javascript
const EventEmitter = require('events');
class MyEmitter extends EventEmitter {}

const myEmitter = new MyEmitter();
// Register an event listener
myEmitter.on('event', () => {
  console.log('An event occurred!');
});

// Emit the event
myEmitter.emit('event');
```

## libuv
Libuv is a multi-platform support library that provides an abstraction layer for asynchronous I/O operations in Node.js. It is responsible for handling low-level system calls and providing a consistent API for file system access, networking, timers, and other asynchronous operations across different operating systems.

## Node.js process
The Node.js process is the runtime environment in which Node.js applications execute. It is responsible for managing the execution of JavaScript code, handling events, and coordinating I/O operations. The process object in Node.js provides information about the current Node.js process, such as its ID, environment variables, and command-line arguments.

### Example of accessing the process object in Node.js:
```javascript
console.log(`Process ID: ${process.pid}`);
console.log(`Node.js version: ${process.version}`);
console.log(`Current working directory: ${process.cwd()}`);
```

## Node.js versions
Node.js follows a release schedule that includes Long-Term Support (LTS) and Current releases.

## LTS versions
LTS versions of Node.js are stable releases that receive long-term support, including security updates and bug fixes. These versions are recommended for production use, as they provide a reliable and stable environment for applications. LTS releases typically have a support cycle of 30 months, with active support for the first 18 months and maintenance support for the remaining 12 months.

## Installing Node.js
To install Node.js, you can follow these steps:
1. **Download the Installer**: Visit the official Node.js website (https://nodejs.org/) and download the installer for your operating system (Windows, macOS, or Linux).
2. **Run the Installer**: Execute the downloaded installer and follow the on-screen instructions to complete the installation process. Make sure to select the option to add Node.js to your system's PATH during installation.
3. **Verify the Installation**: Open a terminal or command prompt and run the following commands to verify that Node.js and npm (Node Package Manager) have been installed correctly:
   ```bash
   node -v
   npm -v
   ```
   These commands will display the installed versions of Node.js and npm, confirming that the installation was successful.
4. **Update npm (Optional)**: If you want to update npm to the latest version, you can run the following command:
   ```bash
   npm install -g npm
   ```
5. **Install Node Version Manager (Optional)**: If you want to manage multiple versions of Node.js on your system, you can install a version manager like nvm (Node Version Manager) for Linux/macOS or nvm-windows for Windows. This allows you to easily switch between different Node.js versions as needed.

## `node` command
The `node` command is used to run Node.js applications and execute JavaScript code in the Node.js runtime environment. It can be used to run JavaScript files, start a REPL (Read-Eval-Print Loop) session, and execute scripts directly from the command line.

### Example of using the `node` command:
1. **Running a JavaScript file**: To run a JavaScript file named `app.js`, use the following command:
   ```bash
   node app.js
   ```
2. **Starting a REPL session**: To start an interactive REPL session, simply run the `node` command without any arguments:
   ```bash
    node
    ```
3. **Executing a script directly**: You can also execute JavaScript code directly from the command line using the `-e` flag:
   ```bash
   node -e "console.log('Hello, Node.js!')"
   ```

## Running `.js` files
To run a JavaScript file with Node.js, follow these steps:
1. **Create a JavaScript file**: Create a new file with a `.js` extension (e.g., `app.js`) and write your JavaScript code in it. For example:
   ```javascript
   // app.js
   console.log('Hello, Node.js!');
   ```

2. **Open a terminal or command prompt**: Navigate to the directory where your JavaScript file is located using the `cd` command.

3. **Run the JavaScript file**: Use the `node` command followed by the filename to execute the JavaScript file. For example:
   ```bash
   node app.js
   ```
4. **View the output**: After running the command, you should see the output of your JavaScript code in the terminal. In this case, it will display:
   ```
    Hello, Node.js!
    ```

## Node REPL
The Node.js REPL (Read-Eval-Print Loop) is an interactive command-line interface that allows developers to execute JavaScript code in real-time. It provides a convenient way to test code snippets, explore Node.js features, and debug applications.

### Starting the Node REPL
To start the Node REPL, open a terminal or command prompt and run the following command:
```bash
node
```

### Using the Node REPL
Once the REPL is started, you can type JavaScript code directly into the prompt and press Enter to execute it. The REPL will evaluate the code and print the result. You can also use the REPL to define variables, create functions, and explore Node.js modules.

### Example of using the Node REPL:
```javascript
> const message = 'Hello, Node.js!';
> console.log(message);
Hello, Node.js!
> const add = (a, b) => a + b;
> add(5, 3);
8
```

## node --version
The `node --version` command is used to check the currently installed version of Node.js on your system. This command is useful for verifying that Node.js has been installed correctly and for ensuring compatibility with specific features or libraries that may require a certain version of Node.js.

### Example of using the `node --version` command:
```bash
node --version
```

## node --help
The `node --help` command provides a list of available command-line options and usage information for the Node.js runtime. It is a helpful resource for developers who want to learn about the various flags and options that can be used when running Node.js applications.

### Example of using the `node --help` command:
```bash
node --help
```

## Environment Variables
Environment variables are key-value pairs that can be used to configure the behavior of Node.js applications. They can be set in the operating system or within the Node.js application itself. Common environment variables include `NODE_ENV`, which specifies the environment (e.g., development, production), and `PORT`, which defines the port number on which the application should listen.

### Setting Environment Variables
You can set environment variables in different ways depending on your operating system:
- **On Windows**:
  ```bash
  set NODE_ENV=production
  set PORT=3000
  ```

- **On macOS/Linux**:
  ```bash
    export NODE_ENV=production
    export PORT=3000
  ```

## Setting windows environment variables using node.js
To set environment variables in Windows using Node.js, you can use the `process.env` object. This allows you to define environment variables directly within your Node.js application. Here's how you can do it:

### Example of setting environment variables in Windows using Node.js:
```javascript
// Set environment variables
process.env.NODE_ENV = 'production';
process.env.PORT = '3000';

// Access and log the environment variables
console.log(`Environment: ${process.env.NODE_ENV}`);
console.log(`Port: ${process.env.PORT}`);
```

## process.env
The `process.env` object in Node.js is a global object that provides access to the environment variables of the current process. It allows developers to read and modify environment variables, which can be useful for configuring application behavior based on different environments (e.g., development, testing, production).

### Example of using `process.env`:
```javascript
// Accessing environment variables
const nodeEnv = process.env.NODE_ENV || 'development';
console.log(`Current Environment: ${nodeEnv}`);

// Setting an environment variable
process.env.PORT = '3000';

console.log(`Server will run on port: ${process.env.PORT}`);
```

# Node.js Runtime & Internals

## V8
V8 is an open-source JavaScript engine developed by Google that powers Node.js. It compiles JavaScript code into machine code for fast execution, enabling high-performance applications. V8 includes features like Just-In-Time (JIT) compilation, garbage collection, and optimization techniques to improve the performance of JavaScript code.

### diagram of how v8 works
```plaintext
          ┌───────────────────────────────┐
          │         JavaScript Code        │
          └───────────────────────────────┘
                     │
                     ▼
          ┌───────────────────────────────┐
          │       Parser & Compiler        │
          └───────────────────────────────┘
                     │
                     ▼
          ┌───────────────────────────────┐
          │      Intermediate Representation│
          └───────────────────────────────┘
                     │
                     ▼
          ┌───────────────────────────────┐
          │      Just-In-Time (JIT)       │
          │        Compilation             │
          └───────────────────────────────┘
                     │
                     ▼
          ┌───────────────────────────────┐
          │       Machine Code Execution   │
          └───────────────────────────────┘
```

## libuv
Libuv is a multi-platform support library that provides an abstraction layer for asynchronous I/O operations in Node.js. It handles low-level system calls and provides a consistent API for file system access, networking, timers, and other asynchronous operations across different operating systems. Libuv is a key component of Node.js's event-driven architecture, enabling efficient handling of concurrent connections.

### what is libuv in simple words
Libuv is a library that helps Node.js perform tasks like reading files, making network requests, and handling timers without blocking the execution of other code. It allows Node.js to manage multiple tasks at the same time, making it fast and efficient for building applications that need to handle many users or requests simultaneously.

### diagram of how libuv works
```plaintext
          ┌───────────────────────────────┐
          │         Node.js Application    │
          └───────────────────────────────┘
                     │
                     ▼
          ┌───────────────────────────────┐
          │         libuv Event Loop       │
          └───────────────────────────────┘
                     │
                     ▼
          ┌───────────────────────────────┐
          │   Asynchronous I/O Operations  │
          └───────────────────────────────┘
                     │
                     ▼
          ┌───────────────────────────────┐
          │   System Calls & OS APIs      │
          └───────────────────────────────┘
```

## Node.js C/C++ bindings
Node.js is built on top of the V8 JavaScript engine and uses C/C++ bindings to interface with the underlying system. These bindings allow Node.js to access low-level system resources, such as file systems, network sockets, and operating system APIs, while providing a high-level JavaScript interface for developers.

## Event Loop
The event loop is a core component of Node.js that enables its non-blocking, asynchronous behavior. It continuously checks for events and executes the corresponding callback functions when events occur. The event loop allows Node.js to handle multiple concurrent connections efficiently without blocking the execution of other code.

### Digram of Event Loop
```plaintext

          ┌───────────────────────────────┐
          │         Event Loop            │
          └───────────────────────────────┘
                     ▲        ▲
                     │        │
                     │        │
          ┌──────────┘        └──────────┐
          │                               │
  ┌─────────────────────┐       ┌─────────────────────┐
  │   I/O Operations    │       │   Timers & Events   │
  └─────────────────────┘       └─────────────────────┘
          ▲                               ▲
          │                               │
          └──────────┐        ┌──────────┘
                     │        │
                     ▼        ▼
          ┌───────────────────────────────┐
          │      Callback Functions       │
          └───────────────────────────────┘
```

## Call stack
The call stack is a data structure used by Node.js (and JavaScript in general) to keep track of function calls and their execution context. When a function is called, it is added to the top of the call stack, and when the function completes, it is removed from the stack. The call stack operates in a Last-In-First-Out (LIFO) manner, meaning that the most recently called function is executed first.

### Diagram of Call Stack
```plaintext
          ┌───────────────────────────────┐
          │         Call Stack            │
          └───────────────────────────────┘
                     ▲
                     │
          ┌───────────────────────────────┐
          │   Function A (Top of Stack)   │
          └───────────────────────────────┘
                     ▲
                     │
          ┌───────────────────────────────┐
          │   Function B                  │
          └───────────────────────────────┘
                     ▲
                     │
          ┌───────────────────────────────┐
          │   Function C (Bottom of Stack)│
          └───────────────────────────────┘
```

## Callback queue
The callback queue is a data structure used by Node.js to manage asynchronous operations and their associated callback functions. When an asynchronous operation (such as reading a file or making a network request) is initiated, its callback function is placed in the callback queue. The event loop continuously checks the callback queue and executes the callback functions in the order they were added, once the corresponding asynchronous operations are complete.

### Diagram of Callback Queue
```plaintext
          ┌───────────────────────────────┐
          │       Callback Queue           │
          └───────────────────────────────┘
                     ▲
                     │
          ┌───────────────────────────────┐
          │   Callback Function A         │
          └───────────────────────────────┘
                     ▲
                     │
          ┌───────────────────────────────┐
          │   Callback Function B         │
          └───────────────────────────────┘
                     ▲
                     │
          ┌───────────────────────────────┐
          │   Callback Function C         │
          └───────────────────────────────┘
```

## Microtask queue
The microtask queue is a data structure used by Node.js to manage microtasks, which are a type of asynchronous operation that is executed after the current operation completes but before the next event loop iteration. Microtasks are typically used for operations like promises and process.nextTick() callbacks. The microtask queue has a higher priority than the callback queue, meaning that microtasks are executed before any callbacks in the callback queue.

### Diagram of Microtask Queue
```plaintext
          ┌───────────────────────────────┐
          │       Microtask Queue          │
          └───────────────────────────────┘
                     ▲
                     │
          ┌───────────────────────────────┐
          │   Microtask A                 │
          └───────────────────────────────┘
                     ▲
                     │
          ┌───────────────────────────────┐
          │   Microtask B                 │
          └───────────────────────────────┘
                     ▲
                     │
          ┌───────────────────────────────┐
          │   Microtask C                 │
          └───────────────────────────────┘
```

### Complete diagram of Event Loop, Call Stack, Callback Queue, and Microtask Queue
```plaintext
          ┌───────────────────────────────┐
          │         Event Loop            │
          └───────────────────────────────┘
                     ▲        ▲
                     │        │
                     │        │
          ┌──────────┘        └──────────┐
          │                               │
  ┌─────────────────────┐       ┌─────────────────────┐
  │   I/O Operations    │       │   Timers & Events   │
  └─────────────────────┘       └─────────────────────┘
          ▲                               ▲
          │                               │
          └──────────┐        ┌──────────┘
                     │        │
                     ▼        ▼
          ┌───────────────────────────────┐
          │      Callback Functions       │
          └───────────────────────────────┘
                     ▲
                     │
          ┌───────────────────────────────┐
          │         Call Stack            │
          └───────────────────────────────┘
                     ▲
                     │
          ┌───────────────────────────────┐
          │       Microtask Queue          │
          └───────────────────────────────┘
                     ▲
                     │
          ┌───────────────────────────────┐
          │       Callback Queue           │
          └───────────────────────────────┘

```

## Thread pool
The thread pool is a collection of worker threads that Node.js uses to handle certain types of operations, such as file system access, DNS lookups, and other tasks that can be offloaded from the main event loop. The thread pool allows Node.js to perform these operations concurrently without blocking the execution of other code.

### Thread pool in simple words
The thread pool is like a team of workers that Node.js can use to handle tasks that take a long time to complete, such as reading files or making network requests. Instead of waiting for these tasks to finish, Node.js can send them to the thread pool, which allows the main event loop to continue processing other requests. Once the task is done, the thread pool notifies Node.js, and the result is handled in the callback function.

### Diagram of Thread Pool
```plaintext
          ┌───────────────────────────────┐
          │         Thread Pool            │
          └───────────────────────────────┘
                     ▲
                     │
          ┌───────────────────────────────┐
          │   Worker Thread A              │
          └───────────────────────────────┘
                     ▲
                     │
          ┌───────────────────────────────┐
          │   Worker Thread B              │
          └───────────────────────────────┘
                     ▲
                     │
          ┌───────────────────────────────┐
          │   Worker Thread C              │
          └───────────────────────────────┘
```


## OS-level asynchronous operations
OS-level asynchronous operations refer to tasks that are handled by the operating system rather than the Node.js runtime. These operations include file system access, network requests, and other I/O tasks that can be performed concurrently without blocking the main event loop. Node.js leverages the underlying operating system's capabilities to perform these operations efficiently, allowing it to handle multiple requests simultaneously.

### Example of OS-level asynchronous operations in Node.js:
```javascript
const fs = require('fs');

// Asynchronous file read operation
fs.readFile('example.txt', 'utf8', (err, data) => {
  if (err) {
    console.error('Error reading file:', err);
    return;
  }
  console.log('File contents:', data);
});

// Asynchronous network request using the 'http' module
const http = require('http');

const options = {
  hostname: 'www.example.com',
  port: 80,
  path: '/',
  method: 'GET'
};

const req = http.request(options, (res) => {
  let data = '';

  res.on('data', (chunk) => {
    data += chunk;
  });

  res.on('end', () => {
    console.log('Response from server:', data);
  });
});

req.on('error', (err) => {
  console.error('Error making request:', err);
});

req.end();
```

## How Node.js handles I/O
Node.js handles I/O operations using its event-driven, non-blocking architecture. When an I/O operation is initiated (such as reading a file, making a network request, or querying a database), Node.js offloads the operation to the underlying operating system or the thread pool, allowing the main event loop to continue processing other requests. Once the I/O operation is complete, the operating system or thread pool notifies Node.js, which then executes the corresponding callback function to handle the result. This approach allows Node.js to efficiently manage multiple concurrent I/O operations without blocking the execution of other code, making it well-suited for building scalable and high-performance applications.

### Example of how Node.js handles I/O:
```javascript
const fs = require('fs');

// Asynchronous file read operation
fs.readFile('example.txt', 'utf8', (err, data) => {
  if (err) {
    console.error('Error reading file:', err);
    return;
  }
  console.log('File contents:', data);
});

// Asynchronous network request using the 'http' module
const http = require('http');

const options = {
  hostname: 'www.example.com',
  port: 80,
  method: 'GET'
};

const req = http.request(options, (res) => {
  let data = '';

  res.on('data', (chunk) => {
    data += chunk;
  });

  res.on('end', () => {
    console.log('Response from server:', data);
  });
});

req.on('error', (err) => {
  console.error('Error making request:', err);
});

req.end();
```

## JavaScript thread vs libuv thread pool
In Node.js, there is a distinction between the JavaScript thread and the libuv thread pool. The JavaScript thread is the main thread that runs the event loop and executes JavaScript code. It is responsible for handling synchronous operations, managing the call stack, and processing events from the event loop.
The libuv thread pool, on the other hand, is a collection of worker threads that handle certain types of asynchronous operations, such as file system access, DNS lookups, and other tasks that can be offloaded from the main event loop. The thread pool allows Node.js to perform these operations concurrently without blocking the execution of other code.

### Diagram of JavaScript thread vs libuv thread pool
```plaintext
          ┌───────────────────────────────┐
          │       JavaScript Thread        │
          └───────────────────────────────┘
                     ▲
                     │
          ┌───────────────────────────────┐
          │         Event Loop            │
          └───────────────────────────────┘
                     ▲
                     │
          ┌───────────────────────────────┐
          │      Call Stack & Callbacks   │
          └───────────────────────────────┘
                     ▲
                     │
          ┌───────────────────────────────┐
          │       libuv Thread Pool        │
          └───────────────────────────────┘
                     ▲
                     │
          ┌───────────────────────────────┐
          │   Worker Threads for I/O Ops  │
          └───────────────────────────────┘
```

### Explanation of JavaScript thread vs libuv thread pool
- **JavaScript Thread**: This is the main thread where the Node.js event loop runs. It handles the execution of JavaScript code, manages the call stack, and processes events from the event loop. The JavaScript thread is single-threaded, meaning it can only execute one piece of code at a time.
- **libuv Thread Pool**: This is a pool of worker threads managed by the libuv library. It is used to handle certain types of asynchronous operations that can be offloaded from the main JavaScript thread, such as file system access, DNS lookups, and other I/O tasks. The thread pool allows Node.js to perform these operations concurrently without blocking the execution of other code in the JavaScript thread.


## CPU-bound vs I/O-bound tasks
In Node.js, tasks can be classified as either CPU-bound or I/O-bound based on the nature of the work they perform.
- **CPU-bound tasks**: These tasks require significant processing power and involve intensive computations, such as mathematical calculations, data processing, or complex algorithms. CPU-bound tasks can block the event loop and slow down the performance of a Node.js application if not handled properly. To mitigate this, CPU-bound tasks can be offloaded to worker threads or external services to prevent blocking the main event loop.
- **I/O-bound tasks**: These tasks involve input/output operations, such as reading from or writing to a file, making network requests, or querying a database. I/O-bound tasks are typically handled asynchronously in Node.js, allowing the event loop to continue processing other requests while waiting for the I/O operation to complete. This non-blocking behavior makes Node.js well-suited for handling a large number of concurrent I/O-bound tasks efficiently.

### Example of CPU-bound vs I/O-bound tasks in Node.js:
```javascript
// CPU-bound task: Calculating the factorial of a large number
function factorial(n) {
  if (n === 0 || n === 1) return 1;
  return n * factorial(n - 1);
}

// I/O-bound task: Reading a file asynchronously
const fs = require('fs');
fs.readFile('example.txt', 'utf8', (err, data) => {
  if (err) {
    console.error('Error reading file:', err);
    return;
  }
  console.log('File contents:', data);
});

```

## Blocking vs non-blocking operations
In Node.js, operations can be classified as either blocking or non-blocking based on how they affect the execution of other code in the event loop.
- **Blocking operations**: These operations halt the execution of the program until they are completed. During a blocking operation, the event loop is paused, and no other code can be executed. This can lead to performance bottlenecks, especially when handling multiple concurrent requests. Examples of blocking operations include synchronous file system access and CPU-intensive computations.

- **Non-blocking operations**: These operations allow the program to continue executing other code while waiting for the operation to complete. Non-blocking operations are typically handled asynchronously, using callbacks, promises, or async/await syntax. This allows Node.js to efficiently manage multiple concurrent requests without blocking the event loop. Examples of non-blocking operations include asynchronous file system access, network requests, and database queries.

## Synchronous vs asynchronous APIs
In Node.js, APIs can be classified as either synchronous or asynchronous based on how they handle operations and their impact on the event loop.
- **Synchronous APIs**: Synchronous APIs execute operations in a blocking manner, meaning that the program waits for the operation to complete before moving on to the next line of code. This can lead to performance issues, especially when dealing with I/O-bound tasks or CPU-intensive operations. Examples of synchronous APIs in Node.js include `fs.readFileSync()` and `fs.writeFileSync()` for file system access.
- **Asynchronous APIs**: Asynchronous APIs execute operations in a non-blocking manner, allowing the program to continue executing other code while waiting for the operation to complete. Asynchronous APIs typically use callbacks, promises, or async/await syntax to handle the results of the operation once it is finished. This approach enables Node.js to efficiently manage multiple concurrent requests without blocking the event loop. Examples of asynchronous APIs in Node.js include `fs.readFile()` and `fs.writeFile()` for file system access.

### Example of synchronous vs asynchronous APIs in Node.js:
```javascript
// Synchronous API: Reading a file synchronously
const fs = require('fs');
try {
  const data = fs.readFileSync('example.txt', 'utf8');
  console.log('File contents (synchronous):', data);
} catch (err) {
  console.error('Error reading file (synchronous):', err);
}

// Asynchronous API: Reading a file asynchronously
fs.readFile('example.txt', 'utf8', (err, data) => {
  if (err) {
    console.error('Error reading file (asynchronous):', err);
    return;
  }
  console.log('File contents (asynchronous):', data);
});
```

## Node.js execution lifecycle
The Node.js execution lifecycle refers to the sequence of events that occur from the start of a Node.js application to its termination. Understanding the execution lifecycle is important for developers to manage resources, handle events, and ensure proper cleanup of resources when the application exits.

### diagram of Node.js execution lifecycle
```plaintext
          ┌───────────────────────────────┐
          │      Application Start         │
          └───────────────────────────────┘
                     │
                     ▼
          ┌───────────────────────────────┐
          │   Initialization Phase         │
          └───────────────────────────────┘
                     │
                     ▼
          ┌───────────────────────────────┐
          │   Event Loop & I/O Handling    │
          └───────────────────────────────┘
                     │
                     ▼
          ┌───────────────────────────────┐
          │   Callback Execution Phase     │
          └───────────────────────────────┘
                     │
                     ▼
          ┌───────────────────────────────┐
          │   Cleanup & Resource Release   │
          └───────────────────────────────┘
                     │
                     ▼
          ┌───────────────────────────────┐
          │      Application Exit           │
          └───────────────────────────────┘
```

## Process lifecycle
The process lifecycle in Node.js refers to the stages that a Node.js process goes through from its creation to its termination. Understanding the process lifecycle is important for managing resources, handling events, and ensuring proper cleanup of resources when the application exits.

### Stages of the Node.js process lifecycle:
1. **Process Creation**: When a Node.js application is started, a new process is created by the operating system. This process is responsible for executing the Node.js runtime and the application code.
2. **Initialization**: During the initialization phase, Node.js sets up the necessary environment, loads required modules, and initializes the event loop. This phase prepares the application to handle incoming requests and events.
3. **Event Loop Execution**: After initialization, the Node.js process enters the event loop phase, where it continuously listens for events (such as incoming requests or completed I/O operations) and executes the corresponding callback functions. The event loop allows Node.js to handle multiple concurrent requests efficiently without blocking the execution of other code.
4. **Callback Execution**: When an event occurs, the corresponding callback function is executed. This phase involves processing the results of asynchronous operations and handling any application logic associated with the event.
5. **Cleanup and Resource Release**: Before the process exits, Node.js performs cleanup tasks, such as releasing resources, closing open file descriptors, and terminating any remaining asynchronous operations. This phase ensures that the application exits gracefully and does not leave any resources in an inconsistent state.
6. **Process Termination**: Finally, the Node.js process terminates, and control is returned to the operating system. The exit code of the process indicates whether the application completed successfully or encountered an error during execution.

# Node.js Modules

## CommonJS

## `require()`
require() is a built-in function in Node.js that is used to import modules, JSON files, and local files into a Node.js application. It allows developers to include external code and functionality in their applications, promoting code reusability and modularity.

### Example of using `require()` to import a module:
```javascript
// Importing the built-in 'fs' module for file system operations
const fs = require('fs');

// Using the 'fs' module to read a file asynchronously
fs.readFile('example.txt', 'utf8', (err, data) => {
  if (err) {
    console.error('Error reading file:', err);
    return;
  }
  console.log('File contents:', data);
});
```

## `module.exports`
`module.exports` is a special object in Node.js that is used to define what a module exports and makes available for other modules to import using `require()`. By assigning values, functions, or objects to `module.exports`, developers can control the public interface of their modules, allowing other parts of the application to access and use the exported functionality.

### Example of using `module.exports` to export a function:
```javascript
// math.js - A simple module that exports a function to add two numbers
function add(a, b) {
  return a + b;
}

// Exporting the 'add' function using module.exports
module.exports = add;
```

## `exports`
`exports` is a shorthand reference to `module.exports` in Node.js. It allows developers to export multiple properties or functions from a module in a more concise way. However, it's important to note that if you assign a new value to `exports`, it will break the reference to `module.exports`, and the module will not export the intended functionality.

### Example of using `exports` to export multiple functions:
```javascript
// math.js - A simple module that exports multiple functions
// Exporting the 'add' function
exports.add = function(a, b) {
  return a + b;
};

// Exporting the 'subtract' function
exports.subtract = function(a, b) {
  return a - b;
};
```

## Module caching
Module caching is a feature in Node.js that allows modules to be loaded and executed only once, even if they are required multiple times in different parts of the application. When a module is first loaded using `require()`, Node.js caches the module's exports in memory. Subsequent calls to `require()` for the same module will return the cached version, rather than reloading and executing the module again. This improves performance and ensures that the same instance of the module is used throughout the application.

### Example of module caching in Node.js:
```javascript
// math.js - A simple module that exports a function
function add(a, b) {
  console.log('Executing add function');
  return a + b;
}

// Exporting the 'add' function
module.exports = add;
```

```javascript
// app.js - Main application file
const add = require('./math');

// First call to the 'add' function
console.log(add(2, 3)); // Output: Executing add function \n 5

// Second call to the 'add' function (module is cached, so it won't execute again)
console.log(add(4, 5)); // Output: 9 (no "Executing add function" message, as the module is cached)
```

## Module resolution
Module resolution is the process by which Node.js determines the location of a module when it is required using the `require()` function. When a module is requested, Node.js follows a specific algorithm to locate the module file, which includes checking built-in modules, local files, and node_modules directories. The resolution process ensures that the correct module is loaded and executed in the application.

### Steps of module resolution in Node.js:
1. **Check for built-in modules**: Node.js first checks if the requested module is a built-in module (e.g., `fs`, `http`, etc.). If it is, Node.js loads the built-in module and returns it.
2. **Check for local files**: If the module is not a built-in module, Node.js checks if the requested module is a local file. It looks for the file in the current directory and its parent directories, following the specified path in the `require()` statement. Node.js will look for files with the following extensions in order: `.js`, `.json`, and `.node`.
3. **Check for node_modules directories**: If the module is not found as a local file, Node.js searches for the module in the `node_modules` directories. It starts from the current directory and moves up the directory tree, checking each `node_modules` folder for the requested module.
4. **Load the module**: Once the module is found, Node.js loads and executes the module, caching its exports for future use. If the module cannot be found after following the resolution steps, Node.js throws a `MODULE_NOT_FOUND` error.

## `__dirname` and `__filename`
`__dirname` and `__filename` are special variables in Node.js that provide information about the current module's directory and file path, respectively. They are useful for working with file paths and directories in a Node.js application.

### `__dirname`
`__dirname` is a variable that contains the absolute path of the directory in which the currently executing script resides. It is useful for constructing file paths relative to the current module's location.

### Example of using `__dirname`:
```javascript
const path = require('path');
// Constructing a file path relative to the current module's directory
const filePath = path.join(__dirname, 'example.txt');
console.log('File path:', filePath);
```

### `__filename`
`__filename` is a variable that contains the absolute path of the currently executing script file. It is useful for obtaining the full path of the current module, which can be helpful for logging, debugging, or working with file paths.

### Example of using `__filename`:
```javascript
const path = require('path');
// Getting the absolute path of the currently executing script file
console.log('Current file path:', __filename);
```

## Circular dependencies
Circular dependencies occur when two or more modules depend on each other, creating a loop in the dependency graph. This can lead to issues such as incomplete module exports, unexpected behavior, and difficulties in maintaining the code. In Node.js, circular dependencies can be handled, but they should be avoided whenever possible to ensure clean and maintainable code.

### Example of circular dependencies in Node.js:
```javascript
// moduleA.js
const moduleB = require('./moduleB');

function functionA() {
  console.log('Function A from module A');
  moduleB.functionB();
}

module.exports = { functionA };
```

```javascript
// moduleB.js
const moduleA = require('./moduleA');

function functionB() {
  console.log('Function B from module B');
  moduleA.functionA();
}

module.exports = { functionB };
```

## ES Modules (ESM)

## `"type": "module"`
In Node.js, the `"type": "module"` field in the `package.json` file is used to indicate that the project should be treated as an ECMAScript Module (ESM) project. When this field is set to `"module"`, Node.js will interpret `.js` files as ESM by default, allowing developers to use the `import` and `export` syntax for module management instead of the CommonJS `require()` and `module.exports`.

### Example of using `"type": "module"` in `package.json`:
```json
{
  "name": "my-esm-project",
  "version": "1.0.0",
  "type": "module",
  "main": "index.js",
  "scripts": {
    "start": "node index.js"
  }
}
```

## `import` and `export`
In Node.js, when using ECMAScript Modules (ESM), the `import` and `export` statements are used to manage module dependencies and share functionality between different files. The `import` statement is used to bring in functions, objects, or values from other modules, while the `export` statement is used to make functions, objects, or values available for import in other modules.

### Example of using `import` and `export` in Node.js ESM:
```javascript
// math.js - A simple module that exports a function
export function add(a, b) {
  return a + b;
}
```

```javascript
// app.js - Main application file
import { add } from './math.js';

// Using the imported 'add' function
const result = add(2, 3);

console.log('Result of addition:', result); // Output: Result of addition: 5
```

## Default exports
In Node.js, when using ECMAScript Modules (ESM), a module can have a default export, which allows a single value, function, or object to be exported from the module. The default export can be imported without using curly braces, making it convenient for modules that primarily export one main functionality.

### Example of using default exports in Node.js ESM:
```javascript
// math.js - A simple module that exports a default function
export default function add(a, b) {
  return a + b;
}
```

```javascript
// app.js - Main application file
import add from './math.js'; // Importing the default export

// Using the imported 'add' function
const result = add(2, 3);

console.log('Result of addition:', result); // Output: Result of addition: 5
```

## Named exports
In Node.js, when using ECMAScript Modules (ESM), named exports allow a module to export multiple values, functions, or objects with specific names. Named exports can be imported using their exact names, and multiple named exports can be imported from the same module.

### Example of using named exports in Node.js ESM:
```javascript
// math.js - A simple module that exports multiple named functions
export function add(a, b) {
  return a + b;
}

export function subtract(a, b) {
  return a - b;
}
```

```javascript
// app.js - Main application file
import { add, subtract } from './math.js'; // Importing named exports

// Using the imported functions
const sum = add(2, 3);
const difference = subtract(5, 2);

console.log('Result of addition:', sum); // Output: Result of addition: 5
console.log('Result of subtraction:', difference); // Output: Result of subtraction: 3
```

## Dynamic `import()`
In Node.js, the dynamic `import()` function allows developers to load modules asynchronously at runtime, rather than statically at the top of the file. This feature is useful for code-splitting, lazy loading, and conditionally importing modules based on certain conditions. The `import()` function returns a promise that resolves to the module's exports, allowing developers to handle the imported module asynchronously.

### Example of using dynamic `import()` in Node.js:
```javascript
// Dynamically importing a module based on a condition
const condition = true;

if (condition) {
  import('./math.js')
    .then((mathModule) => {
      const result = mathModule.add(2, 3);
      console.log('Result of addition:', result); // Output: Result of addition: 5
    })
    .catch((error) => {
      console.error('Error importing module:', error);
    });
} else {
  console.log('Condition not met, module not imported.');
}
```

## `import.meta`
In Node.js, `import.meta` is an object that provides metadata about the current module when using ECMAScript Modules (ESM). It contains information such as the URL of the module, which can be useful for determining the module's location or for performing operations based on the module's context. The `import.meta` object is read-only and cannot be modified.

### Example of using `import.meta` in Node.js:
```javascript
// Displaying the URL of the current module using import.meta
console.log('Current module URL:', import.meta.url);
```

## `import.meta.url`
In Node.js, `import.meta.url` is a property of the `import.meta` object that provides the URL of the current module when using ECMAScript Modules (ESM). It returns a string representing the absolute URL of the module file, which can be useful for determining the module's location or for performing operations based on the module's context. The URL is typically in the form of a `file://` URL for local files.

### Example of using `import.meta.url` in Node.js:
```javascript
// Displaying the URL of the current module using import.meta.url
console.log('Current module URL:', import.meta.url);
```

## ESM resolution
ESM resolution in Node.js refers to the process by which the Node.js runtime locates and loads ECMAScript Modules (ESM) when they are imported using the `import` statement. The resolution process follows a specific algorithm to determine the correct module file based on the import path, file extensions, and the module's location in the file system. ESM resolution ensures that the correct module is loaded and executed in the application.

### Steps of ESM resolution in Node.js:
1. **Check for built-in modules**: Node.js first checks if the requested module is a built-in module (e.g., `fs`, `http`, etc.). If it is, Node.js loads the built-in module and returns it.
2. **Check for local files**: If the module is not a built-in module, Node.js checks if the requested module is a local file. It looks for the file in the current directory and its parent directories, following the specified path in the `import` statement. Node.js will look for files with the following extensions in order: `.js`, `.mjs`, and `.json`.
3. **Check for node_modules directories**: If the module is not found as a local file, Node.js searches for the module in the `node_modules` directories. It starts from the current directory and moves up the directory tree, checking each `node_modules` folder for the requested module.
4. **Load the module**: Once the module is found, Node.js loads and executes the module, caching its exports for future use. If the module cannot be found after following the resolution steps, Node.js throws a `MODULE_NOT_FOUND` error.

## Module Systems

## CommonJS vs ESM
CommonJS and ECMAScript Modules (ESM) are two different module systems used in Node.js for managing dependencies and sharing functionality between different files. Each system has its own syntax, features, and use cases, and developers can choose the appropriate module system based on their project requirements.

### CommonJS
- **Syntax**: CommonJS uses the `require()` function to import modules and `module.exports` or `exports` to export functionality.
- **Synchronous loading**: CommonJS modules are loaded synchronously, meaning that the module is loaded and executed before the next line of code is executed. This can lead to blocking behavior, especially for I/O-bound tasks.
- **File extensions**: CommonJS modules typically use the `.js` file extension.
- **Use case**: CommonJS is widely used in Node.js applications and is suitable for server-side development, where synchronous loading is acceptable and the module system is well-established.

### ESM
- **Syntax**: ESM uses the `import` and `export` statements to manage dependencies and share functionality between modules.
- **Asynchronous loading**: ESM modules are loaded asynchronously, allowing for non-blocking behavior and better performance in certain scenarios, such as code-splitting and lazy loading.
- **File extensions**: ESM modules can use the `.js`, `.mjs`, or `.json` file extensions, with `.mjs` being the preferred extension for ESM modules.
- **Use case**: ESM is the standard module system for JavaScript and is suitable for both client-side and server-side development. It is recommended for new projects and is compatible with modern JavaScript features.

## When to use each

### When to use CommonJS
- **Legacy projects**: If you are working on an existing Node.js project that already uses CommonJS, it may be easier to continue using CommonJS for consistency and compatibility.
- **Synchronous loading**: If your application requires synchronous module loading and you are not concerned about blocking behavior, CommonJS may be a suitable choice.
- **Server-side development**: CommonJS is well-established in the Node.js ecosystem and is widely used for server-side development, making it a good choice for backend applications.

### When to use ESM
- **New projects**: For new Node.js projects, it is recommended to use ESM, as it is the standard module system for JavaScript and provides better support for modern features and syntax.
- **Asynchronous loading**: If your application benefits from asynchronous module loading, such as code-splitting or lazy loading, ESM is the preferred choice.
- **Client-side development**: ESM is compatible with both client-side and server-side development, making it a good choice for projects that require code sharing between the frontend and backend.

## Mixing CommonJS and ESM
Mixing CommonJS and ECMAScript Modules (ESM) in a Node.js project can be done, but it requires careful consideration of the module system being used and the compatibility between the two. Node.js provides mechanisms to allow interoperability between CommonJS and ESM, but developers should be aware of the differences in syntax, loading behavior, and module resolution.

### Example of mixing CommonJS and ESM in Node.js:
```javascript
// CommonJS module (math.js)
const add = (a, b) => a + b;

module.exports = { add };
```

```javascript
// ESM module (app.mjs)
import { add } from './math.js'; // Importing CommonJS module using ESM syntax

const result = add(2, 3);
console.log('Result of addition:', result); // Output: Result of addition: 5
```

## Package boundaries
In Node.js, package boundaries refer to the separation of code and functionality into distinct packages or modules. Each package can have its own `package.json` file, which defines the package's metadata, dependencies, and entry points. Package boundaries help organize code, promote modularity, and facilitate dependency management in Node.js applications.

### Example of package boundaries in Node.js:
```plaintext
my-app/
├── package.json          // Main package metadata and dependencies
├── index.js              // Main application entry point
├── utils/
│   ├── package.json      // Utility package metadata and dependencies
│   └── math.js           // Utility module for mathematical operations
├── services/
│   ├── package.json      // Services package metadata and dependencies
│   └── api.js            // Service module for API interactions
```

## Node module resolution algorithm
The Node.js module resolution algorithm is the process by which Node.js determines the location of a module when it is required using the `require()` function or imported using the `import` statement. The algorithm follows a specific set of steps to locate and load the requested module, ensuring that the correct module is executed in the application.

### Steps of the Node.js module resolution algorithm:
1. **Check for built-in modules**: Node.js first checks if the requested module is a built-in module (e.g., `fs`, `http`, etc.). If it is, Node.js loads the built-in module and returns it.
2. **Check for local files**: If the module is not a built-in module, Node.js checks if the requested module is a local file. It looks for the file in the current directory and its parent directories, following the specified path in the `require()` or `import` statement. Node.js will look for files with the following extensions in order: `.js`, `.json`, and `.node`.
3. **Check for node_modules directories**: If the module is not found as a local file, Node.js searches for the module in the `node_modules` directories. It starts from the current directory and moves up the directory tree, checking each `node_modules` folder for the requested module.
4. **Load the module**: Once the module is found, Node.js loads and executes the module, caching its exports for future use. If the module cannot be found after following the resolution steps, Node.js throws a `MODULE_NOT_FOUND` error.

# Built-in Node.js Modules

## Learn these without frameworks:

## `fs` (File System)
The `fs` module in Node.js is a built-in module that provides an API for interacting with the file system. It allows developers to perform various file operations, such as reading, writing, updating, and deleting files and directories. The `fs` module supports both synchronous and asynchronous methods, enabling developers to choose the appropriate approach based on their application's requirements.

### Example of using the `fs` module in Node.js:
```javascript
const fs = require('fs');

// Asynchronous file read operation
fs.readFile('example.txt', 'utf8', (err, data) => {
  if (err) {
    console.error('Error reading file:', err);
    return;
  }
  console.log('File contents:', data);
});

// Synchronous file write operation
try {
  fs.writeFileSync('output.txt', 'Hello, Node.js!');
  console.log('File written successfully.');
} catch (err) {
  console.error('Error writing file:', err);
}
```

## `path`
The `path` module in Node.js is a built-in module that provides utilities for working with file and directory paths. It allows developers to manipulate and resolve file paths in a platform-independent manner, making it easier to work with file systems across different operating systems. The `path` module includes methods for joining, resolving, normalizing, and parsing paths.

### Example of using the `path` module in Node.js:
```javascript
const path = require('path');

// Joining paths
const joinedPath = path.join(__dirname, 'folder', 'file.txt');

// Resolving paths
const resolvedPath = path.resolve('folder', 'file.txt');

// Normalizing paths
const normalizedPath = path.normalize('folder//subfolder/../file.txt');

console.log('Joined Path:', joinedPath);
console.log('Resolved Path:', resolvedPath);
console.log('Normalized Path:', normalizedPath);
```

## `http`
The `http` module in Node.js is a built-in module that provides an API for creating HTTP servers and making HTTP requests. It allows developers to build web applications, RESTful APIs, and handle client-server communication over the HTTP protocol. The `http` module supports both server-side and client-side functionality, enabling developers to create web servers and make HTTP requests to external resources.

### Example of using the `http` module in Node.js:
```javascript
const http = require('http');

// Creating an HTTP server
const server = http.createServer((req, res) => {
  res.statusCode = 200;
  res.setHeader('Content-Type', 'text/plain');
  res.end('Hello, Node.js HTTP server!');
});

// Starting the server on port 3000
server.listen(3000, () => {
  console.log('Server running at http://localhost:3000/');
});
```

## `https`
The `https` module in Node.js is a built-in module that provides an API for creating HTTPS servers and making HTTPS requests. It allows developers to build secure web applications, RESTful APIs, and handle client-server communication over the HTTPS protocol. The `https` module is similar to the `http` module but adds support for SSL/TLS encryption, ensuring that data transmitted between the client and server is secure.

### Example of using the `https` module in Node.js:
```javascript
const https = require('https');

// Creating an HTTPS server
const options = {
  key: fs.readFileSync('server.key'), // Path to the private key
  cert: fs.readFileSync('server.cert') // Path to the certificate
};

const server = https.createServer(options, (req, res) => {
  res.writeHead(200, { 'Content-Type': 'text/plain' });
  res.end('Hello, Node.js HTTPS server!');
});

// Starting the server on port 3000
server.listen(3000, () => {
  console.log('HTTPS server running at https://localhost:3000/');
});
```

## difference between `http` and `https`
The main difference between the `http` and `https` modules in Node.js lies in the security of the communication between the client and server. The `http` module is used for creating HTTP servers and making HTTP requests, which transmit data in plaintext and are not encrypted. In contrast, the `https` module is used for creating HTTPS servers and making HTTPS requests, which encrypt the data transmitted between the client and server using SSL/TLS protocols. This encryption ensures that sensitive information, such as passwords and personal data, is protected from eavesdropping and tampering during transmission.

## `url`
The `url` module in Node.js is a built-in module that provides utilities for URL resolution and parsing. It allows developers to work with URLs, extract components, and manipulate query strings in a convenient manner. The `url` module includes methods for parsing URLs into their constituent parts, formatting URLs, and resolving relative URLs against a base URL.

### Example of using the `url` module in Node.js:
```javascript
const url = require('url');

// Parsing a URL
const parsedUrl = url.parse('https://www.example.com:8080/path/to/resource?query=string#hash');
console.log('Parsed URL:', parsedUrl);

// Formatting a URL
const formattedUrl = url.format({
  protocol: 'https',
  hostname: 'www.example.com',
  port: 8080,
  pathname: '/path/to/resource',
  query: { query: 'string' },
  hash: '#hash'
});

console.log('Formatted URL:', formattedUrl);
```

## `querystring`
The `querystring` module in Node.js is a built-in module that provides utilities for parsing and formatting URL query strings. It allows developers to easily convert query strings into JavaScript objects and vice versa, making it convenient to work with query parameters in web applications. The `querystring` module includes methods for parsing query strings, stringifying objects into query strings, and encoding/decoding query parameters.

### Example of using the `querystring` module in Node.js:
```javascript
const querystring = require('querystring');

// Parsing a query string into an object
const parsedQuery = querystring.parse('name=John&age=30&city=New%20York');
console.log('Parsed Query:', parsedQuery);

// Stringifying an object into a query string
const queryObject = { name: 'Jane', age: 25, city: 'Los Angeles' };
const stringifiedQuery = querystring.stringify(queryObject);
console.log('Stringified Query:', stringifiedQuery);
```

## `events`
The `events` module in Node.js is a built-in module that provides an implementation of the EventEmitter class, which allows developers to create and manage custom events in their applications. The `events` module enables the creation of event-driven architectures, where different parts of the application can communicate with each other by emitting and listening for events. This promotes decoupling and modularity in the codebase.

### Example of using the `events` module in Node.js:
```javascript
const EventEmitter = require('events');

// Creating a custom event emitter class
class MyEmitter extends EventEmitter {}

// Creating an instance of the custom event emitter
const myEmitter = new MyEmitter();

// Listening for a custom event
myEmitter.on('greet', (name) => {
  console.log(`Hello, ${name}!`);
});

// Emitting the custom event
myEmitter.emit('greet', 'Alice'); // Output: Hello, Alice!
```

## all events in Node.js
In Node.js, the `events` module provides a wide range of events that can be emitted and listened to within an application. These events can be categorized into built-in events, custom events, and system events. Below is a list of some common events in Node.js:
### Built-in Events
- **'data'**: Emitted when data is available to be read from a stream.
- **'end'**: Emitted when there is no more data to be read from a stream.
- **'error'**: Emitted when an error occurs during an operation.
- **'close'**: Emitted when a stream or resource is closed.
- **'finish'**: Emitted when a writable stream has finished writing data.

### Custom Events
- Developers can create their own custom events using the EventEmitter class. These events can be named according to the application's requirements and can carry any data or payload needed for the event handling.

### example of built-in and custom events in Node.js:
```javascript
const EventEmitter = require('events');

// Creating a custom event emitter class
class MyEmitter extends EventEmitter {}

// Creating an instance of the custom event emitter
const myEmitter = new MyEmitter();

// Listening for a built-in 'data' event
myEmitter.on('data', (chunk) => {
  console.log(`Received data: ${chunk}`);
});

// Listening for a custom 'greet' event
myEmitter.on('greet', (name) => {
  console.log(`Hello, ${name}!`);
});

// Emitting the built-in 'data' event
myEmitter.emit('data', 'This is a data chunk.'); // Output: Received data: This is a data chunk.

// Emitting the custom 'greet' event
myEmitter.emit('greet', 'Alice'); // Output: Hello, Alice!
```

## `stream`
The `stream` module in Node.js is a built-in module that provides an API for working with streaming data. Streams are a powerful way to handle large amounts of data efficiently, allowing developers to read or write data in chunks rather than loading the entire dataset into memory at once. The `stream` module includes various types of streams, such as readable streams, writable streams, duplex streams, and transform streams, each serving different purposes in data processing.

### Example of using the `stream` module in Node.js:
```javascript
const { Readable, Writable } = require('stream');

// Creating a readable stream
const readableStream = new Readable({
  read(size) {
    this.push('Hello, ');
    this.push('Node.js ');
    this.push('Streams!');
    this.push(null); // Signifies the end of the stream
  }
});

// Creating a writable stream
const writableStream = new Writable({
  write(chunk, encoding, callback) {
    console.log(`Received chunk: ${chunk.toString()}`);
    callback();
  }
});

// Piping the readable stream to the writable stream
readableStream.pipe(writableStream);
```

## `buffer`
The `buffer` module in Node.js is a built-in module that provides a way to work with binary data in the form of buffers. Buffers are used to represent raw binary data and are particularly useful when dealing with streams, file I/O, and network communication. The `buffer` module allows developers to create, manipulate, and convert buffers, enabling efficient handling of binary data in Node.js applications.

### Example of using the `buffer` module in Node.js:
```javascript
const { Buffer } = require('buffer');

// Creating a buffer from a string
const bufferFromString = Buffer.from('Hello, Node.js Buffer!');

// Creating a buffer of a specific size
const bufferOfSize = Buffer.alloc(10); // Creates a buffer of 10 bytes initialized to zero

// Writing data to the buffer
bufferOfSize.write('Node.js');

// Reading data from the buffer
console.log('Buffer from string:', bufferFromString.toString()); // Output: Hello, Node.js Buffer!
console.log('Buffer of size:', bufferOfSize.toString()); // Output: Node.js
```

## `util`
The `util` module in Node.js is a built-in module that provides utility functions for various purposes, such as debugging, formatting, and inheritance. It includes functions for working with objects, strings, and asynchronous operations, making it easier for developers to perform common tasks in their applications. The `util` module is often used in conjunction with other Node.js modules to enhance functionality and improve code readability.

### Example of using the `util` module in Node.js:
```javascript
const util = require('util');

// Using util.format() to format a string
const name = 'Alice';

const age = 30;
const formattedString = util.format('My name is %s and I am %d years old.', name, age);
console.log(formattedString); // Output: My name is Alice and I am 30 years old.

// Using util.promisify() to convert a callback-based function to a promise-based function
const fs = require('fs');

const readFileAsync = util.promisify(fs.readFile);

readFileAsync('example.txt', 'utf8')
  .then((data) => {
    console.log('File contents:', data);
  })
  .catch((err) => {
    console.error('Error reading file:', err);
  });
```

## `crypto`
The `crypto` module in Node.js is a built-in module that provides cryptographic functionality, including a set of wrappers for OpenSSL's hash, HMAC, cipher, decipher, sign, and verify functions. It allows developers to perform various cryptographic operations, such as hashing data, generating random bytes, encrypting and decrypting data, and creating digital signatures. The `crypto` module is essential for implementing security features in Node.js applications.

### Example of using the `crypto` module in Node.js:
```javascript
const crypto = require('crypto');

// Generating a random string of bytes
const randomBytes = crypto.randomBytes(16).toString('hex');

console.log('Random Bytes:', randomBytes);

// Creating a hash of a string using SHA-256
const hash = crypto.createHash('sha256').update('Hello, Node.js!').digest('hex');
console.log('SHA-256 Hash:', hash);

// Encrypting and decrypting data using AES-256-CBC
const algorithm = 'aes-256-cbc';   
const key = crypto.randomBytes(32); // Generate a random key
const iv = crypto.randomBytes(16);  // Generate a random initialization vector

const cipher = crypto.createCipheriv(algorithm, key, iv);
let encrypted = cipher.update('Hello, Node.js!', 'utf8', 'hex');

encrypted += cipher.final('hex');
console.log('Encrypted Data:', encrypted);

const decipher = crypto.createDecipheriv(algorithm, key, iv);
let decrypted = decipher.update(encrypted, 'hex', 'utf8');

decrypted += decipher.final('utf8');
console.log('Decrypted Data:', decrypted); // Output: Hello, Node.js!
```

## `os`
The `os` module in Node.js is a built-in module that provides operating system-related utility methods and properties. It allows developers to retrieve information about the underlying operating system, such as CPU architecture, memory usage, network interfaces, and system uptime. The `os` module is useful for building cross-platform applications that need to adapt to different operating systems or gather system-level information.

### Example of using the `os` module in Node.js:
```javascript
const os = require('os');

// Getting the operating system platform
const platform = os.platform();

console.log('Operating System Platform:', platform);

// Getting the CPU architecture
const architecture = os.arch();

console.log('CPU Architecture:', architecture);

// Getting the total system memory
const totalMemory = os.totalmem();

console.log('Total System Memory:', totalMemory, 'bytes');

// Getting the free system memory
const freeMemory = os.freemem();

console.log('Free System Memory:', freeMemory, 'bytes');

// Getting the system uptime
const uptime = os.uptime();

console.log('System Uptime:', uptime, 'seconds');
```

## `process`
The `process` module in Node.js is a built-in module that provides information and control over the current Node.js process. It allows developers to access environment variables, command-line arguments, and process-related information, as well as to manage the process lifecycle. The `process` module is essential for building command-line applications, managing application behavior, and interacting with the operating system.

### Example of using the `process` module in Node.js:
```javascript
const process = require('process');

// Accessing command-line arguments
const args = process.argv.slice(2); // Exclude the first two default arguments (node and script path)
console.log('Command-line arguments:', args);

// Accessing environment variables
const envVar = process.env.MY_ENV_VAR || 'Default Value';

console.log('Environment Variable MY_ENV_VAR:', envVar);

// Getting the current working directory
const currentWorkingDirectory = process.cwd();
console.log('Current Working Directory:', currentWorkingDirectory);

// Exiting the process with a specific exit code
process.exit(0); // Exit with code 0 (success)
```

## `child_process`
The `child_process` module in Node.js is a built-in module that provides the ability to spawn and manage child processes. It allows developers to execute external commands, run scripts, and create new processes that can run concurrently with the main Node.js process. The `child_process` module supports both synchronous and asynchronous methods for creating child processes, enabling developers to choose the appropriate approach based on their application's requirements.

### Example of using the `child_process` module in Node.js:
```javascript
const { exec } = require('child_process');

// Executing a shell command asynchronously
exec('ls -l', (error, stdout, stderr) => {
  if (error) {
    console.error(`Error executing command: ${error.message}`);
    return;
  }
  if (stderr) {
    console.error(`Command stderr: ${stderr}`);
    return;
  }
  console.log(`Command output:\n${stdout}`);
});
```

## `worker_threads`
The `worker_threads` module in Node.js is a built-in module that provides an API for creating and managing worker threads. Worker threads allow developers to run JavaScript code in parallel, enabling concurrent execution of tasks and improving performance for CPU-intensive operations. Each worker thread runs in its own isolated context, allowing for safe and efficient multi-threading in Node.js applications.

### Example of using the `worker_threads` module in Node.js:
```javascript
const { Worker, isMainThread, parentPort } = require('worker_threads');

if (isMainThread) {
  // Main thread: create a new worker
  const worker = new Worker(__filename);

  // Listen for messages from the worker
  worker.on('message', (message) => {
    console.log(`Received message from worker: ${message}`);
  });

  // Send a message to the worker
  worker.postMessage('Hello, Worker!');
} else {
  // Worker thread: listen for messages from the main thread
  parentPort.on('message', (message) => {
    console.log(`Received message from main thread: ${message}`);
    // Send a response back to the main thread
    parentPort.postMessage('Hello, Main Thread!');
  });
}
```

## `cluster`
The `cluster` module in Node.js is a built-in module that provides an API for creating and managing a cluster of Node.js processes. It allows developers to take advantage of multi-core systems by creating multiple worker processes that can share the same server port. The `cluster` module enables load balancing and improves the performance and scalability of Node.js applications, especially for handling high traffic and concurrent requests.

### Example of using the `cluster` module in Node.js:
```javascript
const cluster = require('cluster');
const http = require('http');

if (cluster.isMaster) {
  // Master process: fork worker processes
  const numCPUs = require('os').cpus().length;
  console.log(`Master process is running. Forking ${numCPUs} workers...`);

  for (let i = 0; i < numCPUs; i++) {
    cluster.fork();
  }

  // Listen for worker exit events
  cluster.on('exit', (worker, code, signal) => {
    console.log(`Worker ${worker.process.pid} exited with code ${code} and signal ${signal}`);
    // Optionally, you can fork a new worker to replace the exited one
    cluster.fork();
  });
} else {
  // Worker process: create an HTTP server
  http.createServer((req, res) => {
    res.writeHead(200);
    res.end(`Hello from worker ${process.pid}`);
  }).listen(3000);

  console.log(`Worker ${process.pid} started and listening on port 3000`);
}
```

## `net`
The `net` module in Node.js is a built-in module that provides an API for creating and managing TCP servers and clients. It allows developers to build network applications that can communicate over the TCP protocol, enabling the creation of custom protocols, chat servers, and other networked applications. The `net` module supports both server-side and client-side functionality, allowing for bidirectional communication between connected sockets.

### Example of using the `net` module in Node.js:
```javascript
const net = require('net');

// Creating a TCP server
const server = net.createServer((socket) => {
  console.log('Client connected');

  // Listening for data from the client
  socket.on('data', (data) => {
    console.log(`Received data from client: ${data}`);
    // Echoing the data back to the client
    socket.write(`Echo: ${data}`);
  });

  // Handling client disconnection
  socket.on('end', () => {
    console.log('Client disconnected');
  });
});

// Starting the server on port 3000
server.listen(3000, () => {
  console.log('TCP server listening on port 3000');
});
```

## `dns`
The `dns` module in Node.js is a built-in module that provides an API for performing DNS (Domain Name System) lookups and resolving domain names to IP addresses. It allows developers to query DNS records, perform reverse lookups, and resolve hostnames in a non-blocking manner. The `dns` module is useful for building network applications that require domain name resolution and for interacting with DNS servers.

### Example of using the `dns` module in Node.js:
```javascript
const dns = require('dns');

// Performing a DNS lookup for a domain name
dns.lookup('www.example.com', (err, address, family) => {
  if (err) {
    console.error('DNS lookup error:', err);
    return;
  }
  console.log(`Address: ${address}, Family: IPv${family}`);
});

// Performing a reverse DNS lookup for an IP address
dns.reverse('', (err, hostnames) => {
  if (err) {
    console.error('Reverse DNS lookup error:', err);
    return;
  }
  console.log(`Hostnames for IP address: ${hostnames}`);
});
```

## `readline`
The `readline` module in Node.js is a built-in module that provides an interface for reading input from a readable stream (such as `process.stdin`) one line at a time. It allows developers to create command-line interfaces, interactive prompts, and read user input in a convenient manner. The `readline` module supports both synchronous and asynchronous operations, making it suitable for various use cases.

### Example of using the `readline` module in Node.js:
```javascript
const readline = require('readline');

// Creating a readline interface
const rl = readline.createInterface({
  input: process.stdin,
  output: process.stdout
});

// Prompting the user for input
rl.question('What is your name? ', (name) => {
  console.log(`Hello, ${name}!`);
  rl.close(); // Closing the readline interface
});
```

## `zlib`
The `zlib` module in Node.js is a built-in module that provides an API for compressing and decompressing data using the zlib compression library. It allows developers to work with compressed data streams, enabling efficient storage and transmission of data. The `zlib` module supports various compression algorithms, such as Gzip and Deflate, and provides both synchronous and asynchronous methods for compression and decompression.

### Example of using the `zlib` module in Node.js:
```javascript
const zlib = require('zlib');

// Compressing a string using Gzip
const input = 'Hello, Node.js zlib module!';

zlib.gzip(input, (err, compressedData) => {
  if (err) {
    console.error('Error compressing data:', err);
    return;
  }
  console.log('Compressed Data:', compressedData);

  // Decompressing the compressed data
  zlib.gunzip(compressedData, (err, decompressedData) => {
    if (err) {
      console.error('Error decompressing data:', err);
      return;
    }
    console.log('Decompressed Data:', decompressedData.toString());
  });
});
```

## `assert`
The `assert` module in Node.js is a built-in module that provides a set of assertion functions for testing and validating conditions in code. It allows developers to write tests and verify that certain conditions hold true during the execution of their applications. The `assert` module is commonly used in unit testing and debugging to ensure that code behaves as expected.

### Example of using the `assert` module in Node.js:
```javascript
const assert = require('assert');

// Using assert.strictEqual() to test equality
const actualValue = 5;
const expectedValue = 5;
assert.strictEqual(actualValue, expectedValue, 'Values are not equal!'); // No error thrown

// Using assert.throws() to test for exceptions
function throwError() {
  throw new Error('This is an error!');
}

assert.throws(throwError, Error, 'Expected error was not thrown!'); // No error thrown
```

## `timers`
The `timers` module in Node.js is a built-in module that provides functions for scheduling the execution of code after a specified delay or at regular intervals. It allows developers to create timers, set timeouts, and schedule recurring tasks in their applications. The `timers` module is useful for implementing delayed actions, periodic updates, and time-based events.

### Example of using the `timers` module in Node.js:
```javascript
const timers = require('timers');

// Scheduling a function to run after a delay using setTimeout
timers.setTimeout(() => {
  console.log('This message is displayed after a 2-second delay.');
}, 2000);

// Scheduling a function to run at regular intervals using setInterval
const intervalId = timers.setInterval(() => {
  console.log('This message is displayed every 1 second.');
}, 1000);

// Clearing the interval after 5 seconds
timers.setTimeout(() => {
  timers.clearInterval(intervalId);
  console.log('Interval cleared after 5 seconds.');
}, 5000);
```

## `tty`
The `tty` module in Node.js is a built-in module that provides an interface for working with terminal devices (TTYs). It allows developers to interact with the terminal, control input and output behavior, and manage terminal settings. The `tty` module is useful for building command-line applications, handling user input, and customizing terminal behavior.

### Example of using the `tty` module in Node.js:
```javascript
const tty = require('tty');

// Checking if the current process is running in a TTY
if (tty.isatty(process.stdout.fd)) {
  console.log('The current process is running in a TTY.');
} else {
  console.log('The current process is not running in a TTY.');
}

// Creating a TTY ReadStream for reading input from the terminal
const input = new tty.ReadStream(process.stdin.fd);

// Listening for data events from the TTY ReadStream
input.on('data', (chunk) => {
  console.log(`Received input: ${chunk.toString()}`);
});

// Closing the TTY ReadStream after 5 seconds
setTimeout(() => {
  input.close();
  console.log('TTY ReadStream closed.');
}, 5000);
```

## `console`
The `console` module in Node.js is a built-in module that provides a simple debugging console for logging information, warnings, and errors to the standard output (stdout) and standard error (stderr) streams. It allows developers to print messages, inspect objects, and track the flow of their applications during development and debugging. The `console` module includes various methods for logging, such as `console.log()`, `console.error()`, `console.warn()`, and more.

### Example of using the `console` module in Node.js:
```javascript
const console = require('console');

// Logging a message to the standard output
console.log('Hello, Node.js console module!');

// Logging an error message to the standard error
console.error('This is an error message.');

// Logging a warning message
console.warn('This is a warning message.');

// Inspecting an object using console.dir()
const obj = { name: 'Alice', age: 30, city: 'New York' };
console.dir(obj, { depth: null, colors: true });

// Using console.time() and console.timeEnd() to measure execution time
console.time('Execution Time');

// Simulating a time-consuming operation
setTimeout(() => {
  console.timeEnd('Execution Time'); // Output: Execution Time: <time>ms
}, 2000);
```

## `string_decoder`
The `string_decoder` module in Node.js is a built-in module that provides an API for decoding buffer data into strings while preserving multi-byte character boundaries. It allows developers to handle string data that may be split across multiple buffer chunks, ensuring that characters are decoded correctly without breaking multi-byte sequences. The `string_decoder` module is particularly useful when working with streams and handling text data.

### Example of using the `string_decoder` module in Node.js:
```javascript
const { StringDecoder } = require('string_decoder');
// Creating a StringDecoder instance for UTF-8 encoding
const decoder = new StringDecoder('utf8');

// Decoding buffer data into strings
const buffer1 = Buffer.from([0xE2, 0x9C]); // Incomplete multi-byte character
const buffer2 = Buffer.from([0x94, 0xA2]); // Remaining bytes of the multi-byte character

const decodedString1 = decoder.write(buffer1);
const decodedString2 = decoder.write(buffer2);

console.log('Decoded String 1:', decodedString1); // Output: Decoded String 1:
console.log('Decoded String 2:', decodedString2); // Output: Decoded String 2: ✔️
```

## `perf-hooks`
The `perf_hooks` module in Node.js is a built-in module that provides an API for measuring the performance of code execution. It allows developers to collect high-resolution timing information, monitor performance metrics, and analyze the execution time of specific code blocks or functions. The `perf_hooks` module is useful for profiling applications, identifying performance bottlenecks, and optimizing code.

### Example of using the `perf_hooks` module in Node.js:
```javascript
const { performance, PerformanceObserver } = require('perf_hooks');

// Creating a PerformanceObserver to monitor performance entries
const obs = new PerformanceObserver((list) => {
  const entries = list.getEntries();
  entries.forEach((entry) => {
    console.log(`${entry.name}: ${entry.duration}ms`);
  });
});

obs.observe({ entryTypes: ['measure'] });

// Measuring the execution time of a code block
performance.mark('start');

// Simulating a time-consuming operation
setTimeout(() => {
  performance.mark('end');
  performance.measure('Time taken for operation', 'start', 'end');
}, 2000);
```

## `async_hooks`
The `async_hooks` module in Node.js is a built-in module that provides an API for tracking asynchronous resources and their lifecycle events. It allows developers to monitor the creation, execution, and destruction of asynchronous operations, such as timers, promises, and I/O operations. The `async_hooks` module is useful for debugging, profiling, and understanding the behavior of asynchronous code in Node.js applications.

### Example of using the `async_hooks` module in Node.js:
```javascript
const async_hooks = require('async_hooks');

// Creating an AsyncHook instance to track asynchronous resources
const asyncHook = async_hooks.createHook({
  init(asyncId, type, triggerAsyncId, resource) {
    console.log(`Async resource initialized: ${type} (ID: ${asyncId})`);
  },
  before(asyncId) {
    console.log(`Before async resource execution (ID: ${asyncId})`);
  },
  after(asyncId) {
    console.log(`After async resource execution (ID: ${asyncId})`);
  },
  destroy(asyncId) {
    console.log(`Async resource destroyed (ID: ${asyncId})`);
  }
});

// Enabling the AsyncHook
asyncHook.enable();

// Simulating an asynchronous operation using setTimeout
setTimeout(() => {
  console.log('Asynchronous operation completed.');
}, 1000);
```

## `diagnostics_channel`
The `diagnostics_channel` module in Node.js is a built-in module that provides an API for creating and subscribing to diagnostic channels. It allows developers to instrument their applications and collect diagnostic information, such as performance metrics, error events, and custom telemetry data. The `diagnostics_channel` module is useful for monitoring application behavior, debugging issues, and gaining insights into the runtime performance of Node.js applications.

### Example of using the `diagnostics_channel` module in Node.js:
```javascript
const diagnostics_channel = require('diagnostics_channel');

// Creating a diagnostic channel
const channel = diagnostics_channel.channel('my-channel');

// Subscribing to the diagnostic channel
channel.subscribe((message) => {
  console.log('Received diagnostic message:', message);
});

// Publishing a message to the diagnostic channel
channel.publish({ event: 'test-event', data: 'This is a test message.' });
```

