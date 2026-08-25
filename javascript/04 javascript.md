# Regular Expressions

## What are regex?
Regular expressions (regex) are patterns used to match character combinations in strings. In JavaScript, regex are also objects. These patterns are used with the exec() and test() methods of RegExp, and with the match(), matchAll(), replace(), replaceAll(), search(), and split() methods of String.

## Regex Syntax
A regular expression can be defined in two ways:
1. Using a regex literal, which consists of a pattern enclosed between slashes:
```javascript
const regex = /ab+c/;
```
2. Calling the constructor function of the RegExp object:
```javascript
const regex = new RegExp('ab+c');
```
3. The pattern can include special characters that have specific meanings, such as:
- `.`: Matches any single character except newline characters.
- `^`: Matches the beginning of a string.
- `$`: Matches the end of a string.
- `*`: Matches the preceding character zero or more times.
- `+`: Matches the preceding character one or more times.
- `?`: Matches the preceding character zero or one time.
- `[]`: Matches any one of the characters inside the brackets.
- `|`: Acts as a logical OR between expressions.
- `()` : Groups expressions together and captures the matched text.
- `\`: Escapes special characters or denotes special sequences.
- `{}`: Specifies a quantifier for the preceding character or group.
- `\d`: Matches any digit (equivalent to [0-9]).
- `\D`: Matches any non-digit character (equivalent to [^0-9]).
- `\w`: Matches any word character (alphanumeric or underscore).
- `\W`: Matches any non-word character (equivalent to [^a-zA-Z0-9_]).
- `\s`: Matches any whitespace character (spaces, tabs, line breaks).
- `\S`: Matches any non-whitespace character.
- `\b`: Matches a word boundary.
- `\B`: Matches a non-word boundary.
- `(?=...)`: Positive lookahead assertion.
- `(?!...)`: Negative lookahead assertion.
- `(?<=...)`: Positive lookbehind assertion.
- `(?<!...)`: Negative lookbehind assertion.
- `g`: Global search (find all matches rather than stopping after the first match).
- `i`: Case-insensitive search.
- `m`: Multi-line search (changes the behavior of `^` and `$` to match the start and end of each line).
- `s`: Allows the dot `.` to match newline characters.
- `u`: Enables full Unicode support.
- `y`: Sticky search (matches only from the last index position).
- `d`: Generates indices for substring matches.
- `v`: Enables Unicode property escapes.

## Examples
```javascript
// Example 1: Using regex literal
const regex1 = /hello/;

// Example 2: Using RegExp constructor
const regex2 = new RegExp('hello');

// Example 3: Using special characters
const regex3 = /h.llo/; // Matches "hello", "hallo", "hxllo", etc.

// Example 4: Using quantifiers
const regex4 = /ab*c/; // Matches "ac", "abc", "abbc", etc.

// Example 5: Using character classes
const regex5 = /[aeiou]/; // Matches any vowel

// Example 6: Using logical OR
const regex6 = /cat|dog/; // Matches "cat" or "dog"

// Example 7: Using groups
const regex7 = /(abc)+/; // Matches "abc", "abcabc", "abcabcabc", etc.
```

## Character Classes
Character classes allow you to define a set of characters to match. They are defined using square brackets `[]`. For example, `[abc]` matches any one of the characters 'a', 'b', or 'c'. You can also use ranges, such as `[a-z]` to match any lowercase letter.

### Example of Character Classes
```javascript
const regex = /[aeiou]/; // Matches any vowel
const regex2 = /[0-9]/; // Matches any digit
const regex3 = /[a-zA-Z]/; // Matches any letter
```

## Quantifiers
Quantifiers specify how many instances of a character, group, or character class must be present in the input for a match to be found. The most common quantifiers are:
- `*`: Matches 0 or more occurrences of the preceding element.
- `+`: Matches 1 or more occurrences of the preceding element.
- `?`: Matches 0 or 1 occurrence of the preceding element.
- `{n}`: Matches exactly n occurrences of the preceding element.
- `{n,}`: Matches n or more occurrences of the preceding element.
- `{n,m}`: Matches between n and m occurrences of the preceding element.
- `*?`, `+?`, `??`, `{n,m}?`: These are lazy quantifiers that match as few occurrences as possible.

### Example of Quantifiers
```javascript
const regex1 = /a*/; // Matches 0 or more 'a's
const regex2 = /a+/; // Matches 1 or more 'a's
const regex3 = /a?/; // Matches 0 or 1 'a'
const regex4 = /a{3}/; // Matches exactly 3 'a's
const regex5 = /a{2,}/; // Matches 2 or more 'a's
const regex6 = /a{2,4}/; // Matches between 2 and 4 'a's
```

## Groups
Groups allow you to combine multiple tokens together and treat them as a single unit. Groups are created using parentheses `()`. You can also use non-capturing groups with `(?:...)` if you don't want to capture the matched text.

### Example of Groups
```javascript
const regex1 = /(abc)+/; // Matches "abc", "abcabc", "abcabcabc", etc.
const regex2 = /(?:abc)+/; // Matches "abc", "abcabc", but does not capture the matched text
```

## Capturing Groups
Capturing groups allow you to extract specific parts of the matched string. You can access the captured groups using the `match()` method or the `exec()` method.

### Example of Capturing Groups
```javascript
const regex = /(hello) (world)/;
const str = "hello world";
const result = str.match(regex);
console.log(result[0]); // "hello world"
console.log(result[1]); // "hello"
console.log(result[2]); // "world"
```

## Non-Capturing Groups
Non-capturing groups allow you to group parts of a regex without capturing the matched text.

### Example of Non-Capturing Groups
```javascript
const regex = /(?:hello) (world)/;
const str = "hello world";
const result = str.match(regex);
console.log(result[0]); // "hello world"
console.log(result[1]); // "world"
```

## Alternation
Alternation allows you to match one of several patterns. It is represented by the pipe `|` character.

### Example of Alternation
```javascript
const regex = /cat|dog/;
const str1 = "I have a cat.";
const str2 = "I have a dog.";
console.log(regex.test(str1)); // true
console.log(regex.test(str2)); // true
```

## Anchors
Anchors are special characters that match a position in the string rather than a character. The most common anchors are:
- `^`: Matches the beginning of a string.
- `$`: Matches the end of a string.

### Example of Anchors
```javascript
const regex1 = /^hello/; // Matches "hello" at the start of a string
const regex2 = /world$/; // Matches "world" at the end of a string
```

## Flags
Flags are optional parameters that can be added to a regex to modify its behavior. The most common flags are:
- `g`: Global search (find all matches rather than stopping after the first match).
- `i`: Case-insensitive search.
- `m`: Multi-line search (changes the behavior of `^` and `$` to match the start and end of each line).

### Example of Flags
```javascript
const regex1 = /hello/g; // Global search
const regex2 = /hello/i; // Case-insensitive search
const regex3 = /hello/m; // Multi-line search
```

## g,i,m,s,u,y,d,v Flags
- `g`: Global search (find all matches rather than stopping after the first match).
- `i`: Case-insensitive search.
- `m`: Multi-line search (changes the behavior of `^` and `$` to match the start and end of each line).
- `s`: Allows the dot `.` to match newline characters.
- `u`: Enables full Unicode support.
- `y`: Sticky search (matches only from the last index position).
- `d`: Generates indices for substring matches.
- `v`: Enables Unicode property escapes.

### Example of g,i,m,s,u,y,d,v Flags
```javascript
const regex1 = /hello/g; // Global search
const regex2 = /hello/i; // Case-insensitive search
const regex3 = /hello/m; // Multi-line search
const regex4 = /hello/s; // Dot matches newline characters
const regex5 = /hello/u; // Full Unicode support
const regex6 = /hello/y; // Sticky search
const regex7 = /hello/d; // Generates indices for substring matches
const regex8 = /hello/v; // Enables Unicode property escapes
```

## test(), match(), matchAll(), replace(), replaceAll(), search(), and split() Methods
These methods are used to work with regex in JavaScript.

### test()
The `test()` method executes a search for a match between a regex and a specified string.
```javascript
const regex = /hello/;
const str = "hello world";
console.log(regex.test(str)); // true
```

### match()
The `match()` method retrieves the matches when matching a string against a regex.
```javascript
const regex = /hello/;
const str = "hello world";
console.log(str.match(regex)); // ["hello"]
```

### matchAll()
The `matchAll()` method returns an iterator of all results matching a string against a regex, including capturing groups.
```javascript
const regex = /hello/g;
const str = "hello world, hello universe";
console.log([...str.matchAll(regex)]); // [["hello"], ["hello"]]
```

### replace()
The `replace()` method returns a new string with some or all matches of a regex replaced by a replacement.
```javascript
const regex = /hello/;
const str = "hello world";
console.log(str.replace(regex, "hi")); // "hi world"
```

### replaceAll()
The `replaceAll()` method returns a new string with all matches of a regex replaced by a replacement.
```javascript
const regex = /hello/g;
const str = "hello world, hello universe";
console.log(str.replaceAll(regex, "hi")); // "hi world, hi universe"
```

### search()
The `search()` method executes a search for a match between a regex and a specified string, returning the index of the match, or -1 if the search fails.
```javascript
const regex = /hello/;
const str = "hello world";
console.log(str.search(regex)); // 0
```

### split()
The `split()` method divides a string into an array of substrings using a regex as the delimiter.
```javascript
const regex = /,\s*/;
const str = "apple, banana, cherry";
console.log(str.split(regex)); // ["apple", "banana", "cherry"]
```

# Dates & Time

## Date Object
The Date object is a built-in object in JavaScript that allows you to work with dates and times. It provides methods for creating, manipulating, and formatting dates.

### Example of Creating a Date Object
```javascript
const date1 = new Date(); // Current date and time
const date2 = new Date('2024-06-01'); // Specific date
const date3 = new Date(2024, 5, 1); // Year, Month (0-indexed), Day
```

## Creating Dates
Creating dates can be done using the Date constructor in several ways:
1. **Current Date and Time**:
```javascript
const currentDate = new Date();
```
2. **Specific Date**:
```javascript
const specificDate = new Date('2024-06-01T12:00:00');
```
3. **Using Year, Month, Day**:
```javascript
const date = new Date(2024, 5, 1); // June 1, 2024 (Month is 0-indexed)
```

## Getting Date Values
You can retrieve various components of a date using the following methods:
- `getFullYear()`: Returns the year (4 digits).
- `getMonth()`: Returns the month (0-11).
- `getDate()`: Returns the day of the month (1-31).
- `getDay()`: Returns the day of the week (0-6, where 0 is Sunday).
- `getHours()`: Returns the hour (0-23).
- `getMinutes()`: Returns the minutes (0-59).
- `getSeconds()`: Returns the seconds (0-59).

### Example of Getting Date Values
```javascript
const date = new Date('2024-06-01T12:00:00');
console.log(date.getFullYear()); // 2024
console.log(date.getMonth()); // 5 (June)
console.log(date.getDate()); // 1
console.log(date.getDay()); // 6 (Saturday)
console.log(date.getHours()); // 12
console.log(date.getMinutes()); // 0
console.log(date.getSeconds()); // 0
```

## Setting Date Values
You can modify the components of a date using the following methods:
- `setFullYear(year)`: Sets the year (4 digits).
- `setMonth(month)`: Sets the month (0-11).
- `setDate(day)`: Sets the day of the month (1-31).
- `setHours(hour)`: Sets the hour (0-23).
- `setMinutes(minutes)`: Sets the minutes (0-59).
- `setSeconds(seconds)`: Sets the seconds (0-59).

### Example of Setting Date Values
```javascript
const date = new Date();
date.setFullYear(2025);
date.setMonth(11); // December
date.setDate(25);
date.setHours(10);
date.setMinutes(30);
date.setSeconds(45);
console.log(date); // Outputs the modified date
```

## Formatting Dates
You can format dates in JavaScript using various methods. The most common methods are:
- `toDateString()`: Returns the date portion of a Date object as a human-readable string.
- `toTimeString()`: Returns the time portion of a Date object as a human-readable string.
- `toISOString()`: Returns the date as a string in ISO format.

### Example of Formatting Dates
```javascript
const date = new Date('2024-06-01T12:00:00');
console.log(date.toDateString()); // "Sat Jun 01 2024"
console.log(date.toTimeString()); // "12:00:00 GMT+0000 (Coordinated Universal Time)"
console.log(date.toISOString()); // "2024-06-01T12:00:00.000Z"
```

## Timestamps
A timestamp is a numeric representation of a specific point in time, usually expressed as the number of milliseconds since January 1, 1970 (the Unix epoch). In JavaScript, you can get the current timestamp using the `Date.now()` method or by creating a new Date object and calling the `getTime()` method.

### Example of Timestamps
```javascript
const timestamp1 = Date.now(); // Current timestamp in milliseconds
const date = new Date();
const timestamp2 = date.getTime(); // Timestamp from a Date object
console.log(timestamp1); // e.g., 1712345678901
console.log(timestamp2); // e.g., 1712345678901
```

## UTC 
The `Date` object in JavaScript also provides methods to work with Coordinated Universal Time (UTC). You can use these methods to get or set date and time values in UTC.

### Example of UTC Methods
```javascript
const date = new Date('2024-06-01T12:00:00Z'); // UTC time
console.log(date.getUTCFullYear()); // 2024
console.log(date.getUTCMonth()); // 5 (June)
console.log(date.getUTCDate()); // 1
console.log(date.getUTCHours()); // 12
console.log(date.getUTCMinutes()); // 0
console.log(date.getUTCSeconds()); // 0
```

## Time Zones
JavaScript's `Date` object automatically handles time zones based on the user's local system settings.

### Example of Time Zones
```javascript
const date = new Date('2024-06-01T12:00:00Z'); // UTC time
console.log(date.toString()); // Outputs the date in local time zone
console.log(date.toLocaleString('en-US', { timeZone: 'America/New_York' })); // Outputs the date in New York time zone
console.log(date.toLocaleString('en-US', { timeZone: 'Asia/Tokyo' })); // Outputs the date in Tokyo time zone
```

## Date Calculations
You can perform date calculations in JavaScript by manipulating the timestamp values. For example, you can add or subtract days, months, or years by adjusting the timestamp.

### Example of Date Calculations
```javascript
const date = new Date('2024-06-01T12:00:00');
// Add 7 days
const newDate = new Date(date.getTime() + 7 * 24 * 60 * 60 * 1000);
console.log(newDate); // Outputs the date 7 days later
// Subtract 1 month
const previousMonth = new Date(date.getTime() - 30 * 24 * 60 * 60 * 1000);
console.log(previousMonth); // Outputs the date 1 month earlier
```

## Intl.DateTimeFormat
The `Intl.DateTimeFormat` object enables language-sensitive date and time formatting. You can use it to format dates according to different locales and options.

### Example of Intl.DateTimeFormat
```javascript
const date = new Date('2024-06-01T12:00:00');
const formatter = new Intl.DateTimeFormat('en-US', {
  year: 'numeric',
  month: 'long',
  day: 'numeric',
  hour: '2-digit',
  minute: '2-digit',
  second: '2-digit',
  timeZoneName: 'short'
});

console.log(formatter.format(date)); // Outputs: "June 1, 2024, 12:00:00 PM GMT+0"
```

## Temporal API Concepts
The Temporal API is a new date and time API in JavaScript that provides a more robust and flexible way to work with dates, times, and time zones. It is designed to address the limitations of the existing `Date` object and provide better support for modern applications.

### Example of Temporal API
```javascript
const { PlainDate, PlainTime, PlainDateTime, Duration, ZonedDateTime } = Temporal;

// Create a PlainDate
const date = PlainDate.from('2024-06-01');

// Create a PlainTime
const time = PlainTime.from('12:00:00');

// Create a PlainDateTime
const dateTime = PlainDateTime.from('2024-06-01T12:00:00');

// Create a Duration
const duration = Duration.from({ days: 7, hours: 5 });

