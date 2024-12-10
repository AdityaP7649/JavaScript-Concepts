# JavaScript-Concepts

1. Variables (`var`, `let`, `const`):
Think of variables like labeled boxes where you can store different types of information.
- `var`: An older way to declare variables, with fewer restrictions (less recommended now)
- `let`: Modern way to declare variables that can be changed later
- `const`: Used for values that shouldn't change (constant values)

Example:
```javascript
let age = 25;  // Can be changed later
const PI = 3.14;  // Cannot be modified
var name = "John";  // Old-style declaration
```

2. Data Types:
Imagine different types of containers for different kinds of information:
- `String`: Text data (wrapped in quotes)
- `Number`: Numeric values (both integers and decimals)
- `Boolean`: True or false values
- `Object`: Complex data structure that can hold multiple values
- `Undefined`: A variable that has been declared but not assigned a value
- `Null`: Intentional absence of any object value
- `Symbol`: Unique identifier
- `BigInt`: For extremely large numbers

Example:
```javascript
let text = "Hello";  // String
let count = 42;  // Number
let isTrue = true;  // Boolean
let person = {name: "Alice", age: 30};  // Object
let nothing = null;  // Null
let unused;  // Undefined
```

3. Type Conversion:
Changing one type of data to another:
```javascript
let numString = "42";
let num = Number(numString);  // Converts string to number
let stringNum = String(num);  // Converts number to string
let boolValue = Boolean(num);  // Converts to true/false
```

4. Operators:
Different ways to perform operations:
- Arithmetic: `+`, `-`, `*`, `/`, `%` (remainder)
- Comparison: `==`, `===`, `>`, `<`, `>=`, `<=`
- Logical: `&&` (and), `||` (or), `!` (not)
- Assignment: `=`, `+=`, `-=`, `*=`, `/=`
- Ternary: `condition ? valueIfTrue : valueIfFalse`

Example:
```javascript
let x = 10;
let y = 5;
let result = x + y;  // Arithmetic
let isEqual = (x === y);  // Comparison
let combined = (x > 0 && y < 10);  // Logical
let shorthand = x += 5;  // Assignment
let quick = (x > 0) ? "Positive" : "Negative";  // Ternary
```

5. Conditional Statements:
Ways to make decisions in code:
```javascript
// If-else
if (age >= 18) {
    console.log("Adult");
} else {
    console.log("Minor");
}

// Switch
switch (day) {
    case "Monday":
        console.log("Start of work week");
        break;
    case "Friday":
        console.log("Almost weekend!");
        break;
    default:
        console.log("Regular day");
}
```

6. Loops:
Repeating actions multiple times:
```javascript
// Standard for loop
for (let i = 0; i < 5; i++) {
    console.log(i);
}

// While loop
let j = 0;
while (j < 5) {
    console.log(j);
    j++;
}

// For...of (iterating over arrays)
let fruits = ["apple", "banana", "cherry"];
for (let fruit of fruits) {
    console.log(fruit);
}
```

7. Functions:
Ways to create reusable blocks of code:
```javascript
// Function declaration
function greet(name) {
    return `Hello, ${name}!`;
}

// Function expression
let multiply = function(a, b) {
    return a * b;
};

// Arrow function
let add = (a, b) => a + b;
```

8. Scope:
Where variables can be accessed:
```javascript
// Global scope
let globalVar = "I'm everywhere";

function exampleScope() {
    // Local/function scope
    let localVar = "I'm inside the function";
}
```

9. Hoisting:
JavaScript moves variable and function declarations to the top of their scope:
```javascript
console.log(x);  // Doesn't throw an error, returns undefined
var x = 5;

// Equivalent to:
var x;
console.log(x);
x = 5;
```

10. Closures:
Functions that remember the environment they were created in:
```javascript
function createCounter() {
    let count = 0;
    return function() {
        return ++count;
    };
}

let counter = createCounter();
console.log(counter());  // 1
console.log(counter());  // 2
```

1. Object Literals:
Objects are like containers that hold related information together:
```javascript
let person = {
    name: "John",      // Property
    age: 30,           // Property
    city: "New York"   // Property
};
```

2. Object Methods:
Functions that are part of an object:
```javascript
let car = {
    brand: "Toyota",
    start: function() {
        console.log("Engine started!");
    },
    // Shorthand method syntax
    stop() {
        console.log("Engine stopped!");
    }
};
car.start();  // Calls the method
```

