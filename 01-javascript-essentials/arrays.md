# Arrays & Array Methods

[← Back to Topics](../README.md)

---

### 💡 What Are Arrays?

Arrays are **ordered lists** of values. They are one of the most used data structures in React.

### Creating Arrays

```javascript
const fruits = ['apple', 'banana', 'cherry'];
const mixed = [1, 'hello', true, null, { id: 1 }];
const empty = [];
```

### Accessing & Modifying

```javascript
const colors = ['red', 'green', 'blue'];

colors[0];          // 'red' (first item)
colors[2];          // 'blue' (third item)
colors.length;      // 3
colors[1] = 'lime'; // Replace 'green' with 'lime'
```

### 🔑 Essential Methods

#### Adding & Removing

```javascript
const arr = [1, 2, 3];

arr.push(4);      // [1, 2, 3, 4]    — Add to end
arr.pop();        // [1, 2, 3]       — Remove from end
arr.unshift(0);   // [0, 1, 2, 3]    — Add to start
arr.shift();      // [1, 2, 3]       — Remove from start
arr.splice(1, 1); // [1, 3]          — Remove 1 item at index 1
```

#### Searching

```javascript
const fruits = ['apple', 'banana', 'cherry', 'banana'];

fruits.indexOf('banana');     // 1 (first occurrence)
fruits.lastIndexOf('banana'); // 3 (last occurrence)
fruits.includes('cherry');    // true
fruits.find(f => f.startsWith('c'));      // 'cherry'
fruits.findIndex(f => f.startsWith('c')); // 2
```

### 🔑 Iteration Methods (Crucial for React)

#### `.map()` — Transform Each Item ⭐

Returns a **new array** with transformed items. Used constantly in React to render lists:

```javascript
const nums = [1, 2, 3];
const doubled = nums.map(n => n * 2);
// [2, 4, 6]
```

#### `.filter()` — Keep Matching Items ⭐

Returns a **new array** with only items that pass the test:

```javascript
const nums = [1, 2, 3, 4, 5];
const evens = nums.filter(n => n % 2 === 0);
// [2, 4]
```

#### `.reduce()` — Accumulate Into One Value

```javascript
const nums = [1, 2, 3, 4];
const sum = nums.reduce((total, n) => total + n, 0);
// 10
```

#### `.forEach()` — Do Something With Each Item

```javascript
const fruits = ['apple', 'banana'];
fruits.forEach(fruit => console.log(fruit));
// 'apple'
// 'banana'
```

> ⚠️ `.forEach()` returns `undefined` — use `.map()` when you need a new array.

#### `.some()` & `.every()`

```javascript
const nums = [1, 2, 3, 4, 5];

nums.some(n => n > 4);  // true  — At least one matches
nums.every(n => n > 0); // true  — All match
```

### 🔑 Non-Mutating Methods (Safe for React State)

```javascript
const arr = [3, 1, 2];

// These return NEW arrays (original unchanged)
arr.slice(0, 2);            // [3, 1]
[...arr].sort();            // [1, 2, 3]
[...arr].reverse();         // [2, 1, 3]
arr.concat([4, 5]);         // [3, 1, 2, 4, 5]
arr.flat();                 // Flattens nested arrays
```

### 📝 Quick Reference

| Method | Mutates? | Returns | Used For |
|--------|----------|---------|----------|
| `.map()` | No | New array | Transforming data |
| `.filter()` | No | New array | Filtering data |
| `.reduce()` | No | Single value | Aggregating data |
| `.forEach()` | No | `undefined` | Side effects |
| `.find()` | No | Item or `undefined` | Finding one item |
| `.some()` | No | `boolean` | Any match? |
| `.every()` | No | `boolean` | All match? |
| `.push()` | **Yes** | New length | Adding items |
| `.splice()` | **Yes** | Removed items | Removing items |
| `.sort()` | **Yes** | Sorted array | Sorting |

---

[← Back to Topics](../README.md)