// Create a ZonedDateTime
const zonedDateTime = ZonedDateTime.from('2024-06-01T12:00:00+00:00[UTC]');
console.log(date.toString()); // "2024-06-01"
```

# Internationalization (i18n)
Internationalization (i18n) is the process of designing and developing applications that can be adapted to different languages and regions without requiring engineering changes. JavaScript provides built-in support for internationalization through the `Intl` object, which includes constructors for formatting dates, times, numbers, and currencies according to different locales.

## Intl
The `Intl` object is the namespace for the ECMAScript Internationalization API, which provides language-sensitive string comparison, number formatting, and date and time formatting.

### Example of Intl
```javascript
const number = 1234567.89;
// Format number for US locale
const usFormatter = new Intl.NumberFormat('en-US');
console.log(usFormatter.format(number)); // "1,234,567.89"
// Format number for German locale
const deFormatter = new Intl.NumberFormat('de-DE');
console.log(deFormatter.format(number)); // "1.234.567,89"
```

## Intl.NumberFormat
The `Intl.NumberFormat` object enables language-sensitive number formatting. You can use it to format numbers according to different locales and options, such as currency, percentage, and decimal formatting.

### Example of Intl.NumberFormat
```javascript
const number = 1234567.89;
// Format number for US locale
const usFormatter = new Intl.NumberFormat('en-US', { style: 'currency', currency: 'USD' });
console.log(usFormatter.format(number)); // "$1,234,567.89"

// Format number for German locale
const deFormatter = new Intl.NumberFormat('de-DE', { style: 'currency', currency: 'EUR' });
console.log(deFormatter.format(number)); // "1.234.567,89 €"

// Format number Indian locale
const inFormatter = new Intl.NumberFormat('en-IN', { style: 'currency', currency: 'INR' });
console.log(inFormatter.format(number)); // "₹12,34,567.89"
```

## Intl.DateTimeFormat
The `Intl.DateTimeFormat` object enables language-sensitive date and time formatting. You can use it to format dates according to different locales and options, such as date style, time style, and time zone.

### Example of Intl.DateTimeFormat
```javascript
const date = new Date('2024-06-01T12:00:00');
// Format date for US locale

const usFormatter = new Intl.DateTimeFormat('en-US', {
  year: 'numeric',
  month: 'long',
  day: 'numeric',
  hour: '2-digit',
  minute: '2-digit',
  second: '2-digit',
  timeZoneName: 'short'
});

console.log(usFormatter.format(date)); // "June 1, 2024, 12:00:00 PM GMT+0"
```

## Intl.Collator
The `Intl.Collator` object enables language-sensitive string comparison. You can use it to compare strings according to different locales and options, such as sensitivity, case, and numeric sorting.

### Example of Intl.Collator
```javascript
const collator = new Intl.Collator('en-US', { sensitivity: 'base' });
const strings = ['apple', 'Banana', 'cherry', 'date'];

const sortedStrings = strings.sort(collator.compare);
console.log(sortedStrings); // ["apple", "Banana", "cherry", "date"]
```

## Intl.RelativeTimeFormat
The `Intl.RelativeTimeFormat` object enables language-sensitive relative time formatting. You can use it to format relative time values according to different locales and options, such as numeric and style.

### Example of Intl.RelativeTimeFormat
```javascript
const rtf = new Intl.RelativeTimeFormat('en-US', { numeric: 'auto' });
console.log(rtf.format(-1, 'day')); // "yesterday"
console.log(rtf.format(1, 'day')); // "tomorrow"
console.log(rtf.format(-2, 'hour')); // "2 hours ago"
console.log(rtf.format(3, 'minute')); // "in 3 minutes"
```

## Locale handling
JavaScript provides built-in support for handling different locales through the `Intl` object. You can specify the desired locale when creating instances of `Intl.NumberFormat`, `Intl.DateTimeFormat`, `Intl.Collator`, and `Intl.RelativeTimeFormat`. The locale determines how numbers, dates, times, and strings are formatted and compared.

### Example of Locale Handling
```javascript
const number = 1234567.89;
// Format number for US locale

const usFormatter = new Intl.NumberFormat('en-US');
console.log(usFormatter.format(number)); // "1,234,567.89"

// Format number for German locale
const deFormatter = new Intl.NumberFormat('de-DE');
console.log(deFormatter.format(number)); // "1.234.567,89"
 
// Format number for Indian locale
const inFormatter = new Intl.NumberFormat('en-IN');
console.log(inFormatter.format(number)); // "12,34,567.89"
```

## Currency formatting
The `Intl.NumberFormat` object can also be used to format numbers as currency values. You can specify the currency code and style when creating an instance of `Intl.NumberFormat`.

### Example of Currency Formatting
```javascript
const number = 1234567.89;
// Format number as USD currency
const usdFormatter = new Intl.NumberFormat('en-US', { style: 'currency', currency: 'USD' });
console.log(usdFormatter.format(number)); // "$1,234,567.89"

// Format number as EUR currency
const eurFormatter = new Intl.NumberFormat('de-DE', { style: 'currency', currency: 'EUR' });
console.log(eurFormatter.format(number)); // "1.234.567,89 €"

// Format number as INR currency
const inrFormatter = new Intl.NumberFormat('en-IN', { style: 'currency', currency: 'INR' });
console.log(inrFormatter.format(number)); // "₹12,34,567.89"
```

## Number formatting
The `Intl.NumberFormat` object enables language-sensitive number formatting. You can use it to format numbers according to different locales and options, such as decimal places, grouping separators, and significant digits.

### Example of Number Formatting
```javascript
const number = 1234567.89;
// Format number for US locale with 2 decimal places
const usFormatter = new Intl.NumberFormat('en-US', { minimumFractionDigits: 2, maximumFractionDigits: 2 });
console.log(usFormatter.format(number)); // "1,234,567.89"

// Format number for German locale with 2 decimal places
const deFormatter = new Intl.NumberFormat('de-DE', { minimumFractionDigits: 2, maximumFractionDigits: 2 });
console.log(deFormatter.format(number)); // "1.234.567,89"

// Format number for Indian locale with 2 decimal places
const inFormatter = new Intl.NumberFormat('en-IN', { minimumFractionDigits: 2, maximumFractionDigits: 2 });
console.log(inFormatter.format(number)); // "12,34,567.89"
```

# Memory & Performance

# Stack vs Heap
In JavaScript, memory is managed in two main areas: the stack and the heap. Understanding the differences between these two memory areas is crucial for optimizing performance and managing memory effectively.

- **Stack**: The stack is a region of memory that stores primitive values (such as numbers, strings, and booleans) and function call information. It operates in a last-in, first-out (LIFO) manner, meaning that the last item added to the stack is the first one to be removed. The stack is typically used for short-lived data and has a limited size.

- **Heap**: The heap is a region of memory that stores objects and reference types (such as arrays and functions). Unlike the stack, the heap does not have a strict order for adding and removing items. It is used for long-lived data and has a larger size compared to the stack. Memory in the heap is managed by the garbage collector, which automatically frees up memory that is no longer in use.

## Garbage Collection
Garbage collection is the process of automatically identifying and reclaiming memory that is no longer in use by the program. In JavaScript, the garbage collector runs periodically to free up memory occupied by objects that are no longer reachable or referenced in the code. This helps prevent memory leaks and ensures efficient memory usage.

### Example of Garbage Collection
```javascript
function createObject() {
  const obj = { name: 'John', age: 30 };
  return obj;
}

const myObject = createObject(); // The object is created and referenced by myObject
// When myObject is no longer needed, it can be set to null
myObject = null; // The object is now eligible for garbage collection
```

## Memory Leaks
A memory leak occurs when a program retains references to objects that are no longer needed, preventing the garbage collector from reclaiming that memory. Memory leaks can lead to increased memory usage and degraded performance over time.

### Common Causes of Memory Leaks
1. **Global Variables**: Declaring variables in the global scope can lead to memory leaks if they are not properly managed.
2. **Closures**: Closures can retain references to variables in their outer scope, leading to memory leaks if not handled carefully.
3. **Event Listeners**: Failing to remove event listeners when they are no longer needed can cause memory leaks, as the listener retains a reference to the DOM element.
4. **Timers**: Using `setInterval` or `setTimeout` without clearing them can lead to memory leaks if the callbacks retain references to objects.

### Example of Memory Leak
```javascript
let myArray = [];
function addToArray() {
  const obj = { name: 'John' };
  myArray.push(obj); // The object is added to the array and retained in memory
}

let intervalId = setInterval(addToArray, 1000); // The function is called every second
// If we don't clear the interval, the array will keep growing and cause a memory leak

clearInterval(intervalId); // Clear the interval when it's no longer needed
```

## Detached DOM Nodes
A detached DOM node is a node that has been removed from the document but still exists in memory because there are references to it in JavaScript. Detached nodes can lead to memory leaks if they are not properly managed, as they prevent the garbage collector from reclaiming the memory used by those nodes.

### Example of Detached DOM Nodes
```javascript
const button = document.createElement('button');
button.textContent = 'Click me';
document.body.appendChild(button);

button.addEventListener('click', () => {
  console.log('Button clicked');
});

// Later, if we remove the button from the DOM but still have a reference to it
document.body.removeChild(button); // The button is removed from the DOM
// However, the reference to the button still exists in memory
// To avoid memory leaks, we should remove the event listener and clear the reference
button.removeEventListener('click', () => {
  console.log('Button clicked');
});
button = null; // Clear the reference to the button
```

## Unnecessary event listeners
Unnecessary event listeners can lead to memory leaks if they are not removed when they are no longer needed. Event listeners retain references to the elements they are attached to, preventing those elements from being garbage collected.

### Example of Unnecessary Event Listeners
```javascript
const button = document.createElement('button');
button.textContent = 'Click me';
document.body.appendChild(button);

button.addEventListener('click', () => {
  console.log('Button clicked');
});

// Later, if we remove the button from the DOM but don't remove the event listener
document.body.removeChild(button); // The button is removed from the DOM

// The event listener still exists and retains a reference to the button
// To avoid memory leaks, we should remove the event listener before removing the button
button.removeEventListener('click', () => {
  console.log('Button clicked');
});
```

## Closures and memory
Closures can lead to memory leaks if they retain references to variables in their outer scope that are no longer needed. When a closure is created, it captures the variables from its outer scope, which can prevent those variables from being garbage collected.

### Example of Closures and Memory
```javascript
function createCounter() {
  let count = 0; // This variable is captured by the closure
  return function() {
    count++;
    console.log(count);
  };
}

const counter = createCounter(); // The closure retains a reference to 'count'
counter(); // 1
counter(); // 2
// If we no longer need the counter, we can set it to null to allow garbage collection
counter = null; // The closure and 'count' can now be garbage collected
```

## Performance profiling
Performance profiling is the process of analyzing the performance of a JavaScript application to identify bottlenecks and optimize its execution. Modern browsers provide built-in developer tools that allow you to profile your code, measure execution time, and identify memory usage.

### Example of Performance Profiling
1. Open the browser's developer tools (usually by pressing F12 or right-clicking and selecting "Inspect").
2. Navigate to the "Performance" or "Profiler" tab.
3. Start recording the performance while interacting with your application.
4. Stop the recording and analyze the results, looking for long-running functions, memory usage, and potential memory leaks.

### Example of Using Performance API
```javascript
const start = performance.now(); // Start measuring time
// Some code to profile

const end = performance.now(); // End measuring time
console.log(`Execution time: ${end - start} milliseconds`);
```

## Browser DevTools Performance
The browser's developer tools provide a performance profiling feature that allows you to analyze the performance of your JavaScript code. You can use it to identify slow functions, memory leaks, and other performance issues.

### Example of Using Browser DevTools Performance
1. Open the browser's developer tools (usually by pressing F12 or right-clicking and selecting "Inspect").
2. Navigate to the "Performance" or "Profiler" tab.
3. Click the "Record" button to start profiling your application.
4. Interact with your application to simulate user actions.
5. Click the "Stop" button to stop profiling and analyze the results.

## Browser Memory tools
The browser's developer tools provide memory profiling features that allow you to analyze the memory usage of your JavaScript application. You can use these tools to identify memory leaks, detached DOM nodes, and other memory-related issues.

### Example of Using Browser Memory Tools
1. Open the browser's developer tools (usually by pressing F12 or right-clicking and selecting "Inspect").
2. Navigate to the "Memory" or "Heap" tab.
3. Take a snapshot of the current memory usage.
4. Interact with your application to simulate user actions.
5. Take another snapshot and compare it with the previous one to identify memory leaks or increased memory usage.

## Lazy loading
Lazy loading is a performance optimization technique that defers the loading of non-critical resources until they are needed. This can improve the initial load time of a web application and reduce memory usage by only loading resources when they are required.

### Example of Lazy Loading Images
```html
<img src="placeholder.jpg" data-src="actual-image.jpg" alt="Lazy Loaded Image" class="lazy-load">
<script>
    document.addEventListener('DOMContentLoaded', () => {
        const lazyImages = document.querySelectorAll('.lazy-load');
        const observer = new IntersectionObserver((entries, observer) => {
        entries.forEach(entry => {
            if (entry.isIntersecting) {
            const img = entry.target;
            img.src = img.dataset.src; // Load the actual image
            observer.unobserve(img); // Stop observing the image
            }
        });
        });
    
        lazyImages.forEach(img => {
        observer.observe(img); // Start observing each lazy-loaded image
        });
    });
</script>
```

## Code splitting
Code splitting is a performance optimization technique that involves breaking up your JavaScript code into smaller chunks or modules. This allows you to load only the necessary code for a specific page or feature, reducing the initial load time and improving performance.

### Example of Code Splitting with Webpack
```javascript
// In your main JavaScript file
import(/* webpackChunkName: "moduleA" */ './moduleA').then(moduleA => {
    moduleA.doSomething();
});

// In moduleA.js
export function doSomething() {
    console.log('Module A is doing something');
}
```

## Memoization
Memoization is a performance optimization technique that involves caching the results of expensive function calls and returning the cached result when the same inputs occur again. This can significantly improve performance for functions that are called frequently with the same arguments.

### Example of Memoization
```javascript
function memoize(fn) {
    const cache = new Map();
    return function(...args) {
        const key = JSON.stringify(args);
        if (cache.has(key)) {
            return cache.get(key); // Return cached result
        }
        const result = fn(...args);
        cache.set(key, result); // Cache the result
        return result;
    };
}

// Example usage
const expensiveFunction = (num) => {
    console.log('Calculating...');
    return num * num; // Simulate an expensive calculation
};

const memoizedFunction = memoize(expensiveFunction);
console.log(memoizedFunction(5)); // Calculating... 25
console.log(memoizedFunction(5)); // 25 (cached result, no calculation)
console.log(memoizedFunction(10)); // Calculating... 100
```

## Efficient DOM manipulation
Efficient DOM manipulation is crucial for improving the performance of web applications. Frequent and unnecessary updates to the DOM can lead to performance issues, so it's important to minimize DOM manipulations and batch updates when possible.

### Example of Efficient DOM Manipulation
```javascript
const container = document.getElementById('container');
// Inefficient way: multiple DOM manipulations
const items = ['Item 1', 'Item 2', 'Item 3'];
items.forEach(item => {
    const div = document.createElement('div');
    div.textContent = item;
    container.appendChild(div); // Each appendChild triggers a reflow
});

// Efficient way: batch DOM manipulations
const fragment = document.createDocumentFragment();
items.forEach(item => {
    const div = document.createElement('div');
    div.textContent = item;
    fragment.appendChild(div); // Append to fragment instead of DOM
});
container.appendChild(fragment); // Single appendChild triggers a reflow
```

## Event delegation
Event delegation is a performance optimization technique that involves attaching a single event listener to a parent element instead of multiple child elements. This allows you to handle events for dynamically added elements and reduces the number of event listeners in your application.

### Example of Event Delegation
```javascript
const list = document.getElementById('list');
// Attach a single event listener to the parent element
list.addEventListener('click', (event) => {
    if (event.target && event.target.nodeName === 'LI') {
        console.log(`List item clicked: ${event.target.textContent}`);
    }
});

// Dynamically add list items
const newItem = document.createElement('li');
newItem.textContent = 'New Item';
list.appendChild(newItem); // The event listener will still work for this new item
```

## Debouncing and throttling
Debouncing and throttling are performance optimization techniques that help control the rate at which a function is executed. They are commonly used to improve performance in scenarios where a function is called frequently, such as during window resizing, scrolling, or input events.

### Example of Debouncing
```javascript
function debounce(func, wait) {
    let timeout;
    return function(...args) {
        clearTimeout(timeout);
        timeout = setTimeout(() => func.apply(this, args), wait);
    };
}

// Example usage
const handleResize = () => {
    console.log('Window resized');
};

window.addEventListener('resize', debounce(handleResize, 200)); // Debounce the resize event
```

### Example of Throttling
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
    console.log('Window scrolled');
};

window.addEventListener('scroll', throttle(handleScroll, 200)); // Throttle the scroll event
```

# Security

