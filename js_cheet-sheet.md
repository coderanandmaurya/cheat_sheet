Here's a basic JavaScript cheat sheet to get you started:

### **JavaScript Cheat Sheet**

JavaScript is a high-level, versatile programming language that is primarily used for creating interactive and dynamic content on the web. It is an essential part of web development, along with HTML and CSS.

### **JavaScript**

- **Purpose**: JavaScript enables you to create interactive effects and dynamic features on web pages, such as form validation, animations, and content updates without reloading the page.
- **Execution**: It is executed in the browser, making it possible to run code directly on the client side. JavaScript can also be used on the server side with environments like Node.js.
- **Syntax**: JavaScript syntax is similar to other C-based languages like C++ and Java, making it relatively easy to learn if you have experience with those languages.
- **Objects and Functions**: JavaScript is object-oriented and functional, allowing you to use objects and functions to structure your code.

### **ECMAScript (ES)**

ECMAScript (often abbreviated as ES) is a specification for scripting languages like JavaScript. It defines the language's core features and functionality, which implementations like JavaScript adhere to.

- **Standardization**: ECMAScript is standardized by ECMA International, which ensures consistency and compatibility across different implementations.
- **Versions**: Over time, ECMAScript has evolved with various versions that introduce new features and improvements. Each version is referred to as ES followed by the year of release (e.g., ES5, ES6, ES2017).

### **Key Versions of ECMAScript**

1. **ES3 (ECMAScript 3)**: Released in 1999, it introduced regular expressions, try/catch for error handling, and more.

2. **ES5 (ECMAScript 5)**: Released in 2009, it added strict mode, JSON support, and methods like `Array.prototype.forEach()` and `Object.defineProperty()`.

3. **ES6 (ECMAScript 2015)**: A major update with significant new features including:
   - **Arrow Functions**: Shorter syntax for functions.
     ```javascript
     const add = (a, b) => a + b;
     ```
   - **Classes**: A more traditional way to define objects and inheritance.
     ```javascript
     class Person {
         constructor(name) {
             this.name = name;
         }
         greet() {
             return `Hello, ${this.name}!`;
         }
     }
     ```
   - **Template Literals**: For easier string interpolation and multi-line strings.
     ```javascript
     let name = "Alice";
     let greeting = `Hello, ${name}!`;
     ```
   - **Destructuring**: Extracting values from arrays or objects into variables.
     ```javascript
     let [a, b] = [1, 2];
     let {x, y} = {x: 10, y: 20};
     ```

4. **ES7 (ECMAScript 2016)**: Introduced:
   - **Exponentiation Operator**: `**` for powers.
     ```javascript
     let squared = 2 ** 2; // 4
     ```
   - **Array.prototype.includes()**: For checking if an array contains a value.
     ```javascript
     let numbers = [1, 2, 3];
     console.log(numbers.includes(2)); // true
     ```

5. **ES8 (ECMAScript 2017)**: Added:
   - **Async/Await**: For handling asynchronous operations more gracefully.
     ```javascript
     async function fetchData() {
         let response = await fetch('https://api.example.com/data');
         let data = await response.json();
         return data;
     }
     ```
   - **Object.entries()**: Converts an object into an array of key-value pairs.
     ```javascript
     let obj = { a: 1, b: 2 };
     console.log(Object.entries(obj)); // [['a', 1], ['b', 2]]
     ```

6. **ES9 (ECMAScript 2018)**: Introduced:
   - **Rest/Spread Properties**: For objects, allowing more flexible copying and merging.
     ```javascript
     let obj1 = { a: 1, b: 2 };
     let obj2 = { ...obj1, c: 3 };
     ```
   - **Asynchronous Iteration**: For iterating over asynchronous data sources.
     ```javascript
     async function* asyncGenerator() {
         yield 1;
         yield 2;
     }
     ```

7. **ES10 (ECMAScript 2019)**: Added:
   - **Array.prototype.flat() and Array.prototype.flatMap()**: For flattening arrays.
     ```javascript
     let arr = [1, [2, 3], [4, [5]]];
     console.log(arr.flat(2)); // [1, 2, 3, 4, 5]
     ```
   - **Object.fromEntries()**: Converts a list of key-value pairs into an object.
     ```javascript
     let entries = [['a', 1], ['b', 2]];
     let obj = Object.fromEntries(entries);
     ```

