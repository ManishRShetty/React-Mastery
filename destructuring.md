# Topic 1: Destructuring

[← Back to Topics](./README.md)

---

### 💡 Why It Matters in React

In React, **destructuring** is used *everywhere* — to extract data from `props`, `state`, context, and hook return values — without repetitive dot notation like `props.user.name`.

### The Old Way ❌

Manually assigning each property to a variable is verbose and error-prone:

```javascript
const user = { id: 1, name: 'SARA', role: 'ADMIN' };

// Tedious, repetitive dot notation
const name = user.name;
const role = user.role;
```

### The Modern Way ✅

Destructuring lets you pull out exactly what you need in a single, clean line:

```javascript
const user = { id: 1, name: 'SARA', role: 'ADMIN' };

// Clean & concise
const { name, role } = user;
```

### 🔑 Key Patterns

#### 1. Object Destructuring (Most Common in React)

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

#### 3. Array Destructuring (Used with Hooks)

```javascript
// React's useState returns an array
const [count, setCount] = useState(0);

// Skip values you don't need
const [, , third] = [1, 2, 3];
```

### 🏋️ Drill: Refactor Props

The component below accesses props the messy way. **Refactor** it to use destructuring directly in the parameter list.

**Before — Messy ❌**

```jsx
const UserCard = (props) => {
  return `User: ${props.user.name}, Age: ${props.user.age}`;
};
```

**After — Clean ✅**

```jsx
const UserCard = ({ user: { name, age } }) => {
  return `User: ${name}, Age: ${age}`;
};
```

> **What changed?** Instead of receiving the entire `props` object and drilling into it with dot notation, we destructure `user` from props and then further destructure `name` and `age` from `user` — all in the function signature.

---

[← Back to Topics](./README.md)
