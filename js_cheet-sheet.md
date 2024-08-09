Here's a basic JavaScript cheat sheet to get you started:

### **JavaScript Cheat Sheet**

#### **1. Variables**
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

#### **2. Data Types**
- **String**: `"Hello"`
- **Number**: `100`
- **Boolean**: `true` / `false`
- **Object**: `{ key: "value" }`
- **Array**: `[1, 2, 3]`
- **Undefined**: `undefined`
- **Null**: `null`
- **Symbol**: `Symbol('description')`

#### **3. Functions**
```javascript
function greet(name) {
  return `Hello, ${name}`;
}

const add = (a, b) => a + b; // Arrow function
```

#### **4. Control Flow**
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

#### **5. Array Methods**
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

#### **6. Object Methods**
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

#### **7. Events**
```javascript
document.getElementById('myButton').addEventListener('click', () => {
  alert('Button clicked!');
});
```

#### **8. DOM Manipulation**
```javascript
let elem = document.getElementById('myElement');
elem.textContent = 'New content';
elem.style.color = 'blue';
```

#### **9. Promises & Async/Await**
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

#### **10. Error Handling**
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