8. **ES11 (ECMAScript 2020)**: Introduced:
   - **Optional Chaining**: For safely accessing deeply nested properties.
     ```javascript
     let user = { profile: { name: 'John' } };
     console.log(user.profile?.name); // 'John'
     ```
   - **Nullish Coalescing Operator (??)**: Returns the right-hand operand when the left-hand operand is `null` or `undefined`.
     ```javascript
     let foo = null ?? 'default'; // 'default'
     ```

9. **ES12 (ECMAScript 2021)**: Added:
   - **Logical Assignment Operators**: Combined logical operators with assignment.
     ```javascript
     let x = true;
     x &&= false; // x is false
     ```
   - **WeakRefs**: For holding weak references to objects that don't prevent garbage collection.
     ```javascript
     let obj = {};
     let weakRef = new WeakRef(obj);
     ```

10. **ES13 (ECMAScript 2022)**: Introduced:
    - **Class Fields**: Allow class properties to be defined directly in the class body.
      ```javascript
      class MyClass {
          myField = 42;
      }
      ```
    - **Top-level await**: Allows using `await` at the top level of a module.
      ```javascript
      let data = await fetch('https://api.example.com/data');
      ```

11. **ES14 (ECMAScript 2023)**: Added:
    - **Array.prototype.findLast() and Array.prototype.findLastIndex()**: Methods to find elements from the end of an array.
      ```javascript
      let arr = [1, 2, 3, 4];
      console.log(arr.findLast(x => x < 4)); // 3
      ```

Each version of ECMAScript brings new features and improvements to JavaScript, making it a more powerful and efficient language for developers.

<hr>

## **1. Variables**
```javascript
let name = "John";   // Mutable variable
const age = 30;      // Immutable variable

// Variable types
let num = 100;       // Number
let isActive = true; // Boolean
let person = {       // Object
  name: "Alice",
  age: 25
};
let numbers = [1, 2, 3]; // Array
```

<hr>

## **2. Data Types**
- **String**: `"Hello"`
- **Number**: `100`
- **Boolean**: `true` / `false`
- **Object**: `{ key: "value" }`
- **Array**: `[1, 2, 3]`
- **Undefined**: `undefined`
- **Null**: `null`
- **Symbol**: `Symbol('description')`
  
In JavaScript, data types are the classifications that dictate how values can be used in the language. JavaScript has several built-in data types that fall into two categories: **primitive types** and **reference types**.

### **Primitive Data Types**
Primitive data types are immutable (i.e., their values cannot be changed) and are directly stored in the memory.

1. **String**
   - Represents a sequence of characters.
   - Example:
     ```javascript
     let greeting = "Hello, World!";
     console.log(typeof greeting); // Output: string
     ```

2. **Number**
   - Represents both integer and floating-point numbers.
   - Example:
     ```javascript
     let age = 30;
     let pi = 3.14;
     console.log(typeof age); // Output: number
     console.log(typeof pi);  // Output: number
     ```

3. **Boolean**
   - Represents a logical entity with two possible values: `true` or `false`.
   - Example:
     ```javascript
     let isJavaScriptFun = true;
     console.log(typeof isJavaScriptFun); // Output: boolean
     ```

4. **Undefined**
   - Represents a variable that has been declared but not yet assigned a value.
   - Example:
     ```javascript
     let x;
     console.log(typeof x); // Output: undefined
     ```

5. **Null**
   - Represents the intentional absence of any object value. It is a special keyword in JavaScript.
   - Example:
     ```javascript
     let y = null;
     console.log(typeof y); // Output: object (this is a known quirk in JavaScript)
     ```

6. **Symbol** (ES6)
   - Represents a unique and immutable identifier that can be used as a key for object properties.
   - Example:
     ```javascript
     let sym = Symbol("id");
     console.log(typeof sym); // Output: symbol
     ```

7. **BigInt** (ES11)
   - Represents integers with arbitrary precision, allowing you to work with very large numbers.
   - Example:
     ```javascript
     let bigNumber = BigInt(1234567890123456789012345678901234567890n);
     console.log(typeof bigNumber); // Output: bigint
     ```

### **Reference Data Types**
Reference data types are objects that store references (or pointers) to the values rather than the actual values. They are mutable, meaning their values can be changed.

1. **Object**
   - A collection of properties, where each property is a key-value pair. The key is a string (or symbol), and the value can be of any data type.
   - Example:
     ```javascript
     let person = {
         name: "Alice",
         age: 25
     };
     console.log(typeof person); // Output: object
     ```

2. **Array**
   - A special type of object used to store ordered collections of values.
   - Example:
     ```javascript
     let numbers = [1, 2, 3, 4, 5];
     console.log(typeof numbers); // Output: object
     ```

