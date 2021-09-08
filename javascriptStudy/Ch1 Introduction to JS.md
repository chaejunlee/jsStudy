# Introduction to JavaScript

- JavaScript is a **high-level, dynamic, interpreted programming language that is well-suited to object-oriented and functional programming styles**.

- JS's variables are **untyped**.

<br>

> ### JavaScript: Names, Versions, and Modes
>
>
> - ECMAScript, or ES, refers to the **language standard and to versions of that standard**. (ECMA - European Computer Manufacturer's Association)
>
> - ES5 standard has been supported by all web browsers. This book treats **ES5 as the compatibility baseline and no longer discusses earlier versions of the language**.
>
> - **ES6 was released in 2015** and added major new features—including `class` and `module` syntax—that changed JavaScript from a scripting language into a serious, general-purpose language suitable for large-scale software engineering.
>
> - In ES5 and later, programs can opt in to JavaScript’s strict mode in which a number of early language mistakes have been corrected. The mechanism for opting in is the **`“use strict”`** directive
>
> - => There is a **legacy JavaScript** and **strict JavaScript**.
>
> - In ES6 and later, the use of new language features often implicitly invokes strict mode. For example, if you use the ES6 `class` keyword or create an ES6 module, then all the code within the class or module is automatically strict, and the **old, flawed features are not available in those contexts**.

<br>

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

<br>

> ### Comment Syntax in Code Examples
>
> - **=>** : to show the value produced by the code before the comment. (like a web browser console in a printed book)
>
> - **// =>** : serve as an *assertion*.  
  **// a == 42 (==**) : another *assertion*. 
>
> - **// !** : the code on the line before the comment throws an exception (and the rest of the comment after the exclamation mark usually explains what kind of exception is thrown).

<br>

- `[]`, `{}`, `.` are called *initializer expression*. An *expression* is a phrase of JavaScript that can be *evaluated* to produce a value. One of the most common ways to form expressions in JavaScript is to use *operators*:

```javascript

// Operators act on values (the operands) to produce a new value.
// Arithmetic operators are some of the simplest:
3 + 2                       // => 5: addition
3 - 2                       // => 1: subtraction
3 * 2                       // => 6: multiplication
3 / 2                       // => 1.5: division
points[1].x - points[0].x   // => 1: more complicated operands also work
"3" + "2"                   // => "32": + adds numbers, concatenates strings

// JavaScript defines some shorthand arithmetic operators
let count = 0;              // Define a variable
count++;                    // Increment the variable
count--;                    // Decrement the variable
count += 2;                 // Add 2: same as count = count + 2;
count *= 3;                 // Multiply by 3: same as count = count * 3;
count                       // => 6: variable names are expressions, too.

// Equality and relational operators test whether two values are equal,
// unequal, less than, greater than, and so on. They evaluate to true or false.
let x = 2, y = 3;           // These = signs are assignment, not equality tests
x === y                     // => false: equality
x !== y                     // => true: inequality
x < y                       // => true: less-than
x <= y                      // => true: less-than or equal
x > y                       // => false: greater-than
x >= y                      // => false: greater-than or equal
"two" === "three"           // => false: the two strings are different
"two" > "three"             // => true: "tw" is alphabetically greater than "th"
false === (x > y)           // => true: false is equal to false

// Logical operators combine or invert boolean values
(x === 2) && (y === 3)      // => true: both comparisons are true. && is AND
(x > 3) || (y < 3)          // => false: neither comparison is true. || is OR
!(x === y)                  // => true: ! inverts a boolean value

```

- **JavaScript *statements* **: full sentences, **JavaScript expression**: phrases

- Roughly, an **expression** is something that computes a value but doesn't *do* anything. **Statements**, on the other hand, don't have a value, but they do alter the program state. (variable declarations and assignment statements)

- The other broad category of statement is *control structures*, such as conditionals and loops.

- A ** *function* ** is a named and parameterized block of JavaScript code that you **define once**, and can then **invoke over and over again**.

```javascript

// Functions are parameterized blocks of JavaScript code that we can invoke.
function plus1(x) {           // Define a function named "plus1" with parameter "x"
 return x + 1;                // Return a value one larger than the value passed in
}                             // Functions are enclosed in curly braces
plus1(y)                      // => 4: y is 3, so this invocation returns 3+1
let square = function(x) {    // Functions are values and can be assigned to vars
 return x * x;                // Compute the function's value
};                            // Semicolon marks the end of the assignment.
square(plus1(y))              // => 16: invoke two functions in one expression

```

- In ES6 and later, there is a shorthand syntax for defining functions. This concise syntax uses => to separate the argument list from the function body, also known as *arrow functions*. Arrow functions are most commonly used when you want to pass an unnamed function as an argument to another function.

```javascript

// The preceding code looks like this when rewritten to use arrow functions
const plus1 = x => x + 1;   // The input x maps to the output x + 1
const square = x => x * x;  // The input x maps to the output x * x
plus1(y)                    // => 4: function invocation is the same
square(plus1(y))            // => 16

```

- When we use functions with objects, we get methods:

```javascript

// When functions are assigned to the properties of an object, we call
// them "methods." All JavaScript objects (including arrays) have methods:
let a = [];                   // Create an empty array
a.push(1,2,3);                // The push() method adds elements to an array
a.reverse();                  // Another method: reverse the order of elements

// We can define our own methods, too. The "this" keyword refers to the object
// on which the method is defined: in this case, the points array from earlier.
points.dist = function() {    // Define a method to compute distance between points
 let p1 = this[0];            // First element of array we're invoked on
 let p2 = this[1];            // Second element of the "this" object
 let a = p2.x-p1.x;           // Difference in x coordinates
 let b = p2.y-p1.y;           // Difference in y coordinates
 return Math.sqrt(a*a + b*b); // The Pythagorean theorem
                              // Math.sqrt() computes the square root
};
points.dist()                 // => Math.sqrt(2): distance between our 2 points

```

- JavaScript control structure statements

```javascript

// JavaScript statements include conditionals and loops using the syntax
// of C, C++, Java, and other languages.
function abs(x) {         // A function to compute the absolute value.
  if (x >= 0) {           // The if statement...
    return x;             // executes this code if the comparison is true.
  }                       // This is the end of the if clause.
  else {                  // The optional else clause executes its code if
    return -x;            // the comparison is false.
  }                       // Curly braces optional when 1 statement per clause.
}                         // Note return statements nested inside if/else.
abs(-10) === abs(10)      // => true

function sum(array) {     // Compute the sum of the elements of an array
  let sum = 0;            // Start with an initial sum of 0.
  for(let x of array) {   // Loop over array, assigning each element to x.
    sum += x;             // Add the element value to the sum.
  }                       // This is the end of the loop.
  return sum;             // Return the sum.
}
sum(primes)               // => 28: sum of the first 5 primes 2+3+5+7+11

function factorial(n) {   // A function to compute factorials
  let product = 1;        // Start with a product of 1
  while(n > 1) {          // Repeat statements in {} while expr in () is true
    product *= n;         // Shortcut for product = product * n;
    n--;                  // Shortcut for n = n - 1
  }                       // End of loop
  return product;         // Return the product
}
factorial(4) // => 24: 1*4*3*2

function factorial2(n) {  // Another version using a different loop
  let i, product = 1;     // Start with 1
  for(i=2; i <= n; i++)   // Automatically increment i from 2 up to n
    product *= i;         // Do this each time. {} not needed for 1-line loops
  return product;         // Return the factorial
}
factorial2(5)             // => 120: 1*2*3*4*5

```

- JavaScript supports an **object-oriented programming style**, but it is significantly different than “classical” object-oriented programming languages.

```javascript

class Point {             // By convention, class names are capitalized.
  constructor(x, y) {     // Constructor function to initialize new instances.
    this.x = x;           // This keyword is the new object being initialized.
    this.y = y;           // Store function arguments as object properties.
  }                       // No return is necessary in constructor functions.
  distance() {            // Method to compute distance from origin to point.
    return Math.sqrt(     // Return the square root of x² + y².
      this.x * this.x +   // this refers to the Point object on which
      this.y * this.y     // the distance method is invoked.
    );
  }
}

// Use the Point() constructor function with "new" to create Point objects
let p = new Point(1, 1);  // The geometric point (1,1).

// Now use a method of the Point object p
p.distance()              // => Math.SQRT2

```

## 1.4 Example: Character Frequency Histograms

- I found it interesting. Understood about 70%, maybe. Want to catch-up so quick!!

## 1.5 Summary

- This book explains JavaScript from the bottom up. This means that we start with low level details like comments, identifiers, variables, and types; then build to expressions, statements, objects, and functions; and then cover high-level language abstractions like classes and modules.

-  True mastery of JavaScript requires an understanding of the details.