3. Object Properties:
Ways to work with object properties:
```javascript
let student = {
    name: "Alice",
    grade: 95
};

// Adding new property
student.age = 20;

// Checking if property exists
console.log("name" in student);  // true

// Deleting a property
delete student.grade;
```

4. Object Prototypes:
A way to add methods and properties to all instances of an object:
```javascript
function Animal(name) {
    this.name = name;
}

// Adding method to prototype
Animal.prototype.speak = function() {
    console.log(this.name + " makes a sound");
};

let dog = new Animal("Rex");
dog.speak();  // "Rex makes a sound"
```

5. Inheritance:
Creating a new object based on another object:
```javascript
class Animal {
    constructor(name) {
        this.name = name;
    }
    
    speak() {
        console.log(this.name + " makes a sound");
    }
}

class Dog extends Animal {
    bark() {
        console.log(this.name + " barks");
    }
}

let myDog = new Dog("Buddy");
myDog.speak();  // Inherited method
myDog.bark();   // Dog's own method
```

6. `this` Keyword:
Refers to the current context:
```javascript
let person = {
    name: "John",
    greet() {
        // 'this' refers to the person object
        console.log(`Hello, my name is ${this.name}`);
    }
};

// Arrow functions handle 'this' differently
let calculator = {
    value: 0,
    increment: () => {
        // 'this' does not work as expected in arrow functions
        this.value++;  // Careful!
    }
};
```

7. Destructuring:
Extracting values from objects or arrays easily:
```javascript
// Object destructuring
let {name, age} = {name: "John", age: 30, city: "NY"};
console.log(name);  // "John"

// Array destructuring
let [first, second] = ["apple", "banana", "cherry"];
console.log(first);  // "apple"
```

8. Spread Operator:
Expanding elements of an array or object:
```javascript
// Combining arrays
let fruits = ["apple", "banana"];
let moreFruits = [...fruits, "cherry"];

// Copying objects
let original = {x: 1, y: 2};
let copy = {...original};

// Passing arguments
function sum(x, y, z) {
    return x + y + z;
}
let numbers = [1, 2, 3];
console.log(sum(...numbers));
```

9. Rest Parameters:
Collecting multiple arguments into an array:
```javascript
function sum(...numbers) {
    return numbers.reduce((a, b) => a + b, 0);
}
console.log(sum(1, 2, 3, 4));  // 10

// Destructuring with rest
let [first, ...rest] = [1, 2, 3, 4, 5];
console.log(rest);  // [2, 3, 4, 5]
```

10. Arrays and Array Methods:
Powerful ways to manipulate arrays:
```javascript
let numbers = [1, 2, 3, 4, 5];

// Map: Transform each element
let doubled = numbers.map(num => num * 2);
// [2, 4, 6, 8, 10]

// Filter: Keep elements that pass a test
let evenNumbers = numbers.filter(num => num % 2 === 0);
// [2, 4]

// Reduce: Combine array elements
let sum = numbers.reduce((total, num) => total + num, 0);
// 15

// Other useful methods
numbers.forEach(num => console.log(num));
let hasEven = numbers.some(num => num % 2 === 0);
let allEven = numbers.every(num => num % 2 === 0);
```

1. Promises:
Promises represent the eventual completion (or failure) of an asynchronous operation.

```javascript
let myPromise = new Promise((resolve, reject) => {
    // Simulating an async operation
    let success = true;
    if (success) {
        resolve("Operation successful!");
    } else {
        reject("Something went wrong");
    }
});

myPromise
    .then(result => console.log(result))
    .catch(error => console.log(error));
```

2. Async/Await:
A more readable way to work with promises:

```javascript
async function fetchData() {
    try {
        let response = await fetch('https://api.example.com/data');
        let data = await response.json();
        return data;
    } catch (error) {
        console.log('Error fetching data:', error);
    }
}
```

3. Callbacks:
Functions passed as arguments to other functions:

```javascript
function greet(name, callback) {
    console.log('Hello ' + name);
    callback();
}

greet('John', function() {
    console.log('Callback executed!');
});
```

4. Event Loop:
JavaScript's mechanism for handling asynchronous operations:

```javascript
console.log('Start');

// Microtask (Promise)
Promise.resolve().then(() => {
    console.log('Promise resolved');
});

// Macrotask (setTimeout)
setTimeout(() => {
    console.log('Timeout completed');
}, 0);

console.log('End');
// Output order: Start, End, Promise resolved, Timeout completed
```

5. `setTimeout` and `setInterval`:
Scheduling function calls:

```javascript
// Run once after delay
let timeout = setTimeout(() => {
    console.log('Delayed execution');
}, 2000);

// Repeat at intervals
let interval = setInterval(() => {
    console.log('Repeated every 2 seconds');
}, 2000);

// Stop the interval
clearInterval(interval);
```

6. Error Handling:
Managing and throwing errors:

```javascript
function divide(a, b) {
    try {
        if (b === 0) {
            throw new Error('Division by zero');
        }
        return a / b;
    } catch (error) {
        console.error(error.message);
    } finally {
        console.log('Calculation attempted');
    }
}
```

7. `null` vs `undefined`:
Difference in value representation:

```javascript
let x;  // undefined
let y = null;  // explicitly set to nothing

console.log(x);  // undefined
console.log(y);  // null

console.log(typeof x);  // "undefined"
console.log(typeof y);  // "object"
```

8. Event Handling:
Responding to user interactions:

```javascript
let button = document.getElementById('myButton');

button.addEventListener('click', function(event) {
    console.log('Button clicked!');
    console.log(event);  // Event details
});
```

9. DOM Manipulation:
Changing HTML elements:

```javascript
// Create new element
let newDiv = document.createElement('div');
newDiv.textContent = 'New content';

// Modify existing element
let existingElement = document.getElementById('myElement');
existingElement.style.color = 'red';
existingElement.classList.add('highlight');
```

10. Template Literals:
Advanced string formatting:

```javascript
let name = 'John';
let age = 30;

let message = `
    Hello, ${name}!
    You are ${age} years old.
    Multiline strings are easy now.
`;
```

11. Modules:
Organizing and sharing code:

```javascript
// math.js
export function add(a, b) {
    return a + b;
}

// main.js
import { add } from './math.js';
console.log(add(5, 3));  // 8
```

12. Classes and Objects:
Object-oriented programming:

```javascript
class Person {
    constructor(name, age) {
        this.name = name;
        this.age = age;
    }

    sayHello() {
        console.log(`Hello, I'm ${this.name}`);
    }
}

let john = new Person('John', 30);
john.sayHello();
```

13. `super` Keyword:
Calling parent class methods:

```javascript
class Animal {
    constructor(name) {
        this.name = name;
    }
}

class Dog extends Animal {
    constructor(name, breed) {
        super(name);  // Call parent constructor
        this.breed = breed;
    }
}
```

14. `new` Operator:
Creating object instances:

```javascript
function Car(make, model) {
    this.make = make;
    this.model = model;
}

let myCar = new Car('Toyota', 'Corolla');
```

15. Generators:
Functions that can be paused and resumed:

```javascript
function* numberGenerator() {
    yield 1;
    yield 2;
    yield 3;
}

let generator = numberGenerator();
console.log(generator.next().value);  // 1
console.log(generator.next().value);  // 2
```

16. Iterators:
Custom iteration behavior:

```javascript
let customIterator = {
    [Symbol.iterator]() {
        let count = 0;
        return {
            next() {
                count++;
                return { 
                    value: count, 
                    done: count > 3 
                };
            }
        };
    }
};
```

17. Symbols:
Unique identifiers:

```javascript
let sym1 = Symbol('description');
let sym2 = Symbol('description');

console.log(sym1 === sym2);  // false
```

18. WeakMap and WeakSet:
Special collections with weak references:

```javascript
let weakMap = new WeakMap();
let obj = {};

weakMap.set(obj, 'value');
```

19. Proxy and Reflect:
Metaprogramming techniques:

```javascript
let handler = {
    get(target, property) {
        console.log(`Accessing ${property}`);
        return target[property];
    }
};

let obj = { name: 'John' };
let proxy = new Proxy(obj, handler);
console.log(proxy.name);  // Logs access and returns 'John'
```

20. JSON Parsing:
Converting between objects and strings:

```javascript
let obj = { name: 'John', age: 30 };
let jsonString = JSON.stringify(obj);
let parsedObj = JSON.parse(jsonString);
```

21. Regular Expressions:
Pattern matching in strings:

```javascript
let pattern = /hello/i;  // Case-insensitive
console.log(pattern.test('Hello World'));  // true
```

22. Tagged Templates:
Custom string processing:

```javascript
function highlight(strings, ...values) {
    return strings.reduce((result, str, i) => 
        `${result}${str}<span class="highlight">${values[i] || ''}</span>`, 
    '');
}