3. **Function**
   - A callable object that encapsulates code to perform a specific task. Functions are also considered objects in JavaScript.
   - Example:
     ```javascript
     function greet() {
         return "Hello!";
     }
     console.log(typeof greet); // Output: function
     ```

4. **Date**
   - Represents a single moment in time and is used for date and time calculations.
   - Example:
     ```javascript
     let today = new Date();
     console.log(typeof today); // Output: object
     ```

5. **RegExp**
   - Represents regular expressions, which are patterns used to match character combinations in strings.
   - Example:
     ```javascript
     let pattern = /ab+c/;
     console.log(typeof pattern); // Output: object
     ```

6. **Map and Set** (ES6)
   - **Map**: A collection of key-value pairs where keys can be of any data type.
   - **Set**: A collection of unique values (no duplicates allowed).
   - Example:
     ```javascript
     let map = new Map();
     map.set("key1", "value1");
     console.log(typeof map); // Output: object

     let set = new Set([1, 2, 3]);
     console.log(typeof set); // Output: object
     ```

### **Special Considerations**
- **Type Coercion**: JavaScript can automatically convert one data type to another (e.g., a string to a number) in certain contexts. This is known as type coercion.
- **Type Checking**: You can check the type of a value using the `typeof` operator.

Understanding these data types is essential for working effectively with JavaScript, as they influence how you manage and manipulate data in your programs.

<hr>

## **2A. Operators**
Certainly! Here's a single JavaScript code snippet that demonstrates all the major operators:

```javascript
// Arithmetic Operators
let a = 10;
let b = 3;

let sum = a + b;           // Addition: 13
let difference = a - b;    // Subtraction: 7
let product = a * b;       // Multiplication: 30
let quotient = a / b;      // Division: 3.333...
let remainder = a % b;     // Modulus: 1
let power = a ** b;        // Exponentiation: 1000

// Assignment Operators
let x = 5;
x += 2;  // x = x + 2 -> 7
x -= 3;  // x = x - 3 -> 4
x *= 2;  // x = x * 2 -> 8
x /= 4;  // x = x / 4 -> 2
x %= 2;  // x = x % 2 -> 0

// Comparison Operators
let isEqual = (a == b);          // false
let isNotEqual = (a != b);       // true
let isStrictEqual = (a === b);   // false
let isStrictNotEqual = (a !== b);// true
let isGreaterThan = (a > b);     // true
let isLessThan = (a < b);        // false
let isGreaterOrEqual = (a >= b); // true
let isLessOrEqual = (a <= b);    // false

// Logical Operators
let andResult = (a > 5 && b < 5); // true (both conditions true)
let orResult = (a > 5 || b > 5);  // true (one condition true)
let notResult = !(a < 5);         // true (negation)

// Bitwise Operators
let andBitwise = a & b;  // AND: 2 (in binary: 1010 & 0011 -> 0010)
let orBitwise = a | b;   // OR: 11 (in binary: 1010 | 0011 -> 1011)
let xorBitwise = a ^ b;  // XOR: 9 (in binary: 1010 ^ 0011 -> 1001)
let notBitwise = ~a;     // NOT: -11 (in binary: ~1010 -> 0101)
let leftShift = a << 1;  // Left shift: 20 (in binary: 1010 << 1 -> 10100)
let rightShift = a >> 1; // Right shift: 5 (in binary: 1010 >> 1 -> 0101)

// Ternary Operator
let isEven = (a % 2 === 0) ? 'Even' : 'Odd'; // 'Even'

// String Operators
let greeting = "Hello" + " " + "World!"; // Concatenation: "Hello World!"
```

This code covers:

- **Arithmetic Operators**: `+`, `-`, `*`, `/`, `%`, `**`
- **Assignment Operators**: `=`, `+=`, `-=`, `*=`, `/=`, `%=`
- **Comparison Operators**: `==`, `!=`, `===`, `!==`, `>`, `<`, `>=`, `<=`
- **Logical Operators**: `&&`, `||`, `!`
- **Bitwise Operators**: `&`, `|`, `^`, `~`, `<<`, `>>`
- **Ternary Operator**: `? :`
- **String Operator**: `+` (concatenation)

<hr>

## **3. Functions**
In JavaScript, functions are fundamental building blocks. They allow you to encapsulate logic, perform tasks, and return values. There are several ways to create functions, and they can be categorized into different types based on their syntax and use cases. Below are the common ways to create functions in JavaScript:

### 1. **Function Declaration**
A function declaration defines a function with a name. It can be called before it is defined due to hoisting.