## XSS (Cross-Site Scripting)
Cross-Site Scripting (XSS) is a security vulnerability that allows attackers to inject malicious scripts into web pages viewed by other users. This can lead to unauthorized access to sensitive information, session hijacking, and other malicious activities. XSS attacks typically occur when user input is not properly sanitized or escaped before being rendered on a web page.

### Example of XSS Vulnerability
```javascript
// Vulnerable code that directly inserts user input into the DOM
const userInput = '<script>alert("XSS Attack!");</script>';
document.getElementById('output').innerHTML = userInput; // This will execute the injected script
```

### Preventing XSS Attacks
To prevent XSS attacks, it is essential to sanitize and escape user input before rendering it on the web page. This can be done using various techniques, such as:
1. **Escaping HTML**: Convert special characters in user input to their corresponding HTML entities.
```javascript
function escapeHTML(str) {
    return str.replace(/&/g, '&amp;')
              .replace(/</g, '&lt;')
              .replace(/>/g, '&gt;')
              .replace(/"/g, '&quot;')
              .replace(/'/g, '&#039;');
}
const userInput = '<script>alert("XSS Attack!");</script>';
const safeInput = escapeHTML(userInput);
document.getElementById('output').innerHTML = safeInput; // This will display the input as text, not execute it
```

## DOM-based XSS
DOM-based XSS is a type of Cross-Site Scripting (XSS) vulnerability that occurs when the client-side JavaScript code manipulates the Document Object Model (DOM) in an unsafe manner, allowing attackers to inject malicious scripts. Unlike traditional XSS, which involves server-side vulnerabilities, DOM-based XSS is entirely client-side and can be exploited by manipulating the URL or other client-side inputs.

### Example of DOM-based XSS Vulnerability
```javascript
// Vulnerable code that reads user input from the URL and inserts it into the DOM
const urlParams = new URLSearchParams(window.location.search);
const userInput = urlParams.get('input'); // Get user input from URL parameter
document.getElementById('output').innerHTML = userInput; // This will execute any injected script if the input is not sanitized
```

## SQL Injection awareness
SQL Injection is a security vulnerability that allows attackers to manipulate SQL queries by injecting malicious input into user-supplied data. This can lead to unauthorized access to the database, data leakage, and other malicious activities. SQL Injection typically occurs when user input is not properly sanitized or parameterized before being used in SQL queries.

### Example of SQL Injection Vulnerability
```javascript
// Vulnerable code that constructs an SQL query using user input
const userInput = "'; DROP TABLE users; --"; // Malicious input
const query = `SELECT * FROM users WHERE username = '${userInput}'`; // This will execute the injected SQL command
```

## CSRF (Cross-Site Request Forgery)
Cross-Site Request Forgery (CSRF) is a security vulnerability that allows attackers to trick users into performing actions on a web application without their consent. This can lead to unauthorized actions being performed on behalf of the user, such as changing account settings or making transactions. CSRF attacks typically occur when a user is authenticated on a website and visits a malicious site that sends requests to the target site.

### Example of CSRF Vulnerability
```html
<!-- Vulnerable form that performs an action on the server -->
<form action="https://example.com/change-password" method="POST">
    <input type="hidden" name="newPassword" value="attackerPassword">
    <input type="submit" value="Change Password">
</form>
```

### Preventing CSRF Attacks
To prevent CSRF attacks, it is essential to implement anti-CSRF tokens and validate them on the server side. This ensures that requests are coming from legitimate sources and not from malicious sites.
```javascript
// Example of generating and validating CSRF tokens
// Server-side code (Node.js/Express)
const csrf = require('csurf');
const csrfProtection = csrf({ cookie: true });
app.use(csrfProtection);
app.get('/form', (req, res) => {
    res.render('form', { csrfToken: req.csrfToken() }); // Include CSRF token in the form
});
app.post('/change-password', csrfProtection, (req, res) => {
    // Validate CSRF token and process the request
});
```

## CORS (Cross-Origin Resource Sharing)
Cross-Origin Resource Sharing (CORS) is a security feature implemented by web browsers that restricts web pages from making requests to a different domain than the one that served the web page. CORS is used to prevent malicious websites from accessing sensitive data on other domains without permission. It allows servers to specify which origins are allowed to access their resources.

### Example of CORS Configuration
```javascript
// Server-side code (Node.js/Express) to enable CORS
const express = require('express');
const cors = require('cors');
const app = express();

// Enable CORS for all routes
app.use(cors());

// Enable CORS for specific routes
app.get('/api/data', cors(), (req, res) => {
    res.json({ message: 'This is CORS-enabled for all origins!' });
});

// Enable CORS for specific origins
app.get('/api/data', cors({ origin: 'https://example.com' }), (req, res) => {
    res.json({ message: 'This is CORS-enabled for https://example.com only!' });
});
```

## Content Security Policy (CSP)
Content Security Policy (CSP) is a security feature that helps prevent Cross-Site Scripting (XSS) and other code injection attacks by specifying which sources of content are allowed to be loaded on a web page. CSP allows web developers to define a set of rules that restrict the types of content that can be executed, such as scripts, styles, images, and more.

### Example of Content Security Policy
```html
<!-- Example of a Content Security Policy header -->
<meta http-equiv="Content-Security-Policy" content="default-src 'self'; script-src 'self' https://trusted-scripts.com; style-src 'self' https://trusted-styles.com; img-src 'self' https://trusted-images.com;">
```

### Example of Content Security Policy in HTTP Headers
```http
Content-Security-Policy: default-src 'self'; script-src 'self' https://trusted-scripts.com; style-src 'self' https://trusted-styles.com; img-src 'self' https://trusted-images.com;
```

## Input validation and sanitization
Input validation and sanitization are essential security practices that help prevent various types of attacks, such as Cross-Site Scripting (XSS), SQL Injection, and other code injection attacks. Input validation ensures that user input meets specific criteria before being processed, while sanitization removes or escapes potentially harmful characters from the input.

### Example of Input Validation
```javascript
// Example of input validation for a username
function validateUsername(username) {
    const usernameRegex = /^[a-zA-Z0-9_]{3,20}$/; // Allow alphanumeric characters and underscores, 3-20 characters long
    return usernameRegex.test(username);
}
```
### Example of Input Sanitization
```javascript
// Example of input sanitization for user input
function sanitizeInput(input) {
    return input.replace(/&/g, '&amp;')
                .replace(/</g, '&lt;')
                .replace(/>/g, '&gt;')
                .replace(/"/g, '&quot;')
                .replace(/'/g, '&#039;');
}
```

## Output escaping
Output escaping is a security practice that involves converting special characters in user input into their corresponding HTML entities before rendering them on a web page. This helps prevent Cross-Site Scripting (XSS) attacks by ensuring that user input is treated as text rather than executable code.

### Example of Output Escaping
```javascript
// Example of output escaping for user input
function escapeOutput(output) {
    return output.replace(/&/g, '&amp;')
                 .replace(/</g, '&lt;')
                 .replace(/>/g, '&gt;')
                 .replace(/"/g, '&quot;')
                 .replace(/'/g, '&#039;');
}
```

## Secure localStorage usage
LocalStorage is a web storage API that allows you to store key-value pairs in a web browser. While it is convenient for storing data on the client side, it is important to use it securely to prevent unauthorized access and data leaks. Sensitive information should not be stored in localStorage, as it can be accessed by any script running on the same domain.

### Example of Secure localStorage Usage
```javascript
// Example of securely storing and retrieving data in localStorage
// Store data securely (avoid storing sensitive information)
function storeData(key, value) {
    const sanitizedValue = sanitizeInput(value); // Sanitize the value before storing
    localStorage.setItem(key, sanitizedValue);
}

// Retrieve data securely
function retrieveData(key) {
    const value = localStorage.getItem(key);
    return value ? escapeOutput(value) : null; // Escape the output before using it
}
```

## JWT Security concepts
JSON Web Tokens (JWT) are a compact, URL-safe means of representing claims to be transferred between two parties. They are commonly used for authentication and authorization in web applications. JWTs consist of three parts: a header, a payload, and a signature. The header specifies the algorithm used for signing the token, the payload contains the claims (such as user information), and the signature is used to verify the integrity of the token.

### Example of JWT Structure
```javascript
const jwt = require('jsonwebtoken');
// Example of creating a JWT
const payload = { userId: 123, username: 'john_doe' };
const secretKey = 'your_secret_key';
const token = jwt.sign(payload, secretKey, { expiresIn: '1h' }); // Create a JWT with a 1-hour expiration
console.log(token); // Output the generated JWT
```

## Never trust client-side validation
Client-side validation is a useful technique for improving user experience by providing immediate feedback on form inputs. However, it should never be relied upon for security purposes, as it can be easily bypassed by attackers. All input validation and sanitization should be performed on the server side to ensure the integrity and security of the application.

### Example of Server-Side Validation
```javascript
// Example of server-side validation for a username
const express = require('express');
const app = express();
app.use(express.json());

app.post('/register', (req, res) => {
    const { username } = req.body;
    if (!validateUsername(username)) {
        return res.status(400).json({ error: 'Invalid username' });
    }
    // Proceed with registration logic
    res.status(200).json({ message: 'User registered successfully' });
});

function validateUsername(username) {
    const usernameRegex = /^[a-zA-Z0-9_]{3,20}$/; // Allow alphanumeric characters and underscores, 3-20 characters long
    return usernameRegex.test(username);
}
```

## Prototype pollution
Prototype pollution is a security vulnerability that occurs when an attacker is able to manipulate the prototype of a base object, leading to unexpected behavior in the application. This can happen when user input is used to modify the prototype of built-in objects, such as `Object.prototype`, allowing attackers to inject properties or methods that can affect all instances of that object.

### Example of Prototype Pollution Vulnerability
```javascript
// Vulnerable code that allows prototype pollution
function setProperty(obj, key, value) {
    obj[key] = value; // This can modify the prototype if key is "__proto__"
}

// Example of an attacker exploiting prototype pollution
const userInput = { "__proto__": { "isAdmin": true } }; // Malicious input
setProperty({}, userInput.__proto__, true); // This modifies Object.prototype
console.log({}.isAdmin); // true (unexpected behavior due to prototype pollution)
```

# Functional Programming

## Pure Functions
A pure function is a function that, given the same input, will always return the same output and does not have any side effects. Pure functions do not modify any external state or variables, and they do not rely on any external state that may change. This makes them predictable and easier to test.

### Example of Pure Functions
```javascript
// Pure function that adds two numbers
function add(a, b) {
    return a + b; // Always returns the same output for the same inputs
}

// Pure function that calculates the square of a number
function square(x) {
    return x * x; // Always returns the same output for the same input
}
```

## Immutability
Immutability is a concept in functional programming that refers to the idea that data should not be modified after it has been created. Instead of changing existing data, new data structures are created with the desired changes. This helps prevent unintended side effects and makes it easier to reason about the code.

### Example of Immutability
```javascript
// Example of immutability with arrays
const originalArray = [1, 2, 3];

// Create a new array with an additional element without modifying the original array
const newArray = [...originalArray, 4]; // Using spread operator to create a new array
console.log(originalArray); // [1, 2, 3] (original array remains unchanged)
console.log(newArray); // [1, 2, 3, 4] (new array with the additional element)
```

## First-Class Functions
In JavaScript, functions are first-class citizens, meaning they can be treated like any other value. They can be assigned to variables, passed as arguments to other functions, and returned from other functions. This allows for higher-order functions and functional programming techniques.

### Example of First-Class Functions
```javascript
// Assigning a function to a variable
const greet = function(name) {
    return `Hello, ${name}!`;
};

// Passing a function as an argument to another function
function processUserInput(callback) {
    const name = 'Alice';
    console.log(callback(name)); // Call the callback function with the name
}

// Returning a function from another function
function createMultiplier(multiplier) {
    return function(value) {
        return value * multiplier; // Return a new function that multiplies the input by the multiplier
    };
}

// Example usage
processUserInput(greet); // Output: Hello, Alice!

const double = createMultiplier(2);
console.log(double(5)); // Output: 10 (5 multiplied by 2)
```

## Higher-Order Functions
Higher-order functions are functions that can take other functions as arguments or return functions as their result.

### Example of Higher-Order Functions
```javascript
// Higher-order function that takes a function as an argument
function applyOperation(a, b, operation) {
    return operation(a, b); // Call the passed-in function with the provided arguments
}

// Example usage
const add = (x, y) => x + y;

const multiply = (x, y) => x * y;

console.log(applyOperation(5, 3, add)); // Output: 8 (5 + 3)
console.log(applyOperation(5, 3, multiply)); // Output: 15 (5 * 3)
```

## Function Composition
Function composition is a functional programming technique that involves combining multiple functions to create a new function. The output of one function is passed as the input to the next function, allowing for a sequence of operations to be performed in a clear and concise manner.

### Example of Function Composition
```javascript
// Function to add 2 to a number
const add2 = (x) => x + 2;
// Function to multiply a number by 3
const multiplyBy3 = (x) => x * 3;

// Function to compose two functions
const compose = (f, g) => (x) => f(g(x));

// Example usage
const add2ThenMultiplyBy3 = compose(multiplyBy3, add2);

console.log(add2ThenMultiplyBy3(4)); // Output: 18 (4 + 2 = 6, then 6 * 3 = 18)
```

## Currying
Currying is a functional programming technique that involves transforming a function that takes multiple arguments into a sequence of functions that each take a single argument. This allows for partial application of functions, where some arguments can be fixed while others can be provided later.

### Example of Currying
```javascript
// Function that takes two arguments and returns their sum
function add(a, b) {
    return a + b;
}

// Curried version of the add function
function curriedAdd(a) {
    return function(b) {
        return a + b; // Return a new function that takes the second argument
    };
}

// Example usage
const add5 = curriedAdd(5); // Fix the first argument to 5

console.log(add5(3)); // Output: 8 (5 + 3)
console.log(curriedAdd(2)(4)); // Output: 6 (2 + 4)
```

## Partial Application
Partial application is a functional programming technique that involves fixing a number of arguments to a function, producing a new function that takes the remaining arguments. This allows for more flexible and reusable functions.

### Example of Partial Application
```javascript
// Function that takes three arguments and returns their sum
function sum(a, b, c) {
    return a + b + c;
}

// Partial application function
function partial(fn, ...fixedArgs) {
    return function(...remainingArgs) {
        return fn(...fixedArgs, ...remainingArgs); // Call the original function with fixed and remaining arguments
    };
}

// Example usage
const add5And3 = partial(sum, 5, 3); // Fix the first two arguments to 5 and 3

console.log(add5And3(2)); // Output: 10 (5 + 3 + 2)
console.log(partial(sum, 1)(2, 3)); // Output: 6 (1 + 2 + 3)
```

## Map
The `map` function is a higher-order function that creates a new array by applying a provided function to each element of the original array. It does not modify the original array and returns a new array with the transformed values.

### Example of Map
```javascript
const numbers = [1, 2, 3, 4, 5];
// Use map to create a new array with each number squared
const squaredNumbers = numbers.map(num => num * num);
console.log(squaredNumbers); // Output: [1, 4, 9, 16, 25]
```

## Filter
The `filter` function is a higher-order function that creates a new array containing only the elements of the original array that satisfy a specified condition. It does not modify the original array and returns a new array with the filtered values.

### Example of Filter
```javascript
const numbers = [1, 2, 3, 4, 5];
// Use filter to create a new array with only even numbers
const evenNumbers = numbers.filter(num => num % 2 === 0);
console.log(evenNumbers); // Output: [2, 4]
```

## Reduce
The `reduce` function is a higher-order function that applies a provided function to an accumulator and each element of the array (from left to right) to reduce it to a single value. It takes an initial value for the accumulator and returns the final accumulated result.

### Example of Reduce
```javascript
const numbers = [1, 2, 3, 4, 5];
// Use reduce to calculate the sum of all numbers in the array
const sum = numbers.reduce((accumulator, currentValue) => accumulator + currentValue, 0);
console.log(sum); // Output: 15 (1 + 2 + 3 + 4 + 5)
```

## Referential Transparency
Referential transparency is a property of expressions in programming where an expression can be replaced with its corresponding value without changing the program's behavior. In functional programming, referential transparency is an important concept that allows for easier reasoning about code and enables optimizations such as memoization.

### Example of Referential Transparency
```javascript
// Example of a referentially transparent function
function add(a, b) {
    return a + b; // This function always returns the same output for the same inputs
}

// Example of a function that is not referentially transparent
let counter = 0;

function increment() {
    counter++; // This function has side effects and does not always return the same output for the same inputs
    return counter;
}
```

