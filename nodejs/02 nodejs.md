# Buffers

## What is a Buffer?
A Buffer is a temporary storage area for data that is being transferred from one place to another. In Node.js, Buffers are used to handle binary data directly, allowing you to work with raw memory allocations. They are particularly useful when dealing with streams of data, such as reading files or receiving data over a network.

## Why Buffers exist?
Buffers exist in Node.js to provide a way to handle binary data efficiently. JavaScript, the language that Node.js is built on, primarily works with strings and objects, which are not suitable for handling raw binary data. Buffers allow developers to manipulate binary data directly, making it possible to work with files, network protocols, and other low-level data operations.

## Binary data
Binary data refers to data that is represented in a binary format, which consists of sequences of 0s and 1s. This type of data is often used for representing images, audio files, video files, and other types of media. In Node.js, Buffers provide a way to work with binary data efficiently, allowing developers to read, write, and manipulate binary data without the overhead of converting it to strings or other formats.

## Buffer.from()
The `Buffer.from()` method is used to create a new Buffer instance from an existing array, string, or another Buffer. This method is particularly useful when you need to convert data into a Buffer for further processing.

```javascript
const bufferFromString = Buffer.from('Hello, World!');
const bufferFromArray = Buffer.from([1, 2, 3, 4, 5]);
console.log(bufferFromString); // Output: <Buffer 48 65 6c 6c 6f 2c 20 57 6f 72 6c 64 21>
console.log(bufferFromArray); // Output: <Buffer 01 02 03 04 05>
```

## Buffer.alloc()
The `Buffer.alloc()` method is used to create a new Buffer instance of a specified size, filled with zeros. This method is useful when you need to allocate a buffer of a specific size for storing binary data.

```javascript
const bufferAlloc = Buffer.alloc(10);
console.log(bufferAlloc); // Output: <Buffer 00 00 00 00 00 00 00 00 00 00>
```

## Buffer.allocUnsafe()
The `Buffer.allocUnsafe()` method is used to create a new Buffer instance of a specified size without initializing the memory. This method is faster than `Buffer.alloc()`, but it may contain old data, so it should be used with caution.

```javascript
const bufferAllocUnsafe = Buffer.allocUnsafe(10);
console.log(bufferAllocUnsafe); // Output: <Buffer ...> (may contain old data)
```

## Buffer length
The `length` property of a Buffer instance returns the size of the buffer in bytes. This property is useful for determining how much data is stored in the buffer.

```javascript
const buffer = Buffer.from('Hello, World!');
console.log(buffer.length); // Output: 13
```

## Reading Buffer data
To read data from a Buffer, you can use various methods provided by the Buffer class. For example, you can use the `toString()` method to convert the buffer data into a string format.

```javascript
const buffer = Buffer.from('Hello, World!');
console.log(buffer.toString()); // Output: Hello, World!
```

## Writing Buffer data
To write data to a Buffer, you can use the `write()` method. This method allows you to write a string or binary data into the buffer at a specified offset.

```javascript
const buffer = Buffer.alloc(20);
buffer.write('Hello, World!', 0);
console.log(buffer.toString()); // Output: Hello, World!
```

## Encoding
Buffers can be created with different encodings, such as 'utf8', 'ascii', 'base64', and 'hex'. The encoding determines how the binary data is interpreted when converting to and from strings.

```javascript
const bufferUtf8 = Buffer.from('Hello, World!', 'utf8');
const bufferBase64 = Buffer.from('Hello, World!', 'base64');
console.log(bufferUtf8.toString('utf8')); // Output: Hello, World!
console.log(bufferBase64.toString('base64')); // Output: SGVsbG8sIFdvcmxkIQ==
```

## UTF-8
UTF-8 is a variable-width character encoding used for electronic communication. It can represent every character in the Unicode character set and is backward compatible with ASCII. In Node.js, Buffers can be used to handle UTF-8 encoded data efficiently.

```javascript
const bufferUtf8 = Buffer.from('Hello, World!', 'utf8');
console.log(bufferUtf8.toString('utf8')); // Output: Hello, World!
```

## Base64
Base64 is a binary-to-text encoding scheme that represents binary data in an ASCII string format. It is commonly used for encoding data that needs to be stored and transferred over media that are designed to deal with textual data. In Node.js, you can create a Buffer from a Base64 encoded string and convert it back to its original form.

```javascript
const bufferBase64 = Buffer.from('SGVsbG8sIFdvcmxkIQ==', 'base64');
console.log(bufferBase64.toString('utf8')); // Output: Hello, World!
```

## Hex
Hexadecimal (hex) is a base-16 number system that uses 16 symbols (0-9 and A-F) to represent values. In Node.js, Buffers can be created from hex strings and converted back to their original binary form.

```javascript
const bufferHex = Buffer.from('48656c6c6f2c20576f726c6421', 'hex');
console.log(bufferHex.toString('utf8')); // Output: Hello, World!
```

## Buffer conversion
Buffers can be converted to different formats using the `toString()` method with the desired encoding.

```javascript
const buffer = Buffer.from('Hello, World!');
console.log(buffer.toString('utf8')); // Output: Hello, World!
console.log(buffer.toString('base64')); // Output: SGVsbG8sIFdvcmxkIQ==
console.log(buffer.toString('hex')); // Output: 48656c6c6f2c20576f726c6421
```

## Buffer comparison
Buffers can be compared using the `compare()` method, which returns a number indicating whether the first buffer is less than, equal to, or greater than the second buffer.

```javascript
const buffer1 = Buffer.from('Hello');
const buffer2 = Buffer.from('World');
const comparison = Buffer.compare(buffer1, buffer2);
if (comparison < 0) {
    console.log('buffer1 is less than buffer2');
} else if (comparison > 0) {
    console.log('buffer1 is greater than buffer2');
} else {
    console.log('buffer1 is equal to buffer2');
}
```

## Buffer concatenation
Buffers can be concatenated using the `Buffer.concat()` method, which combines multiple Buffer instances into a single Buffer.

```javascript
const buffer1 = Buffer.from('Hello, ');
const buffer2 = Buffer.from('World!');
const concatenatedBuffer = Buffer.concat([buffer1, buffer2]);
console.log(concatenatedBuffer.toString()); // Output: Hello, World!
```

# Events & EventEmitter

## Event-driven architecture
Node.js is built on an event-driven architecture, which means that it uses events to handle asynchronous operations. In this architecture, an event is emitted when a specific action occurs, and event listeners are used to respond to those events. This allows Node.js to handle multiple operations concurrently without blocking the execution of code.

