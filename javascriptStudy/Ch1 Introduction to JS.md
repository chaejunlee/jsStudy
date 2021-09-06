# Introduction to JavaScript

- JavaScript is a **high-level, dynamic, interpreted programming language that is well-suited to object-oriented and functional programming styles**.

- JS's variables are **untyped**.
    
    
> ### JavaScript: Names, Versions, and Modes
>
>
- ECMAScript, or ES, refers to the **language standard and to versions of that standard**. (ECMA - European Computer Manufacturer's Association)
>
- ES5 standard has been supported by all web browsers. This book treats **ES5 as the compatibility baseline and no longer discusses earlier versions of the language**.
>
- **ES6 was released in 2015** and added major new features—including `class` and `module` syntax—that changed JavaScript from a scripting language into a serious, general-purpose language suitable for large-scale software engineering.
>
- In ES5 and later, programs can opt in to JavaScript’s strict mode in which a number of early language mistakes have been corrected. The mechanism for opting in is the **`“use strict”`** directive
>
- => There is a **legacy JavaScript** and **strict JavaScript**.
>
- In ES6 and later, the use of new language features often implicitly invokes strict mode. For example, if you use the ES6 `class` keyword or create an ES6 module, then all the code within the class or module is automatically strict, and the **old, flawed features are not available in those contexts**.



-  Input and output (as well as more sophisticated features, such as networking, storage, and graphics) are the responsibility of the **“host environment”** within which JavaScript is embedded.

- The original host environment for JavaScript was a **web browser**, and this is still the most common execution environment for JavaScript code. 

- Since 2010, **Node** gives JavaScript access to the entire operating system, allowing JavaScript programs to read and write files, send and receive data over the network, and make and serve HTTP requests.

## 1.1 Exploring JavaScript

- The easiest way to try out a few lines of JavaScript is to open up the **web developer
tools in your web browser** (with F12, Ctrl-Shift-I, or Command-Option-I) and select
the Console tab.

- Another way to try out JavaScript code is to download and install **Node**.

## 1.2 Hello World

- For longer chunks of code, you can do:

  1. Write your code in a text editor, then **copy and paste to the JavaScript console**.

  2. Write your code in a text editor, then **copy and paste into a Node session**.

  3. Save your code to a **.js file** and then **run that file of JavaScript code with Node**:
`$ node snippet.js`  

- If you use Node in a noninteractive manner (like iii.), it won't automatically print out the value of all the code you run. You have to do that yourself. You can **use the function `console.log()`** to display text and other JavaScript values in your terminal window or in a browser's developer tools console.

## 1.3 A Tour of JavaScript

- This chapter is quick introductory chapter.

- Chap2 is about JavaScript comments, semicolons, and the Unicode character set.

- Chap3 is about JavaScript variables and the values you can assign to those variables.

```javascript
// variables are declared with the let keyword:
let x;        // Declare a variable named x.

// Values can be assigned to variables with an = sign 
x = 0;              // Now the variable x has the value 0
x                   // => 0: A variable evaluates to its value.

// JavaScript supports several types of values
x = 1;              // Numbers.
x = 0.01;           // Numbers can be integers or reals.
x = "hello world";  // Strings of text in quotation marks.
x = 'JavaScript';   // Single quote marks also delimit strings.
x = true;           // A Boolean value.
x = false;          // The other Boolean value.
x = null;           // Null is a special value that means "no value."
x = undefined;      // Undefined is another special value like null.
```
- JavaScript supports: `Numbers (integers, reals)`, `Strings`, `Boolean`, `null`, `undefined`, + (`object`, `array`)

```javascript
// JavaScript's most important datatype is the object.
// An object is a collection of name/value pairs, or a string to value map.

let book = {                // Objects are enclosed in curly braces.
  topic: "JavaScript",      // The property "topic" has value "JavaScript."
  edition: 7                // The property "edition" has value 7
};                          // The curly brace marks the end of the object.

// Access the properties of an object with . or []:

book.topic                  // => "JavaScript"
book["edition"]             // => 7: another way to access property values.
book.author = "Flanagan";   // Create new properties by assignment.
book.contents = {};         // {} is an empty object with no properties.

// Conditionally access properties with ?. (ES2020):

book.contents?.ch01?.sect1  // => undefined: book.contents has no ch01 property.

// JavaScript also supports arrays (numerically indexed lists) of values:
let primes = [2, 3, 5, 7];  // An array of 4 values, delimited with [ and ].
primes[0]                   // => 2: the first element (index 0) of the array.
primes.length               // => 4: how many elements in the array.
primes[primes.length-1]     // => 7: the last element of the array.
primes[4] = 9;              // Add a new element by assignment.
primes[4] = 11;             // Or alter an existing element by assignment.
let empty = [];             // [] is an empty array with no elements.
empty.length                // => 0

// Arrays and objects can hold other arrays and objects:

let points = [              // An array with 2 elements.
  {x: 0, y: 0},             // Each element is an object.
  {x: 1, y: 1}
];

let data = {                // An object with 2 properties
  trial1: [[1,2], [3,4]],   // The value of each property is an array.
  trial2: [[2,3], [4,5]]    // The elements of the arrays are arrays.
};
```

> ### Comment Syntax in Code Examples
>
- **=>** : to show the value produced by the code before the comment. (like a web browser console in a printed book)
>
- **// =>** : serve as an *assertion*.  
  **// a == 42 (==**) : another *assertion*. 
>
- **// !** : the code on the line before the comment throws an exception (and the rest of the comment after the exclamation mark usually explains what kind of exception is thrown).

