# Spread & Rest Operators

[← Back to Topics](../README.md)

---

### 💡 What Are They?

Both use the `...` syntax but do opposite things:
- **Spread** `...` → **Expands** an array/object into individual elements
- **Rest** `...` → **Collects** individual elements into an array/object

### Spread Operator — Expanding ✅

#### With Arrays

```javascript
const nums = [1, 2, 3];

// Copy an array
const copy = [...nums]; // [1, 2, 3]

// Merge arrays
const all = [...nums, 4, 5]; // [1, 2, 3, 4, 5]
const merged = [...nums, ...[4, 5]]; // [1, 2, 3, 4, 5]

// Pass array as function arguments
Math.max(...nums); // 3
```

#### With Objects

```javascript
const user = { name: 'Alice', age: 25 };

// Copy an object
const copy = { ...user }; // { name: 'Alice', age: 25 }

// Merge objects (later properties overwrite earlier ones)
const updated = { ...user, age: 26, role: 'Admin' };
// { name: 'Alice', age: 26, role: 'Admin' }
```

> ⚠️ Spread only does a **shallow copy** — nested objects/arrays are still shared by reference.

### Rest Operator — Collecting ✅

#### In Function Parameters

Collects remaining arguments into an array:

```javascript
const sum = (first, ...rest) => {
  console.log(first); // 1
  console.log(rest);  // [2, 3, 4]
  return rest.reduce((total, n) => total + n, first);
};

sum(1, 2, 3, 4); // 10
```

#### In Destructuring

Collects remaining properties:

```javascript
// With objects
const { name, ...rest } = { name: 'Alice', age: 25, role: 'Admin' };
// name = 'Alice'
// rest = { age: 25, role: 'Admin' }

// With arrays
const [first, ...others] = [1, 2, 3, 4];
// first = 1
// others = [2, 3, 4]
```

### 🔑 Common Patterns

```javascript
// Remove a property immutably
const user = { name: 'Alice', age: 25, password: 'secret' };
const { password, ...safeUser } = user;
// safeUser = { name: 'Alice', age: 25 }

// Add to array without mutation
const todos = ['task1', 'task2'];
const newTodos = [...todos, 'task3'];

// Update item in array without mutation
const items = [1, 2, 3, 4];
const updated = items.map(item => item === 2 ? 20 : item);
// [1, 20, 3, 4]
```

---

[← Back to Topics](../README.md)