## Side Effects
In programming, a side effect is any operation that modifies some state or interacts with the outside world (e.g., changing a variable, writing to a file, making a network request) outside of its own scope. In functional programming, functions are expected to be pure and free of side effects, which makes them easier to reason about and test.

### Example of Side Effects
```javascript
// Example of a function with side effects
let counter = 0;

function increment() {
    counter++; // This function modifies the external variable 'counter', which is a side effect
    return counter;
}

// Example of a pure function without side effects
function add(a, b) {
    return a + b; // This function does not modify any external state and always returns the same output for the same inputs
}
```

## Declarative Programming
Declarative programming is a programming paradigm that focuses on describing what the program should accomplish rather than detailing how to achieve it. In declarative programming, you express the desired outcome, and the underlying implementation takes care of the execution. This contrasts with imperative programming, where you provide step-by-step instructions on how to achieve a specific result.

### Example of Declarative Programming
```javascript
// Example of declarative programming using the map function
const numbers = [1, 2, 3, 4, 5];
// Use map to create a new array with each number squared
const squaredNumbers = numbers.map(num => num * num);
console.log(squaredNumbers); // Output: [1, 4, 9, 16, 25]
```

## Imperative Programming
Imperative programming is a programming paradigm that focuses on describing how a program should achieve a specific result through a sequence of statements or commands. In imperative programming, you provide step-by-step instructions that change the program's state to achieve the desired outcome. This contrasts with declarative programming, where you describe what the program should accomplish without specifying how to do it.

### Example of Imperative Programming
```javascript
// Example of imperative programming using a for loop
const numbers = [1, 2, 3, 4, 5];
// Create a new array to store the squared numbers
const squaredNumbers = [];
for (let i = 0; i < numbers.length; i++) {
    squaredNumbers.push(numbers[i] * numbers[i]); // Calculate the square and add it to the new array
}
console.log(squaredNumbers); // Output: [1, 4, 9, 16, 25]
```

# Advanced Browser Concepts

## Rendering pipeline
The rendering pipeline is the process by which a web browser takes HTML, CSS, and JavaScript code and converts it into pixels on the screen. It involves several stages, including parsing, style calculation, layout, painting, and compositing. Understanding the rendering pipeline is important for optimizing web performance and ensuring smooth user experiences.

### Stages of the Rendering Pipeline
1. **Parsing**: The browser parses the HTML and CSS to create the Document Object Model (DOM) and the CSS Object Model (CSSOM).
2. **Style Calculation**: The browser calculates the styles for each element based on the CSS rules and the DOM structure.
3. **Layout**: The browser calculates the position and size of each element based on the styles and the DOM structure.
4. **Painting**: The browser paints the pixels for each element onto the screen based on the calculated layout and styles.
5. **Compositing**: The browser combines the painted layers into a final image that is displayed on the screen.

### Example of Rendering Pipeline
```javascript
// Example of measuring the time taken for each stage of the rendering pipeline
const startTime = performance.now();

// Simulate some DOM manipulation
const div = document.createElement('div');

div.style.width = '100px';
div.style.height = '100px';
div.style.backgroundColor = 'red';
document.body.appendChild(div);

const endTime = performance.now();
console.log(`Time taken for rendering pipeline: ${endTime - startTime} ms`);
```

## Reflow and Repaint
Reflow and repaint are two important concepts in the rendering pipeline that affect the performance of web applications. Reflow (also known as layout) occurs when the browser recalculates the positions and sizes of elements in the DOM, while repaint occurs when the browser redraws the pixels on the screen for elements that have changed visually.

### Example of Reflow and Repaint
```javascript
// Example of triggering reflow and repaint
const div = document.createElement('div');
div.style.width = '100px';
div.style.height = '100px';
div.style.backgroundColor = 'red';
document.body.appendChild(div);

// Trigger reflow by changing the width of the div
div.style.width = '200px'; // This will cause a reflow
// Trigger repaint by changing the background color of the div
div.style.backgroundColor = 'blue'; // This will cause a repaint
```

## Layout
Layout is the process by which the browser calculates the position and size of each element in the DOM based on the styles applied to them. It is an important part of the rendering pipeline, as it determines how elements are arranged on the screen. Layout can be affected by changes to the DOM, CSS styles, or window size, and it can trigger reflows if elements need to be repositioned or resized.

### Example of Layout
```javascript
// Example of triggering layout by changing the size of an element
const div = document.createElement('div');
div.style.width = '100px';
div.style.height = '100px';
div.style.backgroundColor = 'red';
document.body.appendChild(div);

// Trigger layout by changing the height of the div
div.style.height = '200px'; // This will cause a layout recalculation
```

## Compositing
Compositing is the final stage of the rendering pipeline, where the browser combines the painted layers into a final image that is displayed on the screen. Compositing allows the browser to efficiently render complex scenes by separating elements into layers and only redrawing the layers that have changed. This can improve performance and reduce the amount of work the browser needs to do when updating the display.

### Example of Compositing
```javascript
// Example of triggering compositing by using CSS transforms
const div = document.createElement('div');
div.style.width = '100px';
div.style.height = '100px';
div.style.backgroundColor = 'red';
div.style.position = 'absolute';
document.body.appendChild(div);

// Trigger compositing by applying a CSS transform
div.style.transform = 'translateX(100px)'; // This will cause the browser to create a new layer for the div and composite it onto the screen
```

## Critical Rendering concepts
Critical rendering refers to the process of optimizing the rendering pipeline to ensure that the most important content is displayed to the user as quickly as possible. This involves identifying and prioritizing the critical resources (HTML, CSS, JavaScript) that are necessary for rendering above-the-fold content, while deferring or asynchronously loading non-critical resources.

### Techniques for Critical Rendering Optimization
1. **Minimize Render-Blocking Resources**: Reduce the number of CSS and JavaScript files that block the rendering of the page. Use techniques like inlining critical CSS and deferring non-critical JavaScript.
2. **Prioritize Above-the-Fold Content**: Ensure that the content visible to the user without scrolling is loaded and rendered first. This can be achieved by optimizing the order of resource loading and using techniques like lazy loading for below-the-fold content.
3. **Use Efficient CSS Selectors**: Avoid complex CSS selectors that can slow down the style calculation and layout processes. Use simple and efficient selectors to improve rendering performance.
4. **Optimize Images and Media**: Compress images and use appropriate formats to reduce their size and loading time. Use responsive images and lazy loading to improve performance.
5. **Use Browser Caching**: Leverage browser caching to store static resources locally, reducing the need to fetch them from the server on subsequent visits.

## requestAnimationFrame
`requestAnimationFrame` is a browser API that allows you to schedule a function to be called before the next repaint of the browser. It is commonly used for creating smooth animations and improving performance by synchronizing updates with the browser's rendering cycle. Using `requestAnimationFrame` ensures that your animations run at the optimal frame rate and reduces unnecessary work when the page is not visible.

### Example of requestAnimationFrame
```javascript
let start = null;
function step(timestamp) {
    if (!start) start = timestamp;
    const progress = timestamp - start;
    const div = document.getElementById('animatedDiv');
    div.style.transform = `translateX(${Math.min(progress / 10, 200)}px)`; // Move the div to the right
    if (progress < 2000) { // Stop after 2 seconds
        requestAnimationFrame(step); // Schedule the next frame
    }
}

// Start the animation
requestAnimationFrame(step);
```

## Intersection Observer
The Intersection Observer API is a browser API that allows you to asynchronously observe changes in the intersection of a target element with an ancestor element or the viewport. It is commonly used for lazy loading images, implementing infinite scrolling, and triggering animations when elements come into view. The Intersection Observer API provides a more efficient way to handle these tasks compared to traditional scroll event listeners.

### Example of Intersection Observer
```javascript
// Create an Intersection Observer instance
const observer = new IntersectionObserver((entries, observer) => {
    entries.forEach(entry => {
        if (entry.isIntersecting) {
            console.log('Element is in view:', entry.target);
            // Perform actions when the element is in view, e.g., load content or trigger animations
            observer.unobserve(entry.target); // Stop observing the element if no longer needed
        }
    });
}, { threshold: 0.5 }); // Trigger when 50% of the element is visible

// Target element to observe
const targetElement = document.getElementById('targetElement');

// Start observing the target element
observer.observe(targetElement);
```

## Mutation Observer
The Mutation Observer API is a browser API that allows you to watch for changes in the DOM tree, such as when elements are added, removed, or modified. It provides a more efficient and performant way to observe DOM changes compared to traditional methods like polling or using event listeners. Mutation Observers are commonly used for tasks like monitoring dynamic content updates, implementing custom UI components, and reacting to changes in the DOM.

### Example of Mutation Observer
```javascript
// Create a Mutation Observer instance
const observer = new MutationObserver((mutationsList, observer) => {
    mutationsList.forEach(mutation => {
        if (mutation.type === 'childList') {
            console.log('A child node has been added or removed:', mutation);
        } else if (mutation.type === 'attributes') {
            console.log('An attribute has been changed:', mutation);
        }
    });
});

// Target element to observe
const targetNode = document.getElementById('targetNode');

// Configuration for the observer (observe child nodes and attributes)
const config = { attributes: true, childList: true, subtree: true };

// Start observing the target node
observer.observe(targetNode, config);
```

## Resize Observer
The Resize Observer API is a browser API that allows you to observe changes to the size of an element. It provides a way to react to changes in an element's dimensions, such as when it is resized due to window resizing, content changes, or CSS modifications. The Resize Observer API is useful for implementing responsive designs, dynamic layouts, and custom UI components that need to adapt to size changes.

### Example of Resize Observer
```javascript
// Create a Resize Observer instance
const resizeObserver = new ResizeObserver(entries => {
    for (let entry of entries) {
        const { width, height } = entry.contentRect;
        console.log(`Element resized: ${entry.target.id}, Width: ${width}, Height: ${height}`);
        // Perform actions based on the new size, e.g., adjust layout or styles
    }
});

// Target element to observe
const targetElement = document.getElementById('resizableElement');

// Start observing the target element
resizeObserver.observe(targetElement);
```

## Web Workers
Web Workers are a browser feature that allows you to run JavaScript code in a separate thread from the main execution thread. This enables you to perform computationally intensive tasks without blocking the user interface, resulting in smoother performance and better responsiveness. Web Workers communicate with the main thread using a messaging system, allowing you to send and receive data between threads.

### Example of Web Workers
```javascript
// main.js (main thread)
// Create a new Web Worker
const worker = new Worker('worker.js');

// Listen for messages from the worker
worker.onmessage = function(event) {
    console.log('Message from worker:', event.data);
};

// Send a message to the worker
worker.postMessage('Hello, worker!');
```

```javascript
// worker.js (worker thread)
// Listen for messages from the main thread
self.onmessage = function(event) {
    console.log('Message from main thread:', event.data);
    // Perform some computation or task
    const result = event.data.toUpperCase(); // Example task: convert message to uppercase
    // Send the result back to the main thread
    self.postMessage(result);
};
```

## Service Workers
Service Workers are a browser feature that allows you to run scripts in the background, separate from the main web page. They enable features such as offline support, background sync, and push notifications. Service Workers act as a proxy between the web application and the network, allowing you to intercept and handle network requests, cache resources, and provide a better user experience even when the user is offline.

### Example of Service Workers
```javascript
// Registering a Service Worker in main.js
if ('serviceWorker' in navigator) {
    navigator.serviceWorker.register('/service-worker.js')
        .then(registration => {
            console.log('Service Worker registered with scope:', registration.scope);
        })
        .catch(error => {
            console.error('Service Worker registration failed:', error);
        });
}
```

```javascript
// service-worker.js (Service Worker script)
// Install event: cache resources
self.addEventListener('install', event => {
    event.waitUntil(
        caches.open('my-cache').then(cache => {
            return cache.addAll([
                '/',
                '/index.html',
                '/styles.css',
                '/script.js'
            ]);
        })
    );
});

// Fetch event: serve cached resources or fetch from network
self.addEventListener('fetch', event => {
    event.respondWith(
        caches.match(event.request).then(response => {
            return response || fetch(event.request);
        })
    );
});
```

## WebSockets
WebSockets are a protocol that provides full-duplex communication channels over a single TCP connection. They allow for real-time, bidirectional communication between a client (such as a web browser) and a server. WebSockets are commonly used for applications that require low-latency communication, such as chat applications, online gaming, and live data feeds.

### Example of WebSockets
```javascript
// Client-side code (JavaScript)
// Create a new WebSocket connection
const socket = new WebSocket('ws://example.com/socket');

// Listen for messages from the server
socket.onmessage = function(event) {
    console.log('Message from server:', event.data);
};

// Send a message to the server
socket.onopen = function() {
    socket.send('Hello, server!');
};

// Handle connection close
socket.onclose = function() {
    console.log('WebSocket connection closed');
};

// Handle errors
socket.onerror = function(error) {
    console.error('WebSocket error:', error);
};
```

```javascript
// Server-side code (Node.js with ws library)
const WebSocket = require('ws');
const wss = new WebSocket.Server({ port: 8080 });

wss.on('connection', function connection(ws) {
    console.log('Client connected');

    // Listen for messages from the client
    ws.on('message', function incoming(message) {
        console.log('Message from client:', message);
        // Echo the message back to the client
        ws.send(`Server received: ${message}`);
    });

    // Handle connection close
    ws.on('close', function close() {
        console.log('Client disconnected');
    });
});
```

## WebRTC
WebRTC (Web Real-Time Communication) is a technology that enables peer-to-peer communication between web browsers and mobile applications. It allows for real-time audio, video, and data sharing without the need for plugins or third-party software. WebRTC is commonly used for video conferencing, online gaming, and file sharing applications.

### Example of WebRTC
```javascript
// Client-side code (JavaScript)
// Create a new RTCPeerConnection
const peerConnection = new RTCPeerConnection();

// Get user media (audio and video)
navigator.mediaDevices.getUserMedia({ video: true, audio: true })
    .then(stream => {
        // Display the local video stream
        const localVideo = document.getElementById('localVideo');
        localVideo.srcObject = stream;

        // Add the local stream to the peer connection
        stream.getTracks().forEach(track => peerConnection.addTrack(track, stream));
    })
    .catch(error => {
        console.error('Error accessing media devices:', error);
    });

// Handle incoming remote stream
peerConnection.ontrack = function(event) {
    const remoteVideo = document.getElementById('remoteVideo');
    remoteVideo.srcObject = event.streams[0];
};

// Create an offer and set local description
peerConnection.createOffer()
    .then(offer => {
        return peerConnection.setLocalDescription(offer);
    })
    .then(() => {
        // Send the offer to the remote peer (e.g., via signaling server)
        // signalingServer.send({ type: 'offer', sdp: peerConnection.localDescription });
    })
    .catch(error => {
        console.error('Error creating offer:', error);
    });
```

## Server-Sent Events (SSE)
Server-Sent Events (SSE) is a technology that allows a server to push real-time updates to a web client over a single HTTP connection. Unlike WebSockets, SSE is unidirectional, meaning that the server can send updates to the client, but the client cannot send messages back to the server over the same connection. SSE is commonly used for applications that require real-time updates, such as live news feeds, stock tickers, and notifications.

### Example of Server-Sent Events (SSE)
```javascript
// Client-side code (JavaScript)
// Create a new EventSource to listen for server-sent events
const eventSource = new EventSource('/sse-endpoint');

// Listen for messages from the server
eventSource.onmessage = function(event) {
    console.log('Message from server:', event.data);
    // Update the UI with the received data
};

// Handle errors
eventSource.onerror = function(error) {
    console.error('SSE error:', error);
};
```

```javascript
// Server-side code (Node.js with Express)
const express = require('express');
const app = express();

app.get('/sse-endpoint', (req, res) => {
    res.setHeader('Content-Type', 'text/event-stream');
    res.setHeader('Cache-Control', 'no-cache');
    res.setHeader('Connection', 'keep-alive');

    // Send a message to the client every second
    const intervalId = setInterval(() => {
        const data = `data: ${new Date().toISOString()}\n\n`;
        res.write(data);
    }, 1000);

    // Clean up when the client disconnects
    req.on('close', () => {
        clearInterval(intervalId);
        res.end();
    });
});

app.listen(3000, () => {
    console.log('Server is running on port 3000');
});
```

