# Objects

[← Back to Topics](../README.md)

---

### 💡 What Are Objects?

Objects are collections of **key-value pairs**. They're the fundamental building block for structuring data in JavaScript.

### Creating Objects

```javascript
// Object literal (most common)
const user = {
  name: 'Alice',
  age: 25,
  isAdmin: true
};

// Shorthand property names
const name = 'Alice';
const age = 25;
const user = { name, age }; // Same as { name: name, age: age }
```

### Accessing Properties

```javascript
const user = { name: 'Alice', age: 25 };

// Dot notation (preferred)
user.name;    // 'Alice'

// Bracket notation (for dynamic keys)
user['name']; // 'Alice'

const key = 'age';
user[key];    // 25
```

### Adding & Modifying Properties

```javascript
const user = { name: 'Alice' };

user.age = 25;            // Add new property
user.name = 'Bob';        // Modify existing
user['role'] = 'Admin';   // Bracket notation

delete user.role;          // Remove a property
```

### 🔑 Object Methods

```javascript
const user = { name: 'Alice', age: 25, role: 'Admin' };

Object.keys(user);    // ['name', 'age', 'role']
Object.values(user);  // ['Alice', 25, 'Admin']
Object.entries(user);  // [['name','Alice'], ['age',25], ['role','Admin']]
```

### 🔑 Computed Property Names

Use expressions as object keys:

```javascript
const field = 'email';

const user = {
  name: 'Alice',
  [field]: 'alice@mail.com'  // key is 'email'
};
// { name: 'Alice', email: 'alice@mail.com' }
```

### 🔑 Methods (Functions in Objects)

```javascript
// Old way
const calc = {
  add: function(a, b) { return a + b; }
};

// Modern shorthand ✅
const calc = {
  add(a, b) { return a + b; },
  subtract(a, b) { return a - b; }
};

calc.add(2, 3); // 5
```

### 🔑 Checking Properties

```javascript
const user = { name: 'Alice', age: 25 };

'name' in user;                    // true
'email' in user;                   // false
user.hasOwnProperty('name');       // true
```

### 🔑 Cloning Objects

```javascript
const original = { name: 'Alice', scores: [90, 85] };

// Shallow copy (nested objects still share references!)
const copy1 = { ...original };
const copy2 = Object.assign({}, original);

// Deep copy (fully independent)
const deep = structuredClone(original);
```

> ⚠️ Spread `...` only does a **shallow copy**. Nested objects and arrays are still shared.

### 🔑 Object Freezing

```javascript
const config = Object.freeze({
  apiUrl: 'https://api.example.com',
  timeout: 5000
});

config.apiUrl = 'changed'; // ❌ Silently fails (or error in strict mode)
```

---

[← Back to Topics](../README.md)