let name = 'John';
let age = 30;
let output = highlight`Name: ${name}, Age: ${age}`;
```

I'll break down these browser-specific and ES6+ features in a comprehensive, easy-to-understand manner:

## Browser-Specific Concepts

### 1. Browser Events
Different types of events you can interact with:

```javascript
// Mouse events
document.getElementById('button').addEventListener('click', () => {
    console.log('Button clicked!');
});

// Keyboard events
document.addEventListener('keydown', (event) => {
    console.log('Key pressed:', event.key);
});

// Form events
document.getElementById('form').addEventListener('submit', (event) => {
    event.preventDefault();  // Prevent form submission
    console.log('Form submitted');
});
```

### 2. Event Delegation
Handling events efficiently for multiple elements:

```javascript
// Instead of adding events to each list item
document.getElementById('parentList').addEventListener('click', (event) => {
    if (event.target.tagName === 'LI') {
        console.log('Clicked item:', event.target.textContent);
    }
});
```

### 3. `addEventListener` and `removeEventListener`
Managing event listeners:

```javascript
function handleClick() {
    console.log('Clicked!');
}

let button = document.getElementById('myButton');
button.addEventListener('click', handleClick);

// Remove the event listener later
button.removeEventListener('click', handleClick);
```

### 4. `localStorage` and `sessionStorage`
Storing data in the browser:

```javascript
// localStorage (persists after browser closes)
localStorage.setItem('username', 'John');
let username = localStorage.getItem('username');
localStorage.removeItem('username');

// sessionStorage (clears when browser tab closes)
sessionStorage.setItem('tempData', 'Temporary value');
```

### 5. Cookies
Managing browser cookies:

```javascript
// Set a cookie
document.cookie = "username=John; expires=Thu, 18 Dec 2023 12:00:00 UTC; path=/";

// Read cookies
console.log(document.cookie);
```

### 6. Fetch API
Modern way to make HTTP requests:

```javascript
fetch('https://api.example.com/data')
    .then(response => response.json())
    .then(data => console.log(data))
    .catch(error => console.error('Error:', error));

// Async/Await syntax
async function fetchData() {
    try {
        let response = await fetch('https://api.example.com/data');
        let data = await response.json();
        return data;
    } catch (error) {
        console.error('Error:', error);
    }
}
```

### 7. XMLHttpRequest
Older method of making HTTP requests:

```javascript
let xhr = new XMLHttpRequest();
xhr.open('GET', 'https://api.example.com/data', true);

xhr.onload = function() {
    if (xhr.status === 200) {
        let data = JSON.parse(xhr.responseText);
        console.log(data);
    }
};

xhr.send();
```

### 8. Geolocation
Accessing user's location:

```javascript
if ("geolocation" in navigator) {
    navigator.geolocation.getCurrentPosition(
        (position) => {
            console.log('Latitude:', position.coords.latitude);
            console.log('Longitude:', position.coords.longitude);
        },
        (error) => {
            console.error('Error getting location:', error);
        }
    );
}
```

### 9. Web APIs
Various browser APIs:

```javascript
// Canvas API
let canvas = document.getElementById('myCanvas');
let ctx = canvas.getContext('2d');
ctx.fillStyle = 'red';
ctx.fillRect(10, 10, 150, 100);

// WebSocket
let socket = new WebSocket('wss://example.com/socket');
socket.onmessage = (event) => {
    console.log('Received:', event.data);
};
```

## ES6+ Features

### 1. Arrow Functions
Concise function syntax:

```javascript
// Traditional function
function add(a, b) {
    return a + b;
}

// Arrow function
const addArrow = (a, b) => a + b;

// With single parameter
const square = x => x * x;
```

### 2. Default Parameters
Setting default values for function parameters:

```javascript
function greet(name = 'Guest', greeting = 'Hello') {
    return `${greeting}, ${name}!`;
}

console.log(greet());  // "Hello, Guest!"
console.log(greet('John'));  // "Hello, John!"
```

### 3. Template Literals
Advanced string interpolation:

```javascript
let name = 'John';
let age = 30;

let message = `
    Hello, ${name}!
    You are ${age} years old.
    Multiline strings are now easy.
`;
```

### 4. Enhanced Object Literals
Simplified object creation:

```javascript
let name = 'John';
let age = 30;

// Old way
let person = {
    name: name,
    age: age,
    sayHello: function() {
        console.log('Hello!');
    }
};