## WebAssembly
WebAssembly (Wasm) is a binary instruction format that allows code written in languages like C, C++, and Rust to run in web browsers at near-native speed. It is designed to be a portable compilation target for high-level languages, enabling developers to write performance-critical code that can run alongside JavaScript in the browser. WebAssembly is particularly useful for applications that require heavy computation, such as games, video editing, and scientific simulations.

### Example of WebAssembly
```javascript
// JavaScript code to load and run a WebAssembly module
// Fetch the WebAssembly binary file
fetch('module.wasm')
    .then(response => response.arrayBuffer())
    .then(bytes => WebAssembly.instantiate(bytes))
    .then(results => {
        const instance = results.instance;
        // Call an exported function from the WebAssembly module
        const result = instance.exports.add(5, 3);
        console.log('Result from WebAssembly:', result); // Output: Result from WebAssembly: 8
    })
    .catch(error => {
        console.error('Error loading WebAssembly module:', error);
    });
```

```c
// C code to be compiled to WebAssembly (module.c)
#include <emscripten.h>

// Exported function to add two integers
EMSCRIPTEN_KEEPALIVE

int add(int a, int b) {
    return a + b;
}
```

## IndexedDB
IndexedDB is a low-level API for storing large amounts of structured data in the browser. It allows developers to create, read, update, and delete data in a transactional manner. IndexedDB is useful for applications that require offline storage, caching, or complex data structures. It provides a way to store data in key-value pairs and supports indexing for efficient querying.

### Example of IndexedDB
```javascript
// Open a database
const request = indexedDB.open('myDatabase', 1);

request.onupgradeneeded = function(event) {
    const db = event.target.result;
    // Create an object store with a key path
    const objectStore = db.createObjectStore('myObjectStore', { keyPath: 'id' });
    // Create an index for the name property
    objectStore.createIndex('name', 'name', { unique: false });
};

request.onsuccess = function(event) {
    const db = event.target.result;

    // Add data to the object store
    const transaction = db.transaction('myObjectStore', 'readwrite');
    const objectStore = transaction.objectStore('myObjectStore');
    objectStore.add({ id: 1, name: 'Alice' });
    objectStore.add({ id: 2, name: 'Bob' });

    transaction.oncomplete = function() {
        console.log('Data added to IndexedDB');
    };

    transaction.onerror = function(event) {
        console.error('Error adding data to IndexedDB:', event.target.error);
    };
};

// Read data from the object store
request.onsuccess = function(event) {
    const db = event.target.result;
    const transaction = db.transaction('myObjectStore', 'readonly');
    const objectStore = transaction.objectStore('myObjectStore');
    const getRequest = objectStore.get(1);

    getRequest.onsuccess = function(event) {
        console.log('Data retrieved from IndexedDB:', event.target.result);
    };

    getRequest.onerror = function(event) {
        console.error('Error retrieving data from IndexedDB:', event.target.error);
    };
};
```

## Cache API
The Cache API is a browser API that allows developers to store and retrieve network requests and responses in a cache. It is commonly used in conjunction with Service Workers to enable offline capabilities and improve performance by caching resources for faster loading. The Cache API provides methods to add, match, and delete cached requests and responses.

### Example of Cache API
```javascript
// Open a cache and add resources to it
caches.open('my-cache').then(cache => {
    cache.addAll([
        '/index.html',
        '/styles.css',
        '/script.js'
    ]).then(() => {
        console.log('Resources added to cache');
    }).catch(error => {
        console.error('Error adding resources to cache:', error);
    });
});

// Retrieve a cached resource
caches.match('/index.html').then(response => {
    if (response) {
        console.log('Cached resource found:', response);
        // Use the cached response (e.g., display it in the UI)
    } else {
        console.log('Cached resource not found');
        // Fetch the resource from the network if not found in cache
    }
}).catch(error => {
    console.error('Error retrieving cached resource:', error);
});
```

# JavaScript Design Patterns

## Module Pattern
The module pattern is a design pattern that allows you to encapsulate code into reusable modules, providing a way to organize and structure your JavaScript code. It helps in creating private and public members, preventing global namespace pollution, and promoting code reusability. The module pattern can be implemented using Immediately Invoked Function Expressions (IIFE) or ES6 modules.

### Example of Module Pattern using IIFE
```javascript
// Module pattern using IIFE
const myModule = (function() {
    // Private members
    let privateVariable = 'I am private';

    function privateMethod() {
        console.log(privateVariable);
    }

    // Public members
    return {
        publicMethod: function() {
            console.log('I am public');
            privateMethod(); // Accessing private method
        }
    };

})();

// Example usage
myModule.publicMethod(); // Output: I am public
// myModule.privateMethod(); // Error: privateMethod is not defined
```

## Revealing Module Pattern
The revealing module pattern is a variation of the module pattern that focuses on exposing only the public members of a module while keeping the private members hidden. It provides a clear and organized way to define the public API of a module, making it easier to understand and maintain. The revealing module pattern is implemented using an IIFE, similar to the module pattern.

### Example of Revealing Module Pattern
```javascript
// Revealing module pattern using IIFE
const myRevealingModule = (function() {
    // Private members
    let privateVariable = 'I am private';

    function privateMethod() {
        console.log(privateVariable);
    }

    // Public members
    function publicMethod() {
        console.log('I am public');
        privateMethod(); // Accessing private method
    }

    // Expose public members
    return {
        publicMethod: publicMethod
    };

})();

// Example usage
myRevealingModule.publicMethod(); // Output: I am public

```

## Factory Pattern
The factory pattern is a design pattern that provides a way to create objects without specifying the exact class of the object that will be created. It defines an interface for creating objects, allowing subclasses to alter the type of objects that will be created. The factory pattern promotes loose coupling and enhances code maintainability by encapsulating the object creation logic.

### Example of Factory Pattern
```javascript
// Factory function to create different types of shapes
function ShapeFactory() {
    this.createShape = function(type) {
        let shape;

        if (type === 'circle') {
            shape = new Circle();
        } else if (type === 'square') {
            shape = new Square();
        } else if (type === 'triangle') {
            shape = new Triangle();
        }

        return shape;
    };
}

// Shape classes
class Circle {
    draw() {
        console.log('Drawing a circle');
    }
}

class Square {
    draw() {
        console.log('Drawing a square');
    }
}

class Triangle {
    draw() {
        console.log('Drawing a triangle');
    }
}

// Example usage
const shapeFactory = new ShapeFactory();

const circle = shapeFactory.createShape('circle');
circle.draw(); // Output: Drawing a circle

const square = shapeFactory.createShape('square');
square.draw(); // Output: Drawing a square

const triangle = shapeFactory.createShape('triangle');
triangle.draw(); // Output: Drawing a triangle
```

## Constructor Pattern
The constructor pattern is a design pattern that uses constructor functions to create and initialize objects. It allows you to define a blueprint for creating objects with specific properties and methods. The constructor pattern promotes code reusability and provides a way to create multiple instances of an object with the same structure.

### Example of Constructor Pattern
```javascript
// Constructor function to create a Person object
function Person(name, age) {
    this.name = name;
    this.age = age;

    this.sayHello = function() {
        console.log(`Hello, my name is ${this.name} and I am ${this.age} years old.`);
    };
}

// Example usage
const person1 = new Person('Alice', 30);
person1.sayHello(); // Output: Hello, my name is Alice and I am 30 years old.

const person2 = new Person('Bob', 25);
person2.sayHello(); // Output: Hello, my name is Bob and I am 25 years old.
```

## Singleton Pattern
The singleton pattern is a design pattern that restricts the instantiation of a class to a single instance. It ensures that there is only one instance of the class and provides a global point of access to that instance. The singleton pattern is useful when you need to control access to shared resources or maintain a single state across an application.

### Example of Singleton Pattern
```javascript
// Singleton pattern using an IIFE
const Singleton = (function() {
    let instance;

    function createInstance() {
        const object = new Object('I am the instance');
        return object;
    }

    return {
        getInstance: function() {
            if (!instance) {
                instance = createInstance();
            }
            return instance;
        }
    };
})();

// Example usage
const instance1 = Singleton.getInstance();
const instance2 = Singleton.getInstance();
console.log(instance1 === instance2); // Output: true (both instances are the same)
```

## Observer Pattern
The observer pattern is a design pattern that defines a one-to-many dependency between objects, allowing multiple observers to be notified and updated automatically when the state of the subject object changes. It promotes loose coupling between the subject and its observers, making it easier to maintain and extend the code.

### Example of Observer Pattern
```javascript
// Subject (Observable) class
class Subject {
    constructor() {
        this.observers = [];
    }

    // Add an observer
    addObserver(observer) {
        this.observers.push(observer);
    }

    // Remove an observer
    removeObserver(observer) {
        this.observers = this.observers.filter(obs => obs !== observer);
    }

    // Notify all observers of a change
    notifyObservers(data) {
        this.observers.forEach(observer => observer.update(data));
    }
}

// Observer class
class Observer {
    constructor(name) {
        this.name = name;
    }

    // Update method called when the subject changes
    update(data) {
        console.log(`${this.name} received update: ${data}`);
    }
}

// Example usage
const subject = new Subject();
const observer1 = new Observer('Observer 1');
const observer2 = new Observer('Observer 2');

subject.addObserver(observer1);
subject.addObserver(observer2);

// Notify observers of a change
subject.notifyObservers('New data available');
// Output:
// Observer 1 received update: New data available
// Observer 2 received update: New data available
```

## Pub/Sub Pattern
The publish-subscribe (pub/sub) pattern is a messaging pattern that allows components to communicate with each other without being tightly coupled. In this pattern, publishers send messages (events) to a central hub (the event bus), and subscribers listen for specific events and react accordingly. This decouples the sender and receiver, making it easier to manage communication between different parts of an application.

### Example of Pub/Sub Pattern
```javascript
// Pub/Sub implementation
class PubSub {
    constructor() {
        this.events = {};
    }

    // Subscribe to an event
    subscribe(event, callback) {
        if (!this.events[event]) {
            this.events[event] = [];
        }
        this.events[event].push(callback);
    }

    // Unsubscribe from an event
    unsubscribe(event, callback) {
        if (this.events[event]) {
            this.events[event] = this.events[event].filter(cb => cb !== callback);
        }
    }

    // Publish an event
    publish(event, data) {
        if (this.events[event]) {
            this.events[event].forEach(callback => callback(data));
        }
    }
}

// Example usage
const pubSub = new PubSub();

// Subscriber 1
pubSub.subscribe('message', data => {
    console.log('Subscriber 1 received:', data);
});

// Subscriber 2
pubSub.subscribe('message', data => {
    console.log('Subscriber 2 received:', data);
});

// Publish an event
pubSub.publish('message', 'Hello, subscribers!');

// Output:
// Subscriber 1 received: Hello, subscribers!
// Subscriber 2 received: Hello, subscribers!
```

## Strategy Pattern
The strategy pattern is a design pattern that defines a family of algorithms, encapsulates each one, and makes them interchangeable. It allows the algorithm to vary independently from the clients that use it. The strategy pattern promotes code reusability and flexibility by enabling the selection of different algorithms at runtime without modifying the client code.

### Example of Strategy Pattern
```javascript
// Strategy interface
class Strategy {
    execute(a, b) {
        throw new Error('Strategy.execute() must be implemented');
    }
}

// Concrete strategies
class AddStrategy extends Strategy {
    execute(a, b) {
        return a + b;
    }
}

class SubtractStrategy extends Strategy {
    execute(a, b) {
        return a - b;
    }
}

// Context class
class Context {
    constructor(strategy) {
        this.strategy = strategy;
    }

    setStrategy(strategy) {
        this.strategy = strategy;
    }

    executeStrategy(a, b) {
        return this.strategy.execute(a, b);
    }
}

// Example usage
const context = new Context(new AddStrategy());
console.log('Addition:', context.executeStrategy(5, 3)); // Output: Addition: 8
context.setStrategy(new SubtractStrategy());
console.log('Subtraction:', context.executeStrategy(5, 3)); // Output: Subtraction: 2
```

## Adapter Pattern
The adapter pattern is a design pattern that allows incompatible interfaces to work together. It acts as a bridge between two different interfaces, enabling them to communicate and work together without modifying their existing code. The adapter pattern is useful when integrating third-party libraries or legacy code into a new system.

### Example of Adapter Pattern
```javascript
// Target interface
class Target {
    request() {
        throw new Error('Target.request() must be implemented');
    }
}

// Adaptee class with a different interface
class Adaptee {
    specificRequest() {
        return 'Adaptee: Specific request';
    }
}

// Adapter class that implements the Target interface and adapts the Adaptee
class Adapter extends Target {
    constructor(adaptee) {
        super();
        this.adaptee = adaptee;
    }

    request() {
        return this.adaptee.specificRequest();
    }
}

// Example usage
const adaptee = new Adaptee();

const adapter = new Adapter(adaptee);
console.log(adapter.request()); // Output: Adaptee: Specific request
```

## Decorator Pattern
The decorator pattern is a design pattern that allows behavior to be added to individual objects, dynamically, without affecting the behavior of other objects from the same class. It provides a flexible alternative to subclassing for extending functionality. The decorator pattern is useful for adding responsibilities to objects at runtime, enabling a more modular and maintainable design.

### Example of Decorator Pattern
```javascript
// Base class
class Coffee {
    cost() {
        return 5; // Base cost of coffee
    }
}

// Decorator class
class MilkDecorator {
    constructor(coffee) {
        this.coffee = coffee;
    }

    cost() {
        return this.coffee.cost() + 2; // Add cost of milk
    }
} 

// Decorator class
class SugarDecorator {
    constructor(coffee) {
        this.coffee = coffee;
    }

    cost() {
        return this.coffee.cost() + 1; // Add cost of sugar
    }
}

// Example usage
const myCoffee = new Coffee();

const coffeeWithMilk = new MilkDecorator(myCoffee);
const coffeeWithMilkAndSugar = new SugarDecorator(coffeeWithMilk);

console.log('Cost of coffee with milk:', coffeeWithMilk.cost()); // Output: Cost of coffee with milk: 7
console.log('Cost of coffee with milk and sugar:', coffeeWithMilkAndSugar.cost()); // Output: Cost of coffee with milk and sugar: 8
```

## Proxy Pattern
The proxy pattern is a design pattern that provides a surrogate or placeholder for another object to control access to it. It allows you to add additional functionality, such as access control, logging, or caching, without modifying the original object's code. The proxy pattern is useful for managing resource-intensive objects or controlling access to sensitive data.

### Example of Proxy Pattern
```javascript
// Real subject class
class RealSubject {
    request() {
        return 'RealSubject: Handling request';
    }
}

// Proxy class
class Proxy {
    constructor(realSubject) {
        this.realSubject = realSubject;
    }

    request() {
        console.log('Proxy: Logging request');
        return this.realSubject.request();
    }
}

// Example usage
const realSubject = new RealSubject();

const proxy = new Proxy(realSubject);
console.log(proxy.request()); // Output: Proxy: Logging request
```

## Command Pattern
The command pattern is a design pattern that encapsulates a request as an object, allowing you to parameterize clients with different requests, queue or log requests, and support undoable operations. It decouples the sender of a request from the receiver, enabling more flexible and extensible designs.

### Example of Command Pattern
```javascript
// Command interface
class Command {
    execute() {
        throw new Error('Command.execute() must be implemented');
    }
}

// Concrete command classes
class LightOnCommand extends Command {
    constructor(light) {
        super();
        this.light = light;
    }

    execute() {
        this.light.turnOn();
    }
}

class LightOffCommand extends Command {
    constructor(light) {
        super();
        this.light = light;
    }

    execute() {
        this.light.turnOff();
    }
}

// Receiver class
class Light {
    turnOn() {
        console.log('Light is ON');
    }

    turnOff() {
        console.log('Light is OFF');
    }
}

// Invoker class
class RemoteControl {
    constructor() {
        this.command = null;
    }

    setCommand(command) {
        this.command = command;
    }

    pressButton() {
        if (this.command) {
            this.command.execute();
        }
    }
}

// Example usage
const light = new Light();

const lightOnCommand = new LightOnCommand(light);
const lightOffCommand = new LightOffCommand(light);

const remoteControl = new RemoteControl();
remoteControl.setCommand(lightOnCommand);

remoteControl.pressButton(); // Output: Light is ON
remoteControl.setCommand(lightOffCommand);

remoteControl.pressButton(); // Output: Light is OFF
```

## Dependency Injection 
The dependency injection pattern is a design pattern that allows you to inject dependencies into a class or function rather than creating them internally. It promotes loose coupling between components, making it easier to test, maintain, and extend the code. Dependency injection can be implemented using constructor injection, setter injection, or interface injection.

