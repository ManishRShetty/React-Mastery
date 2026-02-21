# Variables

[← Back to Topics](../README.md)

---

### 💡 What Are Variables?

Variables are **containers for storing data**. JavaScript has three ways to declare them.

### `var` — The Old Way ❌

```javascript
var name = 'Alice';
var name = 'Bob'; // ✅ No error — can re-declare (dangerous!)
name = 'Charlie'; // ✅ Can re-assign
```

- **Function-scoped** (not block-scoped)
- Can be re-declared and re-assigned
- Gets **hoisted** to the top of its scope

> ⚠️ Avoid `var` in modern code. It leads to hard-to-find bugs.

### `let` — For Values That Change ✅

```javascript
let count = 0;
count = 1;        // ✅ Can re-assign
let count = 2;    // ❌ Error — cannot re-declare
```

- **Block-scoped** `{ }`
- Can be re-assigned, but **not** re-declared

### `const` — For Values That Don't Change ✅

```javascript
const PI = 3.14159;
PI = 3;           // ❌ Error — cannot re-assign
const PI = 3;     // ❌ Error — cannot re-declare
```

- **Block-scoped** `{ }`
- Cannot be re-assigned or re-declared
- ⚠️ Objects & arrays declared with `const` can still be **mutated**:

```javascript
const user = { name: 'Alice' };
user.name = 'Bob'; // ✅ This works — the reference didn't change
user = {};          // ❌ Error — can't reassign the variable
```

### 🔑 Scope Comparison

```javascript
if (true) {
  var a = 1;   // function-scoped — leaks out
  let b = 2;   // block-scoped — stays inside
  const c = 3; // block-scoped — stays inside
}

console.log(a); // 1 ✅
console.log(b); // ❌ ReferenceError
console.log(c); // ❌ ReferenceError
```

### 📝 Rule of Thumb

> Use `const` by default. Use `let` only when you need to re-assign. Never use `var`.

---

[← Back to Topics](../README.md)
