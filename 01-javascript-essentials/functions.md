# Functions

[← Back to Topics](../README.md)

---

### 💡 What Are Functions?

Functions are **reusable blocks of code** that perform a specific task.

### Function Declaration

```javascript
function greet(name) {
  return `Hello, ${name}!`;
}

greet('Alice'); // 'Hello, Alice!'
```

- ✅ **Hoisted** — can be called before it's defined in the code
- Has its own `this` context

### Function Expression

```javascript
const greet = function(name) {
  return `Hello, ${name}!`;
};

greet('Bob'); // 'Hello, Bob!'
```

- ❌ **Not hoisted** — must be defined before use
- Has its own `this` context

### Arrow Functions ✅ (Most Used in React)

```javascript
const greet = (name) => {
  return `Hello, ${name}!`;
};

// Short form — implicit return (single expression)
const greet = (name) => `Hello, ${name}!`;

// Single parameter — parentheses optional
const double = n => n * 2;

// No parameters — parentheses required
const sayHi = () => 'Hi!';
```

- ❌ **Not hoisted**
- ✅ **No own `this`** — inherits from parent scope (perfect for React)

### 🔑 Parameters & Arguments

```javascript
// Default parameters
const greet = (name = 'World') => `Hello, ${name}!`;
greet();        // 'Hello, World!'
greet('Alice'); // 'Hello, Alice!'

// Rest parameters — collect remaining args into an array
const sum = (...numbers) => {
  return numbers.reduce((total, n) => total + n, 0);
};
sum(1, 2, 3, 4); // 10
```

### 🔑 Callback Functions

A function passed as an argument to another function:

```javascript
const numbers = [1, 2, 3];

// The arrow function is a "callback"
numbers.forEach((num) => {
  console.log(num * 2); // 2, 4, 6
});

// Named callback
const double = (n) => n * 2;
const doubled = numbers.map(double); // [2, 4, 6]
```

### 🔑 Higher-Order Functions

Functions that **take or return** other functions:

```javascript
// Returns a function
const multiplier = (factor) => {
  return (number) => number * factor;
};

const double = multiplier(2);
const triple = multiplier(3);

double(5); // 10
triple(5); // 15
```

### 🔑 IIFE (Immediately Invoked Function Expression)

A function that runs as soon as it's defined:

```javascript
(() => {
  const secret = 'hidden';
  console.log(secret); // 'hidden'
})();

// secret is not accessible here
```

### 📝 Which One to Use?

| Type | Use When |
|------|----------|
| Arrow function `=>` | Default choice in modern JS/React |
| Function declaration | Need hoisting or `this` binding |
| Function expression | Assigning to a variable, no hoisting needed |

---

[← Back to Topics](../README.md)
