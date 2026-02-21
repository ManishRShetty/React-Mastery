# Destructuring

[← Back to Topics](../README.md)

---

### 💡 What Is It?

**Destructuring** lets you extract values from objects and arrays into distinct variables in a single, clean statement — instead of repetitive dot notation.

### The Old Way ❌

```javascript
const user = { id: 1, name: 'SARA', role: 'ADMIN' };

// Tedious, repetitive dot notation
const name = user.name;
const role = user.role;
```

### The Modern Way ✅

```javascript
const user = { id: 1, name: 'SARA', role: 'ADMIN' };

// Clean & concise
const { name, role } = user;
```

### 🔑 Key Patterns

#### 1. Object Destructuring

```javascript
// Basic
const { name, role } = user;

// With renaming
const { name: userName, role: userRole } = user;

// With default values
const { name, role = 'USER' } = user;
```

#### 2. Nested Destructuring

```javascript
const company = {
  name: 'Acme',
  address: { city: 'Mumbai', zip: '400001' }
};

const { address: { city, zip } } = company;
console.log(city); // 'Mumbai'
```

#### 3. Array Destructuring

```javascript
const [first, second] = [10, 20];

// Skip values you don't need
const [, , third] = [1, 2, 3];
```

---

[← Back to Topics](../README.md)