// Enhanced object literal
let personES6 = {
    name,
    age,
    sayHello() {
        console.log('Hello!');
    }
};
```

### 5. Rest/Spread Operators
Handling multiple arguments:

```javascript
// Rest operator
function sum(...numbers) {
    return numbers.reduce((a, b) => a + b, 0);
}

// Spread operator
let arr1 = [1, 2, 3];
let arr2 = [...arr1, 4, 5];
```

### 6. Destructuring Assignment
Extracting values from arrays or objects:

```javascript
// Array destructuring
let [first, second] = [1, 2, 3];

// Object destructuring
let { name, age } = { name: 'John', age: 30, city: 'New York' };
```

### 7. Block Scope with `let` and `const`
More precise variable declarations:

```javascript
// `let` is block-scoped
if (true) {
    let x = 10;
    const y = 20;
}
// x and y are not accessible outside the block
```

### 8. Modules
Organizing and sharing code:

```javascript
// math.js
export function add(a, b) {
    return a + b;
}

// main.js
import { add } from './math.js';
```

### 9. Classes
Object-oriented programming syntax:

```javascript
class Person {
    constructor(name, age) {
        this.name = name;
        this.age = age;
    }

    sayHello() {
        console.log(`Hello, I'm ${this.name}`);
    }
}
```

### 10. Promises
Handling asynchronous operations:

```javascript
let promise = new Promise((resolve, reject) => {
    let success = true;
    if (success) {
        resolve('Operation successful');
    } else {
        reject('Operation failed');
    }
});
```

### 11. `Map` and `Set`
New data structures:

```javascript
// Map
let map = new Map();
map.set('key1', 'value1');
map.set('key2', 'value2');

// Set
let set = new Set([1, 2, 3, 3, 4]);
// set now contains [1, 2, 3, 4]
```

## Other Advanced JavaScript Concepts

### 1. Functional Programming
Programming paradigm focused on pure functions and immutability:

```javascript
// Pure function (same input always produces same output)
const multiply = (a, b) => a * b;

// Immutable approach
const numbers = [1, 2, 3, 4];
const doubled = numbers.map(num => num * 2);  // Creates new array

// Function composition
const compose = (f, g) => x => f(g(x));
const addTwo = x => x + 2;
const multiplyByThree = x => x * 3;
const addThenMultiply = compose(multiplyByThree, addTwo);
```

### 2. Currying
Transforming a function with multiple arguments into a sequence of functions:

```javascript
// Regular function
function add(a, b, c) {
    return a + b + c;
}

// Curried version
function curriedAdd(a) {
    return function(b) {
        return function(c) {
            return a + b + c;
        }
    }
}

// Or with arrow functions
const curriedAddArrow = a => b => c => a + b + c;

console.log(curriedAdd(1)(2)(3));  // 6
```

### 3. Memoization
Caching function results to improve performance:

```javascript
function memoize(fn) {
    const cache = {};
    return function(...args) {
        const key = JSON.stringify(args);
        if (key in cache) {
            return cache[key];
        }
        const result = fn.apply(this, args);
        cache[key] = result;
        return result;
    }
}

// Fibonacci with memoization
const fibonacciMemo = memoize(function(n) {
    if (n <= 1) return n;
    return fibonacciMemo(n - 1) + fibonacciMemo(n - 2);
});
```

### 4. Recursion
Function calling itself to solve a problem:

```javascript
// Factorial calculation
function factorial(n) {
    // Base case
    if (n === 0 || n === 1) {
        return 1;
    }
    // Recursive case
    return n * factorial(n - 1);
}

// Tree traversal example
function traverseTree(node) {
    if (!node) return;
    
    console.log(node.value);
    node.children.forEach(traverseTree);
}
```

### 5. Mutable vs Immutable
Understanding data modification:

```javascript
// Mutable (original array is changed)
let mutableArray = [1, 2, 3];
mutableArray.push(4);

// Immutable (new array created)
let immutableArray = [1, 2, 3];
let newArray = [...immutableArray, 4];

// Immutable object update
let person = { name: 'John', age: 30 };
let updatedPerson = { ...person, age: 31 };
```

### 6. `strict` Mode
Enforcing stricter parsing and error handling:

```javascript
'use strict';

// Prevents accidental global variables
function strictFunction() {
    // 'x = 10' would throw an error
    let x = 10;
}