```javascript
function greet(name) {
    return `Hello, ${name}!`;
}

console.log(greet("Alice")); // Output: Hello, Alice!
```

### 2. **Function Expression**
A function expression defines a function and assigns it to a variable. Unlike a function declaration, it is not hoisted, so it can't be called before it's defined.

```javascript
const greet = function(name) {
    return `Hello, ${name}!`;
};

console.log(greet("Bob")); // Output: Hello, Bob!
```

### 3. **Arrow Function**
Arrow functions are a shorter syntax for writing function expressions. They do not have their own `this`, `arguments`, or `super` binding, making them useful for non-method functions.

```javascript
const greet = (name) => `Hello, ${name}!`;

console.log(greet("Charlie")); // Output: Hello, Charlie!
```

### 4. **Anonymous Function**
An anonymous function is a function without a name. It is often used in situations where a function is needed only once, such as in event handlers or immediately invoked function expressions (IIFE).

```javascript
const result = (function(a, b) {
    return a + b;
})(5, 10);

console.log(result); // Output: 15
```

### 5. **Immediately Invoked Function Expression (IIFE)**
An IIFE is a function that is defined and executed immediately. It is often used to create a new scope.

```javascript
(function() {
    console.log("This function runs immediately!");
})();
```

### 6. **Constructor Function**
Constructor functions are used to create objects. When a function is used as a constructor with the `new` keyword, it creates an instance of an object.

```javascript
function Person(name, age) {
    this.name = name;
    this.age = age;
}

const person1 = new Person("David", 30);
console.log(person1.name); // Output: David
console.log(person1.age);  // Output: 30
```

### 7. **Generator Function**
Generator functions use the `function*` syntax and can pause their execution using `yield`. They return a generator object that can be iterated over.

```javascript
function* generateSequence() {
    yield 1;
    yield 2;
    yield 3;
}

const generator = generateSequence();
console.log(generator.next().value); // Output: 1
console.log(generator.next().value); // Output: 2
console.log(generator.next().value); // Output: 3
```

### 8. **Async Function**
Async functions are functions that return a `Promise`. They allow you to write asynchronous code in a more synchronous manner using `async` and `await`.

```javascript
async function fetchData() {
    const response = await fetch('https://api.example.com/data');
    const data = await response.json();
    return data;
}

fetchData().then(data => console.log(data));
```

Each type of function in JavaScript serves different purposes and can be used based on the specific requirements of the code you are writing.

<hr>

## **4. Control Flow**
- **Conditionals**
```javascript
if (condition) {
  // code
} else if (anotherCondition) {
  // code
} else {
  // code
}
```
- **Switch**
```javascript
switch (value) {
  case 1:
    // code
    break;
  case 2:
    // code
    break;
  default:
    // code
}
```
- **Loops**
```javascript
for (let i = 0; i < 5; i++) {
  console.log(i);
}

let j = 0;
while (j < 5) {
  console.log(j);
  j++;
}

let k = 0;
do {
  console.log(k);
  k++;
} while (k < 5);
```
<hr>

## **5. Array Methods**
```javascript
let arr = [1, 2, 3, 4];

// Add/Remove items
arr.push(5);    // Add to end
arr.pop();      // Remove from end
arr.shift();    // Remove from start
arr.unshift(0); // Add to start

// Iteration
arr.forEach(item => console.log(item));

// Mapping
let doubled = arr.map(x => x * 2);

// Filtering
let even = arr.filter(x => x % 2 === 0);
```

<hr>

## **6. Object Methods**
```javascript
let obj = {
  name: "John",
  age: 30,
  greet() {
    return `Hello, ${this.name}`;
  }
};

console.log(obj.greet()); // "Hello, John"
```
<hr>

## **7. Events**
```javascript
document.getElementById('myButton').addEventListener('click', () => {
  alert('Button clicked!');
});
```
<hr>

## **8. DOM Manipulation**
```javascript
let elem = document.getElementById('myElement');
elem.textContent = 'New content';
elem.style.color = 'blue';
```

<hr>

## **9. Promises & Async/Await**
```javascript
// Promise
fetch('https://api.example.com/data')
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error(error));

// Async/Await
async function fetchData() {
  try {
    let response = await fetch('https://api.example.com/data');
    let data = await response.json();
    console.log(data);
  } catch (error) {
    console.error(error);
  }
}
```

<hr>

## **10. Error Handling**
```javascript
try {
  // code that may throw an error
} catch (error) {
  console.error(error);
} finally {
  // code that will run regardless of the outcome
}
```

Feel free to expand or modify this cheat sheet based on your needs!