### Example of Dependency Injection
```javascript
// Service class
class Logger {
    log(message) {
        console.log('Log:', message);
    }
}

// Consumer class that depends on the Logger service
class UserService {
    constructor(logger) {
        this.logger = logger; // Injecting the Logger dependency
    }

    createUser(username) {
        // Perform user creation logic
        this.logger.log(`User created: ${username}`);
    }
}

// Example usage
const logger = new Logger();

const userService = new UserService(logger); // Injecting the Logger dependency
userService.createUser('Alice'); // Output: Log: User created: Alice
```

## Composition Pattern
The composition pattern is a design pattern that allows you to build complex objects by combining simpler objects or components. It promotes code reusability and flexibility by enabling you to create new functionality by composing existing objects rather than relying on inheritance. The composition pattern is often used in scenarios where you want to create objects with varying behaviors or features.

### Example of Composition Pattern
```javascript
// Component classes
class Engine {
    start() {
        console.log('Engine started');
    }
}

class Wheels {
    roll() {
        console.log('Wheels rolling');
    }
}

// Car class that composes Engine and Wheels
class Car {
    constructor(engine, wheels) {
        this.engine = engine;
        this.wheels = wheels;
    }

    drive() {
        this.engine.start();
        this.wheels.roll();
        console.log('Car is driving');
    }
}

// Example usage
const engine = new Engine();

const wheels = new Wheels();
const car = new Car(engine, wheels);
car.drive();
// Output:
// Engine started
// Wheels rolling
// Car is driving
```

# Testing JavaScript

## Why testing?
Testing is a crucial aspect of software development that ensures the quality, reliability, and maintainability of your code. It helps identify bugs, verify that your code behaves as expected, and provides confidence when making changes or adding new features. Testing can also improve code design by encouraging modularity and separation of concerns.

## Types of Testing
There are several types of testing that can be applied to JavaScript code, each serving a different purpose:
- Unit Testing: Focuses on testing individual functions or components in isolation to ensure they work correctly.
- Integration Testing: Tests how different components or modules work together, verifying that they interact correctly.
- End-to-End (E2E) Testing: Simulates real user interactions with the application, testing the entire system from start to finish.
- Performance Testing: Measures the performance and responsiveness of the application under various conditions, ensuring it meets performance requirements.
- Security Testing: Identifies vulnerabilities and ensures that the application is secure against potential threats and attacks.

### Testing Frameworks
There are several popular testing frameworks available for JavaScript, each with its own features and capabilities.
- Jest: A comprehensive testing framework developed by Facebook, known for its simplicity and ease of use. It provides built-in support for mocking, snapshot testing, and code coverage.
- Mocha: A flexible testing framework that allows you to write tests in a variety of styles. It is often used in combination with assertion libraries like Chai for more expressive assertions.
- Jasmine: A behavior-driven development (BDD) framework that provides a clean syntax for writing tests. It includes built-in assertions and supports asynchronous testing.
- QUnit: A powerful testing framework primarily used for testing jQuery applications. It provides a simple API for writing tests and supports asynchronous testing.
- Ava: A minimalistic testing framework that focuses on speed and simplicity. It runs tests concurrently, making it suitable for large test suites.

## Example of Unit Testing with Jest
```javascript
// sum.js (function to be tested)
function sum(a, b) {
    return a + b;
}

// sum.test.js (unit test for the sum function)
const sum = require('./sum');

test('adds 1 + 2 to equal 3', () => {
    expect(sum(1, 2)).toBe(3);
});

test('adds -1 + 1 to equal 0', () => {
    expect(sum(-1, 1)).toBe(0);
});

test('adds 0 + 0 to equal 0', () => {
    expect(sum(0, 0)).toBe(0);
});
```

## Example of Integration Testing with Mocha and Chai
```javascript
// userService.js (module to be tested)
class UserService {
    constructor(database) {
        this.database = database;
    }

    createUser(username) {
        if (!username) {
            throw new Error('Username is required');
        }
        return this.database.save({ username });
    }

    getUser(id) {
        return this.database.findById(id);
    }
}

// userService.test.js (integration test for UserService)
const chai = require('chai');
const expect = chai.expect;
const sinon = require('sinon');
const UserService = require('./userService');

describe('UserService', () => {
    let databaseMock;
    let userService;

    beforeEach(() => {
        databaseMock = {
            save: sinon.stub(),
            findById: sinon.stub()
        };
        userService = new UserService(databaseMock);
    });

    it('should create a user with a valid username', () => {
        const username = 'Alice';
        databaseMock.save.returns({ id: 1, username });

        const result = userService.createUser(username);

        expect(result).to.deep.equal({ id: 1, username });
        expect(databaseMock.save.calledOnce).to.be.true;
    });

    it('should throw an error when creating a user without a username', () => {
        expect(() => userService.createUser()).to.throw('Username is required');
    });

    it('should retrieve a user by ID', () => {
        const userId = 1;
        const user = { id: userId, username: 'Alice' };
        databaseMock.findById.withArgs(userId).returns(user);

        const result = userService.getUser(userId);

        expect(result).to.deep.equal(user);
        expect(databaseMock.findById.calledOnceWith(userId)).to.be.true;
    });
});
```
## Unit testing
Unit testing is a software testing technique that focuses on testing individual units or components of a software application in isolation. The goal of unit testing is to verify that each unit of code, such as a function or method, behaves as expected and produces the correct output for a given input. Unit tests are typically automated and can be run frequently during development to catch bugs early and ensure code quality.

## Example of Unit Testing with Jest
```javascript
// math.js (function to be tested)
function add(a, b) {
    return a + b;
}

// math.test.js (unit test for the add function)
const add = require('./math');

test('adds 1 + 2 to equal 3', () => {
    expect(add(1, 2)).toBe(3);
});

test('adds -1 + 1 to equal 0', () => {
    expect(add(-1, 1)).toBe(0);
});

test('adds 0 + 0 to equal 0', () => {
    expect(add(0, 0)).toBe(0);
});
```

### Example of Unit Testing with Mocha and Chai
```javascript
// calculator.js (function to be tested)
function multiply(a, b) {
    return a * b;
}

// calculator.test.js (unit test for the multiply function)
const chai = require('chai');
const expect = chai.expect;
const multiply = require('./calculator');

describe('multiply', () => {
    it('should multiply 2 and 3 to equal 6', () => {
        expect(multiply(2, 3)).to.equal(6);
    });

    it('should multiply -1 and 5 to equal -5', () => {
        expect(multiply(-1, 5)).to.equal(-5);
    });

    it('should multiply 0 and any number to equal 0', () => {
        expect(multiply(0, 10)).to.equal(0);
        expect(multiply(10, 0)).to.equal(0);
    });
});
```

## Integration testing
Integration testing is a software testing technique that focuses on verifying the interactions and integration between different components or modules of a software application. The goal of integration testing is to ensure that the individual units work together as expected and that data flows correctly between them. Integration tests are typically performed after unit tests and can be automated or manual, depending on the complexity of the system.

### Example of Integration Testing with Mocha and Chai
```javascript
// userService.js (module to be tested)
class UserService {
    constructor(database) {
        this.database = database;
    }

    createUser(username) {
        if (!username) {
            throw new Error('Username is required');
        }
        return this.database.save({ username });
    }

    getUser(id) {
        return this.database.findById(id);
    }
}

// userService.test.js (integration test for UserService)
const chai = require('chai');
const expect = chai.expect;
const sinon = require('sinon');
const UserService = require('./userService');

describe('UserService', () => {
    let databaseMock;
    let userService;

    beforeEach(() => {
        databaseMock = {
            save: sinon.stub(),
            findById: sinon.stub()
        };
        userService = new UserService(databaseMock);
    });

    it('should create a user with a valid username', () => {
        const username = 'Alice';
        databaseMock.save.returns({ id: 1, username });

        const result = userService.createUser(username);

        expect(result).to.deep.equal({ id: 1, username });
        expect(databaseMock.save.calledOnce).to.be.true;
    });

    it('should throw an error when creating a user without a username', () => {
        expect(() => userService.createUser()).to.throw('Username is required');
    });

    it('should retrieve a user by ID', () => {
        const userId = 1;
        const user = { id: userId, username: 'Alice' };
        databaseMock.findById.withArgs(userId).returns(user);

        const result = userService.getUser(userId);

        expect(result).to.deep.equal(user);
        expect(databaseMock.findById.calledOnceWith(userId)).to.be.true;
    });
});
```

## End-to-End (E2E) testing
End-to-End (E2E) testing is a software testing technique that focuses on verifying the entire flow of an application from start to finish, simulating real user interactions. The goal of E2E testing is to ensure that all components of the application work together as expected and that the system behaves correctly under various scenarios. E2E tests are typically automated and can be run in a browser or headless environment.   

### Example of End-to-End Testing with Cypress
```javascript
// cypress/integration/sample_spec.js
describe('My First Test', () => {
    it('Visits the Kitchen Sink', () => {
        cy.visit('https://example.cypress.io');
        cy.contains('type').click();
        cy.url().should('include', '/commands/actions');
        cy.get('.action-email').type('').should('have.value', '');
    });

    it('Fills out a form', () => {
        cy.visit('https://example.cypress.io/commands/actions');
        cy.get('.action-form').within(() => {
            cy.get('input[name="name"]').type('John Doe');
            cy.get('input[name="email"]').type('');
            cy.get('form').submit();
            cy.get('.action-form').should('contain', 'Form submitted');
        });
    });
});
```

## Test cases
Test cases are specific scenarios or conditions that are used to verify the functionality of a software application. Each test case includes a set of inputs, execution steps, and expected outcomes. Test cases help ensure that the application behaves as expected under various conditions and edge cases. They can be written for unit tests, integration tests, and end-to-end tests.

### Example of Test Cases
```javascript
// Test case for the add function
describe('add function', () => {
    it('should return 3 when adding 1 and 2', () => {
        const result = add(1, 2);
        expect(result).toBe(3);
    });

    it('should return 0 when adding -1 and 1', () => {
        const result = add(-1, 1);
        expect(result).toBe(0);
    });

    it('should return 0 when adding 0 and 0', () => {
        const result = add(0, 0);
        expect(result).toBe(0);
    });
});
```

## Assertions
Assertions are statements in test cases that verify whether a specific condition is true or false. They are used to compare the actual output of a function or component with the expected output. If the assertion fails, it indicates that there is a discrepancy between the actual and expected results, which may point to a bug or issue in the code. Assertions are an essential part of testing frameworks and help ensure that the application behaves as intended.

### Example of Assertions with Jest
```javascript
// Example of assertions with Jest
test('adds 1 + 2 to equal 3', () => {
    expect(add(1, 2)).toBe(3); // Assertion: actual output should equal expected output
});

// Example of assertions with Chai
const chai = require('chai');
const expect = chai.expect;

describe('multiply function', () => {
    it('should multiply 2 and 3 to equal 6', () => {
        expect(multiply(2, 3)).to.equal(6); // Assertion: actual output should equal expected output
    });
});
```

## Mocking
Mocking is a technique used in testing to create simulated versions of objects, functions, or modules that mimic the behavior of real dependencies. Mocking allows you to isolate the unit of code being tested by replacing its dependencies with controlled, predictable versions. This helps ensure that tests are focused on the specific functionality being tested and are not affected by external factors or side effects.

### Example of Mocking with Jest
```javascript
// Example of mocking with Jest
const fetchData = require('./fetchData'); // Function that makes an API call

jest.mock('./fetchData'); // Mock the fetchData module

test('fetchData returns expected data', async () => {
    const mockData = { id: 1, name: 'John Doe' };
    fetchData.mockResolvedValue(mockData); // Mock the resolved value of fetchData

    const result = await fetchData();
    expect(result).toEqual(mockData); // Assertion: actual output should equal expected output
});
```

### Example of Mocking with Sinon
```javascript
// Example of mocking with Sinon
const sinon = require('sinon');
const database = require('./database'); // Module that interacts with the database

describe('UserService', () => {
    let databaseMock;
    let userService;

    beforeEach(() => {
        databaseMock = sinon.mock(database); // Create a mock for the database module
        userService = new UserService(databaseMock.object); // Inject the mock into UserService
    });

    afterEach(() => {
        databaseMock.restore(); // Restore the original database module after each test
    });

    it('should create a user with a valid username', () => {
        const username = 'Alice';
        const expectedUser = { id: 1, username };

        databaseMock.expects('save').once().withArgs({ username }).returns(expectedUser); // Set up expectation for the save method

        const result = userService.createUser(username);

        expect(result).to.deep.equal(expectedUser); // Assertion: actual output should equal expected output
        databaseMock.verify(); // Verify that the expectations were met
    });
});
```

## Spying
Spying is a technique used in testing to monitor and record the behavior of functions or methods during test execution. A spy allows you to track how many times a function was called, what arguments were passed to it, and what values it returned. Spying is useful for verifying that certain functions are called as expected and for ensuring that the interactions between components are correct.

### Example of Spying with Jest
```javascript
// Example of spying with Jest
const myModule = require('./myModule'); // Module containing the function to be spied on 

test('should call the function with correct arguments', () => {
    const spy = jest.spyOn(myModule, 'myFunction'); // Create a spy on the myFunction method

    myModule.myFunction('arg1', 'arg2'); // Call the function with arguments

    expect(spy).toHaveBeenCalledWith('arg1', 'arg2'); // Assertion: verify that the function was called with the correct arguments
    spy.mockRestore(); // Restore the original function after the test

    const privateSpy = jest.spyOn(myModule, 'privateMethod', 'get'); // Create a spy on the privateMethod getter
    myModule.privateMethod; // Access the private method
    expect(privateSpy).toHaveBeenCalled(); // Assertion: verify that the private method was accessed
    privateSpy.mockRestore(); // Restore the original private method after the test
});
```

## Example of Spying with Sinon
```javascript
// Example of spying with Sinon
const sinon = require('sinon');
const myModule = require('./myModule'); // Module containing the function to be spied on

describe('myModule', () => {
    let spy;

    beforeEach(() => {
        spy = sinon.spy(myModule, 'myFunction'); // Create a spy on the myFunction method
    });

    afterEach(() => {
        spy.restore(); // Restore the original function after each test
    });

    it('should call the function with correct arguments', () => {
        myModule.myFunction('arg1', 'arg2'); // Call the function with arguments

        sinon.assert.calledWith(spy, 'arg1', 'arg2'); // Assertion: verify that the function was called with the correct arguments
    });
});
```

## Stubbing
Stubbing is a technique used in testing to replace a function or method with a controlled implementation that returns predefined values. Stubs allow you to isolate the unit of code being tested by providing predictable behavior for its dependencies. This helps ensure that tests are focused on the specific functionality being tested and are not affected by external factors or side effects.

### Example of Stubbing with Jest
```javascript
// Example of stubbing with Jest
const myModule = require('./myModule'); // Module containing the function to be stubbed

test('should return expected value from stubbed function', () => {
    const stub = jest.spyOn(myModule, 'myFunction').mockReturnValue('stubbed value'); // Create a stub for the myFunction method

    const result = myModule.myFunction(); // Call the stubbed function

    expect(result).toBe('stubbed value'); // Assertion: verify that the stubbed function returns the expected value
    stub.mockRestore(); // Restore the original function after the test
});
```

## Code Coverage
Code coverage is a measure of how much of your code is executed during testing. It helps identify untested parts of your codebase and provides insights into the effectiveness of your test suite. Code coverage can be measured at different levels, including function coverage, statement coverage, branch coverage, and path coverage. Higher code coverage generally indicates better test quality, but it does not guarantee that all edge cases are tested.

### Example of Code Coverage with Jest
```javascript
// Example of code coverage with Jest
// To enable code coverage in Jest, you can run the following command:
// jest --coverage

// Jest will generate a coverage report that shows the percentage of code covered by tests, including function coverage, statement coverage, branch coverage, and path coverage. The report will also highlight untested lines of code, allowing you to identify areas that need additional testing.
```
## Jest
Jest is a popular JavaScript testing framework developed by Facebook. It is widely used for testing React applications but can also be used for testing any JavaScript code. Jest provides a simple and intuitive API for writing tests, along with built-in features such as mocking, snapshot testing, and code coverage analysis. It is known for its speed, ease of use, and excellent developer experience.

