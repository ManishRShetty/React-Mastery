# Loops

[← Back to Topics](../README.md)

---

### 💡 What Are Loops?

Loops let you **repeat a block of code** multiple times.

### for Loop

The classic loop — best when you know how many iterations you need:

```javascript
for (let i = 0; i < 5; i++) {
  console.log(i); // 0, 1, 2, 3, 4
}
```

### while Loop

Runs as long as the condition is `true`:

```javascript
let count = 0;

while (count < 3) {
  console.log(count); // 0, 1, 2
  count++;
}
```

### do...while Loop

Runs **at least once**, then checks the condition:

```javascript
let num = 5;

do {
  console.log(num); // 5 (runs once even though condition is false)
  num++;
} while (num < 5);
```

### for...of — Iterate Over Values ✅

Best for arrays, strings, and other iterables:

```javascript
const colors = ['red', 'green', 'blue'];

for (const color of colors) {
  console.log(color); // 'red', 'green', 'blue'
}

// Works on strings too
for (const char of 'Hello') {
  console.log(char); // 'H', 'e', 'l', 'l', 'o'
}
```

### for...in — Iterate Over Keys

Best for **objects** (avoid using on arrays):

```javascript
const user = { name: 'Alice', age: 25, role: 'Admin' };

for (const key in user) {
  console.log(`${key}: ${user[key]}`);
}
// name: Alice
// age: 25
// role: Admin
```

### 🔑 Loop Control

```javascript
// break — exit the loop entirely
for (let i = 0; i < 10; i++) {
  if (i === 5) break;
  console.log(i); // 0, 1, 2, 3, 4
}

// continue — skip current iteration
for (let i = 0; i < 5; i++) {
  if (i === 2) continue;
  console.log(i); // 0, 1, 3, 4
}
```

### 📝 Quick Reference

| Loop | Best For |
|------|----------|
| `for` | Known number of iterations |
| `while` | Unknown iterations, condition-based |
| `for...of` | Arrays, strings, iterables |
| `for...in` | Object keys |
| `.forEach()` | Array method (see [Arrays](./arrays.md)) |
| `.map()` | Transform arrays (see [Arrays](./arrays.md)) |

---

[← Back to Topics](../README.md)