// Catches silent errors
function strictModeDemo() {
    // Throws error instead of silently failing
    Object.defineProperty(this, 'x', { value: 0, writable: false });
    // this.x = 10;  // Would throw an error in strict mode
}
```

### 7. Garbage Collection
Automatic memory management:

```javascript
function createObject() {
    // Local object will be garbage collected 
    // when function execution completes
    let tempObject = {
        largeData: new Array(1000000)
    };
}

// Manual hints (though not directly controllable)
let obj = { key: 'value' };
obj = null;  // Helps garbage collector
```

### 8. Debugging
Various debugging techniques:

```javascript
// Console methods
console.log('Simple logging');
console.warn('Warning message');
console.error('Error message');
console.table([{a: 1}, {a: 2}]);  // Tabular output

// Performance measurement
console.time('Loop');
for(let i = 0; i < 1000000; i++) {}
console.timeEnd('Loop');
```

### 9. Performance Optimization
Improving code efficiency:

```javascript
// Avoiding repeated DOM queries
const element = document.getElementById('myElement');

// Using local variables in loops
const len = largeArray.length;
for(let i = 0; i < len; i++) {
    // More efficient than checking length each iteration
}

// Debouncing expensive operations
function debounce(func, delay) {
    let timeoutId;
    return function() {
        const context = this;
        const args = arguments;
        clearTimeout(timeoutId);
        timeoutId = setTimeout(() => func.apply(context, args), delay);
    };
}
```

### 10. Polyfills
Adding modern functionality to older browsers:

```javascript
// Polyfill for Array.prototype.includes
if (!Array.prototype.includes) {
    Array.prototype.includes = function(searchElement /*, fromIndex*/) {
        return this.indexOf(searchElement) !== -1;
    };
}
```

### 11. `typeof` and `instanceof`
Type checking:

```javascript
console.log(typeof 42);  // "number"
console.log(typeof "hello");  // "string"
console.log(typeof undefined);  // "undefined"

class Animal {}
class Dog extends Animal {}
let dog = new Dog();

console.log(dog instanceof Dog);  // true
console.log(dog instanceof Animal);  // true
```

### 12. `eval()`
Executing string as code (use with extreme caution):

```javascript
// Dangerous and not recommended
let result = eval('2 + 2');  // 4

// Security risk - never use with untrusted input
```

### 13. Microtasks and Macrotasks
Understanding JavaScript's execution queue:

```javascript
// Microtask (Promise)
Promise.resolve().then(() => {
    console.log('Microtask');
});

// Macrotask (setTimeout)
setTimeout(() => {
    console.log('Macrotask');
}, 0);

console.log('Synchronous');
// Likely output: Synchronous, Microtask, Macrotask
```

## Design Patterns

### 1. Singleton Pattern
Ensuring only one instance of a class:

```javascript
class Singleton {
    constructor() {
        if (Singleton.instance) {
            return Singleton.instance;
        }
        Singleton.instance = this;
        this.data = [];
    }

    static getInstance() {
        if (!Singleton.instance) {
            Singleton.instance = new Singleton();
        }
        return Singleton.instance;
    }
}
```

### 2. Factory Pattern
Creating objects without specifying exact class:

```javascript
class Animal {
    speak() {
        console.log('Animal sound');
    }
}

class Dog extends Animal {
    speak() {
        console.log('Woof!');
    }
}

class Cat extends Animal {
    speak() {
        console.log('Meow!');
    }
}

class AnimalFactory {
    createAnimal(type) {
        switch(type) {
            case 'dog': return new Dog();
            case 'cat': return new Cat();
            default: return new Animal();
        }
    }
}
```

### 3. Observer Pattern
Defining a one-to-many dependency:

```javascript
class Subject {
    constructor() {
        this.observers = [];
    }

    addObserver(observer) {
        this.observers.push(observer);
    }

    notifyObservers(data) {
        this.observers.forEach(observer => observer.update(data));
    }
}

class Observer {
    update(data) {
        console.log('Received update:', data);
    }
}
```

### 4. Module Pattern
Encapsulating code:

```javascript
const myModule = (function() {
    // Private variables and functions
    let privateVar = 'I am private';

    function privateMethod() {
        console.log(privateVar);
    }

    // Public interface
    return {
        publicMethod: function() {
            privateMethod();
        }
    };
})();
```

### 5. Revealing Module Pattern
Similar to module pattern, but explicitly defines public methods:

```javascript
const revealingModule = (function() {
    let privateVar = 'Private variable';

    function privateMethod() {
        console.log(privateVar);
    }

    function publicMethod() {
        privateMethod();
    }

    return {
        publicMethod: publicMethod
    };
})();
```