### Example of Jest Test
```javascript
// sum.js (function to be tested)
function sum(a, b) {
    return a + b;
}

// sum.test.js (unit test for the sum function)
const sum = require('./sum');

test('adds 1 + 2 to equal 3', () => {
    expect(sum(1, 2)).toBe(3);
});

test('adds -1 + 1 to equal 0', () => {
    expect(sum(-1, 1)).toBe(0);
});

test('adds 0 + 0 to equal 0', () => {
    expect(sum(0, 0)).toBe(0);
});
```

## Vitest
Vitest is a modern JavaScript testing framework that is designed to be fast, lightweight, and easy to use. It is built on top of Vite, a fast build tool for modern web development, and provides a seamless testing experience for Vite projects. Vitest supports features such as hot module replacement (HMR), snapshot testing, and code coverage analysis. It is particularly well-suited for testing Vue.js applications but can also be used for testing any JavaScript code.

### Example of Vitest Test
```javascript
// sum.js (function to be tested)
export function sum(a, b) {
    return a + b;
}

// sum.test.js (unit test for the sum function)
import { describe, it, expect } from 'vitest';

describe('sum function', () => {
    it('adds 1 + 2 to equal 3', () => {
        expect(sum(1, 2)).toBe(3);
    });

    it('adds -1 + 1 to equal 0', () => {
        expect(sum(-1, 1)).toBe(0);
    });

    it('adds 0 + 0 to equal 0', () => {
        expect(sum(0, 0)).toBe(0);
    });
});
```

## Playwright/Cypress concepts
playwright and Cypress are both popular end-to-end (E2E) testing frameworks for web applications. They allow developers to write automated tests that simulate real user interactions with the application, ensuring that it behaves correctly under various scenarios. Both frameworks provide powerful APIs for interacting with web elements, handling asynchronous operations, and asserting expected outcomes.

### Playwright
Playwright is a Node.js library developed by Microsoft that enables developers to automate browser interactions for testing web applications. It supports multiple browsers (Chromium, Firefox, and WebKit) and provides a rich set of features for writing E2E tests, including handling network requests, taking screenshots, and generating test reports. Playwright is known for its speed, reliability, and ability to run tests in parallel.

### Example of Playwright Test
```javascript
// playwright.config.js (Playwright configuration file)
import { defineConfig } from '@playwright/test';

export default defineConfig({
    use: {
        headless: true, // Run tests in headless mode
        viewport: { width: 1280, height: 720 }, // Set the viewport size
        ignoreHTTPSErrors: true, // Ignore HTTPS errors
    },
});

// example.spec.js (Playwright test file)
import { test, expect } from '@playwright/test';

test('should load the homepage and check the title', async ({ page }) => {
    await page.goto('https://example.com'); // Navigate to the homepage
    const title = await page.title(); // Get the page title
    expect(title).toBe('Example Domain'); // Assert that the title is as expected
});
```

### Cypress
Cypress is a JavaScript-based end-to-end testing framework that provides a complete testing solution for web applications. It runs directly in the browser, allowing developers to see the tests as they execute and providing real-time feedback. Cypress offers a simple and intuitive API for writing tests, along with features such as time travel debugging, automatic waiting, and network request stubbing. It is particularly well-suited for testing modern web applications built with frameworks like React, Angular, and Vue.js.

### Example of Cypress Test
```javascript
// cypress.config.js (Cypress configuration file)
const { defineConfig } = require('cypress');

module.exports = defineConfig({
    e2e: {
        baseUrl: 'https://example.com', // Set the base URL for tests
        viewportWidth: 1280, // Set the viewport width
        viewportHeight: 720, // Set the viewport height
    },
});

// example.spec.js (Cypress test file)
describe('Homepage', () => {
    it('should load the homepage and check the title', () => {
        cy.visit('/'); // Navigate to the homepage
        cy.title().should('eq', 'Example Domain'); // Assert that the title is as expected
    });
});
```

# Debugging

## Browser DevTools
Browser DevTools are built-in developer tools provided by modern web browsers that allow developers to inspect, debug, and analyze web applications. They provide a wide range of features for debugging JavaScript code, inspecting HTML and CSS, monitoring network requests, and profiling performance. Browser DevTools are essential for identifying and fixing issues in web applications during development.

### Example of Using Browser DevTools
1. Open the browser and navigate to the web application you want to debug.
2. Right-click on the page and select "Inspect" or press `Ctrl+Shift+I` (Windows/Linux) or `Cmd+Option+I` (Mac) to open the DevTools panel.
3. Use the "Elements" tab to inspect and modify the HTML and CSS of the page.
4. Use the "Console" tab to view log messages, run JavaScript code, and debug errors.
5. Use the "Sources" tab to set breakpoints, step through code, and inspect variables during execution.

## Console
The console is a powerful tool in browser DevTools that allows developers to log messages, run JavaScript code, and debug errors. It provides a way to interact with the web application in real-time, making it easier to identify issues and test code snippets. The console can be used to log information, display error messages, and execute JavaScript commands directly in the context of the web page.

### Example of Using the Console
1. Open the browser and navigate to the web application you want to debug.
2. Open the DevTools panel by right-clicking on the page and selecting "Inspect" or pressing `Ctrl+Shift+I` (Windows/Linux) or `Cmd+Option+I` (Mac).
3. Click on the "Console" tab to access the console.
4. Use `console.log()` to log messages or variables for debugging purposes. For example:
```javascript
console.log('Debugging message:', myVariable);
```
5. Use `console.error()` to log error messages:
```javascript
console.error('An error occurred:', error);
```

## Breakpoints
Breakpoints are a debugging feature that allows developers to pause the execution of JavaScript code at specific lines or conditions. When a breakpoint is hit, the code execution stops, allowing developers to inspect the current state of variables, evaluate expressions, and step through the code line by line. Breakpoints are essential for identifying and fixing issues in complex code.

### Example of Using Breakpoints
1. Open the browser and navigate to the web application you want to debug.
2. Open the DevTools panel by right-clicking on the page and selecting "Inspect" or pressing `Ctrl+Shift+I` (Windows/Linux) or `Cmd+Option+I` (Mac).
3. Click on the "Sources" tab to access the source code of the application.
4. Locate the JavaScript file you want to debug and click on the line number where you want to set a breakpoint. A blue marker will appear, indicating that a breakpoint has been set.
5. Reload the page or trigger the code execution that reaches the breakpoint. The execution will pause at the breakpoint, allowing you to inspect variables and step through the code.

## Conditional Breakpoints
Conditional breakpoints are a type of breakpoint that allows developers to pause the execution of JavaScript code only when a specific condition is met. This feature is useful for debugging scenarios where you want to stop execution based on certain variable values or states, rather than pausing at every occurrence of a line of code. Conditional breakpoints help reduce noise and focus on relevant issues during debugging.

### Example of Using Conditional Breakpoints
1. Open the browser and navigate to the web application you want to debug.
2. Open the DevTools panel by right-clicking on the page and selecting "Inspect" or pressing `Ctrl+Shift+I` (Windows/Linux) or `Cmd+Option+I` (Mac).
3. Click on the "Sources" tab to access the source code of the application.
4. Locate the JavaScript file you want to debug and click on the line number where you want to set a conditional breakpoint. A blue marker will appear, indicating that a breakpoint has been set.
5. Right-click on the blue marker and select "Edit breakpoint" or "Add condition" (depending on the browser). Enter the condition that must be met for the breakpoint to trigger. For example:
```javascript
myVariable === 10
```
6. Reload the page or trigger the code execution that reaches the conditional breakpoint. The execution will pause only when the specified condition is true, allowing you to inspect variables and step through the code.

## Watch expressions
Watch expressions are a debugging feature that allows developers to monitor the values of specific variables or expressions during code execution. By adding watch expressions, you can track how the values change over time, making it easier to identify issues and understand the behavior of your code. Watch expressions are particularly useful when debugging complex logic or when you want to observe the state of certain variables without manually inspecting them at each breakpoint.

### Example of Using Watch Expressions
1. Open the browser and navigate to the web application you want to debug.
2. Open the DevTools panel by right-clicking on the page and selecting "Inspect" or pressing `Ctrl+Shift+I` (Windows/Linux) or `Cmd+Option+I` (Mac).
3. Click on the "Sources" tab to access the source code of the application.
4. Set a breakpoint in the code where you want to start monitoring variables.
5. In the "Watch" panel (usually located on the right side of the DevTools), click on the "+" button to add a new watch expression.

## Call stack inspection
Call stack inspection is a debugging feature that allows developers to view the sequence of function calls that led to the current point of execution in the code. The call stack provides valuable information about the flow of the program, helping developers understand how they arrived at a specific line of code and identify potential issues in the call hierarchy. By inspecting the call stack, you can trace back through the function calls and analyze the context in which a particular piece of code is executed.

### Example of Call Stack Inspection
1. Open the browser and navigate to the web application you want to debug.
2. Open the DevTools panel by right-clicking on the page and selecting "Inspect" or pressing `Ctrl+Shift+I` (Windows/Linux) or `Cmd+Option+I` (Mac).
3. Click on the "Sources" tab to access the source code of the application.
4. Set a breakpoint in the code where you want to inspect the call stack.
5. Reload the page or trigger the code execution that reaches the breakpoint. The execution will pause at the breakpoint.
6. In the "Call Stack" panel (usually located on the right side of the DevTools), you will see a list of function calls that led to the current point of execution. Each entry in the call stack represents a function call, with the most recent call at the top.

## Network tab
The Network tab in browser DevTools is a powerful tool that allows developers to monitor and analyze network requests made by a web application. It provides detailed information about each request, including the request URL, HTTP method, status code, response time, and response data. The Network tab is essential for debugging issues related to API calls, resource loading, and performance optimization.

### Example of Using the Network Tab
1. Open the browser and navigate to the web application you want to debug.
2. Open the DevTools panel by right-clicking on the page and selecting "Inspect" or pressing `Ctrl+Shift+I` (Windows/Linux) or `Cmd+Option+I` (Mac).
3. Click on the "Network" tab to access the network monitoring tools.
4. Reload the page or perform actions in the application that trigger network requests. The Network tab will display a list of all network requests made by the application, including their details.
5. Click on a specific request to view more information, such as request headers, response headers, and response data. You can also inspect the timing of the request to analyze performance and identify potential bottlenecks.

## Sources tab
The Sources tab in browser DevTools is a powerful tool that allows developers to view, edit, and debug the source code of a web application. It provides access to the JavaScript, HTML, and CSS files that make up the application, enabling developers to set breakpoints, step through code, and inspect variables during execution. The Sources tab is essential for identifying and fixing issues in the codebase.

### Example of Using the Sources Tab
1. Open the browser and navigate to the web application you want to debug.
2. Open the DevTools panel by right-clicking on the page and selecting "Inspect" or pressing `Ctrl+Shift+I` (Windows/Linux) or `Cmd+Option+I` (Mac).
3. Click on the "Sources" tab to access the source code of the application.
4. In the left panel, you will see a file navigator that lists all the source files of the application. You can expand folders and click on files to view their contents in the main panel.
5. To set a breakpoint, click on the line number where you want to pause execution.

## Performance tab
The Performance tab in browser DevTools is a powerful tool that allows developers to analyze the performance of a web application. It provides detailed insights into how the application behaves during runtime, including information about rendering, scripting, and network activity. The Performance tab is essential for identifying performance bottlenecks, optimizing code, and ensuring a smooth user experience.

### Example of Using the Performance Tab
1. Open the browser and navigate to the web application you want to analyze.
2. Open the DevTools panel by right-clicking on the page and selecting "Inspect" or pressing `Ctrl+Shift+I` (Windows/Linux) or `Cmd+Option+I` (Mac).
3. Click on the "Performance" tab to access the performance analysis tools.
4. Click on the "Record" button (usually a circular icon) to start recording the performance of the application.
5. Interact with the application by performing actions that you want to analyze, such as clicking buttons, navigating pages, or loading data.

## Memory tab
The Memory tab in browser DevTools is a powerful tool that allows developers to analyze the memory usage of a web application. It provides insights into how memory is allocated and used by the application, helping developers identify memory leaks, optimize memory usage, and improve overall performance. The Memory tab is essential for ensuring that the application runs efficiently and does not consume excessive resources.

### Example of Using the Memory Tab
1. Open the browser and navigate to the web application you want to analyze.
2. Open the DevTools panel by right-clicking on the page and selecting "Inspect" or pressing `Ctrl+Shift+I` (Windows/Linux) or `Cmd+Option+I` (Mac).
3. Click on the "Memory" tab to access the memory analysis tools.
4. You will see three main options for analyzing memory: "Heap snapshot," "Allocation instrumentation on timeline," and "Allocation sampling." Choose the appropriate option based on your analysis needs.
5. For example, to take a heap snapshot, click on the "Heap snapshot" option and then click the "Take snapshot" button. This will capture the current state of memory usage in the application.

## Debugging async code
Debugging asynchronous code can be challenging due to the nature of asynchronous operations, such as callbacks, promises, and async/await. However, modern debugging tools and techniques can help developers effectively debug async code. Here are some strategies for debugging asynchronous code:
1. Use breakpoints: Set breakpoints in your async functions to pause execution and inspect variables at specific points in the code. This allows you to analyze the state of the application during async operations.
2. Use console.log: Insert console.log statements in your async code to log the values of variables and track the flow of execution. This can help you identify where issues may be occurring.
3. Use async/await: When working with promises, consider using async/await syntax to make the code more readable and easier to debug. This allows you to write asynchronous code in a synchronous style, making it easier to follow the flow of execution.
4. Use debugging tools: Modern browsers provide powerful debugging tools that can help you debug async code. For example, you can use the "Sources" tab in Chrome DevTools to set breakpoints, step through code, and inspect variables during async operations.

## Reading stack traces
Reading stack traces is an essential skill for debugging JavaScript applications. A stack trace provides a snapshot of the call stack at the point where an error occurred, showing the sequence of function calls that led to the error. By analyzing the stack trace, developers can identify the source of the error and understand how it propagated through the code.

### Example of Reading a Stack Trace
1. When an error occurs in your JavaScript code, the browser will typically display an error message in the console, along with a stack trace. The stack trace will show the sequence of function calls that led to the error, starting from the most recent call at the top.
2. Each entry in the stack trace includes the function name, the file name, and the line number where the function was called. For example:
```
TypeError: Cannot read property 'foo' of undefined
    at myFunction (script.js:10)
    at anotherFunction (script.js:20)
    at main (script.js:30)
```
3. To read the stack trace, start from the top entry and work your way down. The top entry indicates where the error occurred, while the subsequent entries show the functions that were called leading up to the error.
4. Use the file name and line number information to locate the relevant code in your source files. This will help you understand the context of the error and identify potential issues in your code.

## Common JavaScript errors
1. SyntaxError: This error occurs when there is a mistake in the syntax of your JavaScript code, such as a missing parenthesis or an unexpected token. It prevents the code from being parsed and executed correctly.
2. ReferenceError: This error occurs when you try to access a variable or function that has not been declared or is out of scope. It indicates that the reference to the variable or function is invalid.
3. TypeError: This error occurs when you try to perform an operation on a value of the wrong type, such as calling a method on a non-object or trying to access a property of undefined. It indicates that the value does not support the operation being performed.
4. RangeError: This error occurs when a value is outside the allowable range, such as passing an invalid index to an array or using a number that is too large or too small for a specific operation.
5. EvalError: This error occurs when there is an issue with the eval() function, which is used to evaluate JavaScript code represented as a string. It indicates that the eval() function was used incorrectly or in an unsupported context.

# Advanced JavaScript Topics

## Symbols
Symbols are a unique and immutable primitive data type introduced in ECMAScript 2015 (ES6). They are often used as unique property keys in objects, allowing developers to create properties that do not conflict with other properties or methods. Symbols can be created using the `Symbol()` function, and each symbol is guaranteed to be unique.

### Example of Using Symbols
```javascript
// Creating a symbol
const mySymbol = Symbol('mySymbol');

// Using the symbol as a property key in an object
const myObject = {
    [mySymbol]: 'This is a symbol property'
};

// Accessing the symbol property
console.log(myObject[mySymbol]); // Output: This is a symbol property
```

## Proxy
Proxy is a built-in JavaScript object that allows developers to create a wrapper around another object or function, intercepting and customizing its behavior. Proxies can be used to define custom behavior for fundamental operations such as property access, assignment, enumeration, and function invocation. This makes them a powerful tool for creating dynamic and flexible objects.

### Example of Using Proxy
```javascript
// Creating a target object
const target = {
    name: 'John Doe',
    age: 30
};

// Creating a proxy to intercept property access
const handler = {
    get: function(target, property) {
        if (property in target) {
            return target[property];
        } else {
            return `Property "${property}" does not exist.`;
        }
    }
};

// Creating a proxy object
const proxy = new Proxy(target, handler);

// Accessing properties through the proxy
console.log(proxy.name); // Output: John Doe

console.log(proxy.age); // Output: 30

console.log(proxy.gender); // Output: Property "gender" does not exist.
```

## Reflect
Reflect is a built-in JavaScript object that provides methods for interceptable JavaScript operations. It is part of the ECMAScript 2015 (ES6) specification and is designed to complement the Proxy object. Reflect allows developers to perform operations such as property access, assignment, and function invocation in a more functional and consistent manner. It provides a set of static methods that can be used to manipulate objects and their properties.

### Example of Using Reflect
```javascript
// Creating a target object
const target = {
    name: 'John Doe',
    age: 30
};

// Using Reflect to get a property value
const name = Reflect.get(target, 'name');
console.log(name); // Output: John Doe

// Using Reflect to set a property value
Reflect.set(target, 'age', 31);
console.log(target.age); // Output: 31

// Using Reflect to check if a property exists
const hasName = Reflect.has(target, 'name');
console.log(hasName); // Output: true

// Using Reflect to delete a property
Reflect.deleteProperty(target, 'age');
console.log(target.age); // Output: undefined
```

## WeakRef
WeakRef is a built-in JavaScript object that allows developers to create weak references to objects. A weak reference does not prevent the referenced object from being garbage collected, meaning that if there are no strong references to the object, it can be automatically removed from memory. WeakRef is useful for managing memory in scenarios where you want to hold a reference to an object without preventing it from being garbage collected.

### Example of Using WeakRef
```javascript
// Creating an object
let myObject = { name: 'John Doe' };

// Creating a weak reference to the object
const weakRef = new WeakRef(myObject);

// Accessing the object through the weak reference
console.log(weakRef.deref()); // Output: { name: 'John Doe' }

// Removing the strong reference to the object
myObject = null;

// The object may be garbage collected, and the weak reference may return undefined
console.log(weakRef.deref()); // Output: undefined (if the object has been garbage collected)
```

## FinalizationRegistry
FinalizationRegistry is a built-in JavaScript object that allows developers to register cleanup callbacks for objects that are about to be garbage collected. It provides a way to perform cleanup operations or release resources associated with an object when it is no longer reachable. FinalizationRegistry is useful for managing resources and ensuring that they are properly released when objects are no longer needed.

### Example of Using FinalizationRegistry
```javascript
// Creating a finalization registry
const registry = new FinalizationRegistry((heldValue) => {
    console.log(`Object with held value "${heldValue}" has been garbage collected.`);
});

// Creating an object
let myObject = { name: 'John Doe' };

// Registering the object with the finalization registry
registry.register(myObject, 'myObject');

// Removing the strong reference to the object
myObject = null;

// The cleanup callback will be called when the object is garbage collected
// Note: The timing of garbage collection is non-deterministic, so the callback may not be called immediately.
```

## BigInt
BigInt is a built-in JavaScript object that provides a way to represent and manipulate integers larger than the maximum safe integer limit for the Number type (2^53 - 1). BigInt allows developers to work with arbitrarily large integers without losing precision. It is created by appending an "n" to the end of an integer literal or by using the BigInt constructor.

### Example of Using BigInt
```javascript
// Creating BigInt values
const bigInt1 = 123456789012345678901234567890123456789n; // Using the "n" suffix
const bigInt2 = BigInt('123456789012345678901234567890123456789'); // Using the BigInt constructor

// Performing arithmetic operations with BigInt
const sum = bigInt1 + bigInt2;
console.log(sum); // Output: 246913578024691357802469135780246913578n

const product = bigInt1 * bigInt2;
console.log(product); // Output: 152415787532388367501905199875019052100n
```

## Tagged Template literals
Tagged template literals are a feature in JavaScript that allows developers to create custom string processing functions. They provide a way to define a function that can process template literals, allowing for advanced string manipulation, formatting, and interpolation. Tagged template literals are created by prefixing a template literal with a function name, which receives the template strings and values as arguments.

### Example of Using Tagged Template Literals
```javascript
// Creating a tagged template literal function
function tag(strings, ...values) {
    let result = '';
    for (let i = 0; i < strings.length; i++) {
        result += strings[i];
        if (i < values.length) {
            result += values[i];
        }
    }
    return result.toUpperCase(); // Custom processing: convert to uppercase
}

// Using the tagged template literal
const name = 'John';
const age = 30;
const message = tag`My name is ${name} and I am ${age} years old.`;
console.log(message); // Output: MY NAME IS JOHN AND I AM 30 YEARS OLD.
```

## Property descriptors
Property descriptors are objects that describe the attributes of a property in JavaScript. They provide information about how a property behaves, including whether it is writable, enumerable, configurable, and its value. Property descriptors can be used to define or modify properties on objects using methods like `Object.defineProperty()` and `Object.getOwnPropertyDescriptor()`.

### Example of Using Property Descriptors
```javascript
// Creating an object
const myObject = {};

// Defining a property with a property descriptor
Object.defineProperty(myObject, 'myProperty', {
    value: 42,
    writable: true,
    enumerable: true,
    configurable: true
});

// Accessing the property
console.log(myObject.myProperty); // Output: 42

// Getting the property descriptor
const descriptor = Object.getOwnPropertyDescriptor(myObject, 'myProperty');

console.log(descriptor);
// Output:
{
  value: 42,
  writable: true,
  enumerable: true,
  configurable: true
}
```

## Getters/Setters
Getters and setters are special methods in JavaScript that allow developers to define custom behavior for accessing and modifying object properties. Getters are used to retrieve the value of a property, while setters are used to set the value of a property. They provide a way to encapsulate logic and perform additional operations when getting or setting property values.

### Example of Using Getters and Setters
```javascript
// Creating an object with a getter and setter
const myObject = {
    _name: 'John Doe', // Private property

    // Getter for the name property
    get name() {
        return this._name;
    },

    // Setter for the name property
    set name(value) {
        if (typeof value === 'string' && value.trim() !== '') {
            this._name = value;
        } else {
            console.error('Invalid name value');
        }
    }
};

// Accessing the name property using the getter
console.log(myObject.name); // Output: John Doe

// Setting the name property using the setter
myObject.name = 'Jane Smith';

console.log(myObject.name); // Output: Jane Smith

// Attempting to set an invalid name value
myObject.name = ''; // Output: Invalid name value
```

## Enumerability
Enumerability is a property attribute in JavaScript that determines whether a property of an object can be enumerated in a `for...in` loop or returned by methods like `Object.keys()`. By default, properties created using object literals or the `Object.defineProperty()` method are enumerable. However, you can control the enumerability of a property by setting the `enumerable` attribute in its property descriptor.

### Example of Enumerability
```javascript
// Creating an object with enumerable and non-enumerable properties
const myObject = {};

// Defining an enumerable property
Object.defineProperty(myObject, 'enumerableProperty', {
    value: 'I am enumerable',
    enumerable: true
});

// Defining a non-enumerable property
Object.defineProperty(myObject, 'nonEnumerableProperty', {
    value: 'I am not enumerable',
    enumerable: false
});

// Enumerating properties using a for...in loop
for (const key in myObject) {
    console.log(key); // Output: enumerableProperty
}

// Getting all enumerable property keys using Object.keys()
const keys = Object.keys(myObject);

console.log(keys); // Output: ['enumerableProperty']
```

## Configurable properties
Configurable properties in JavaScript are properties of an object that can be modified or deleted. The `configurable` attribute in a property descriptor determines whether a property can be changed or removed from the object. If a property is configurable, you can change its attributes (such as writable, enumerable, or value) or delete it using the `delete` operator. If a property is not configurable, attempts to modify or delete it will fail.

### Example of Configurable Properties
```javascript
// Creating an object with a configurable property
const myObject = {};

// Defining a configurable property
Object.defineProperty(myObject, 'configurableProperty', {
    value: 'I am configurable',
    configurable: true
});

// Modifying the property descriptor of the configurable property
Object.defineProperty(myObject, 'configurableProperty', {
    value: 'I have been modified',
    writable: false,
    enumerable: true
});

// Accessing the modified property
console.log(myObject.configurableProperty); // Output: I have been modified

// Deleting the configurable property
delete myObject.configurableProperty;

console.log(myObject.configurableProperty); // Output: undefined
```

## Writable properties
Writable properties in JavaScript are properties of an object that can be modified or assigned new values. The `writable` attribute in a property descriptor determines whether a property can be changed. If a property is writable, you can assign a new value to it. If it is not writable, attempts to change its value will fail, and the property will remain unchanged.

### Example of Writable Properties
```javascript
// Creating an object with a writable property
const myObject = {};

// Defining a writable property
Object.defineProperty(myObject, 'writableProperty', {
    value: 'I am writable',
    writable: true
});

// Modifying the writable property
myObject.writableProperty = 'I have been modified';

console.log(myObject.writableProperty); // Output: I have been modified

// Defining a non-writable property
Object.defineProperty(myObject, 'nonWritableProperty', {
    value: 'I am not writable',
    writable: false
});

// Attempting to modify the non-writable property
myObject.nonWritableProperty = 'I cannot be modified';

console.log(myObject.nonWritableProperty); // Output: I am not writable
```

## Object.defineProperty()
`Object.defineProperty()` is a method in JavaScript that allows developers to define or modify properties on an object with specific attributes. It provides a way to create properties with custom behavior, such as controlling their enumerability, configurability, and writability. This method is useful for creating properties that have specific characteristics or for modifying existing properties on an object.

### Example of Using Object.defineProperty()
```javascript
// Creating an object
const myObject = {};

// Defining a property with specific attributes using Object.defineProperty()
Object.defineProperty(myObject, 'myProperty', {
    value: 42,
    writable: true,
    enumerable: true,
    configurable: true
});

// Accessing the property
console.log(myObject.myProperty); // Output: 42

// Modifying the property
myObject.myProperty = 100;

console.log(myObject.myProperty); // Output: 100

// Getting the property descriptor
const descriptor = Object.getOwnPropertyDescriptor(myObject, 'myProperty');

console.log(descriptor);
// Output:
{
  value: 100,
  writable: true,
  enumerable: true,
  configurable: true
}
```

## Object.getOwnPropertyDescriptor()
`Object.getOwnPropertyDescriptor()` is a method in JavaScript that allows developers to retrieve the property descriptor of a specific property on an object. The property descriptor provides information about the attributes of the property, such as its value, writability, enumerability, and configurability. This method is useful for inspecting the characteristics of properties and understanding how they behave.

### Example of Using Object.getOwnPropertyDescriptor()
```javascript
// Creating an object with a property
const myObject = {
    myProperty: 42
};

// Getting the property descriptor of the property using Object.getOwnPropertyDescriptor()

const descriptor = Object.getOwnPropertyDescriptor(myObject, 'myProperty');

console.log(descriptor);
// Output:
{
  value: 42,
  writable: true,
  enumerable: true,
  configurable: true
}
```

## Object.getOwnPropertyDescriptors()
`Object.getOwnPropertyDescriptors()` is a method in JavaScript that allows developers to retrieve the property descriptors of all own properties on an object. It returns an object containing the property descriptors for each property, providing information about their attributes such as value, writability, enumerability, and configurability. This method is useful for inspecting the characteristics of multiple properties at once.

### Example of Using Object.getOwnPropertyDescriptors()
```javascript
// Creating an object with multiple properties
const myObject = {
    property1: 42,
    property2: 'Hello',
    property3: true
};

// Getting the property descriptors of all own properties using Object.getOwnPropertyDescriptors()
const descriptors = Object.getOwnPropertyDescriptors(myObject);

console.log(descriptors);
// Output:
{
  property1: {
    value: 42,
    writable: true,
    enumerable: true,
    configurable: true
  },
  property2: {
    value: 'Hello',
    writable: true,
    enumerable: true,
    configurable: true
  },
  property3: {
    value: true,
    writable: true,
    enumerable: true,
    configurable: true
  }
}
```

## Metaprogramming
Metaprogramming is a programming technique that allows developers to write code that can manipulate or modify other code at runtime. In JavaScript, metaprogramming can be achieved using features such as Proxies, Reflect, and property descriptors. Metaprogramming enables developers to create more dynamic and flexible code by allowing them to intercept and customize the behavior of objects and functions.

### Example of Metaprogramming with Proxy
```javascript
// Creating a target object
const target = {
    name: 'John Doe',
    age: 30
};

// Creating a proxy to intercept property access and modification
const handler = {
    get: function(target, property) {
        if (property in target) {
            return target[property];
        } else {
            return `Property "${property}" does not exist.`;
        }
    },
    set: function(target, property, value) {
        if (typeof value === 'string' && value.trim() !== '') {
            target[property] = value;
            return true;
        } else {
            console.error(`Invalid value for property "${property}".`);
            return false;
        }
    }
};

// Creating a proxy object
const proxy = new Proxy(target, handler);

// Accessing properties through the proxy
console.log(proxy.name); // Output: John Doe

// Modifying properties through the proxy
proxy.age = 31;

console.log(proxy.age); // Output: 31

// Attempting to set an invalid value through the proxy
proxy.name = ''; // Output: Invalid value for property "name".
```

## Tail-call concepts
Tail-call optimization is a programming technique that allows certain types of function calls to be optimized by the JavaScript engine. A tail call occurs when a function calls another function as its last operation, allowing the current function's stack frame to be replaced with the new function's stack frame. This optimization can help reduce memory usage and prevent stack overflow errors in recursive functions.

### Example of Tail-Call Optimization
```javascript
// A simple recursive function that calculates the factorial of a number
function factorial(n, accumulator = 1) {
    if (n <= 1) {
        return accumulator;
    }
    return factorial(n - 1, n * accumulator); // Tail call
}

// Calling the factorial function
console.log(factorial(5)); // Output: 120

// Note: Tail-call optimization is not guaranteed in all JavaScript engines, and its support may vary.
```

## Structured cloning
Structured cloning is a technique in JavaScript that allows developers to create deep copies of complex objects, including objects with nested properties, arrays, and other data structures. It is useful for creating independent copies of objects without retaining references to the original object. Structured cloning can be achieved using the `structuredClone()` function, which is available in modern JavaScript environments.

### Example of Using Structured Cloning
```javascript
// Creating a complex object with nested properties
const originalObject = {
    name: 'John Doe',
    age: 30,
    address: {
        street: '123 Main St',
        city: 'Anytown',
        country: 'USA'
    },
    hobbies: ['reading', 'traveling', 'coding']
};

// Creating a deep copy of the original object using structured cloning
const clonedObject = structuredClone(originalObject);

// Modifying the cloned object
clonedObject.name = 'Jane Smith';

clonedObject.address.city = 'Othertown';

// Modifying the hobbies array in the cloned object
clonedObject.hobbies.push('painting');

// The original object remains unchanged
console.log(originalObject.name); // Output: John Doe

console.log(originalObject.address.city); // Output: Anytown

console.log(originalObject.hobbies); // Output: ['reading', 'traveling', 'coding']

// The cloned object reflects the changes made
console.log(clonedObject.name); // Output: Jane Smith

console.log(clonedObject.address.city); // Output: Othertown

console.log(clonedObject.hobbies); // Output: ['reading', 'traveling', 'coding', 'painting']
```

## Transferable Objects
Transferable objects are a feature in JavaScript that allows developers to transfer ownership of certain types of objects, such as ArrayBuffers, between different execution contexts (e.g., between the main thread and web workers) without copying the underlying data. This can improve performance and reduce memory usage when working with large data sets or binary data.

### Example of Using Transferable Objects
```javascript
// Creating an ArrayBuffer
const buffer = new ArrayBuffer(8);

// Creating a view of the ArrayBuffer
const view = new Uint8Array(buffer);

// Filling the view with data
for (let i = 0; i < view.length; i++) {
    view[i] = i * 2;
}

// Transferring the ArrayBuffer to a web worker
const worker = new Worker('worker.js');

// Sending the ArrayBuffer to the worker as a transferable object
worker.postMessage(buffer, [buffer]);

// In the worker.js file, you can receive the transferred ArrayBuffer
self.onmessage = function(event) {
    const receivedBuffer = event.data;
    const receivedView = new Uint8Array(receivedBuffer);

    // Processing the received data
    console.log(receivedView); // Output: Uint8Array(8) [0, 2, 4, 6, 8, 10, 12, 14]
};
```

