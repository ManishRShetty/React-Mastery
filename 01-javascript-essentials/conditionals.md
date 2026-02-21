# Conditionals

[← Back to Topics](../README.md)

---

### 💡 What Are Conditionals?

Conditionals let your code **make decisions** — run different blocks depending on a condition.

### if / else if / else

```javascript
const score = 85;

if (score >= 90) {
  console.log('A grade');
} else if (score >= 80) {
  console.log('B grade');
} else if (score >= 70) {
  console.log('C grade');
} else {
  console.log('Needs improvement');
}
// Output: 'B grade'
```

### Ternary Operator

A compact `if/else` that **returns a value** — very common in React's JSX:

```javascript
const age = 20;

// Instead of if/else:
const label = age >= 18 ? 'Adult' : 'Minor';
```

Nested ternary (use sparingly):

```javascript
const status = score >= 90 ? 'A' : score >= 80 ? 'B' : 'C';
```

### switch

Best for comparing **one value** against many possible matches:

```javascript
const day = 'Monday';

switch (day) {
  case 'Monday':
  case 'Tuesday':
  case 'Wednesday':
  case 'Thursday':
  case 'Friday':
    console.log('Weekday');
    break;
  case 'Saturday':
  case 'Sunday':
    console.log('Weekend');
    break;
  default:
    console.log('Invalid day');
}
```

### 🔑 Truthy & Falsy Values

JavaScript treats some values as `false` in boolean contexts:

```javascript
// ❌ Falsy values (evaluate to false)
false, 0, -0, '', "", ``, null, undefined, NaN

// ✅ Everything else is truthy, including:
true, 1, -1, 'hello', [], {}, function() {}
```

```javascript
const name = '';

if (name) {
  console.log('Has name');
} else {
  console.log('No name');  // ← This runs ('' is falsy)
}
```

### 🔑 Logical Assignment

Modern shorthand for conditional assignments:

```javascript
let user = null;

// Old way
if (!user) user = 'Guest';

// Modern way
user ??= 'Guest';   // Assign if null/undefined
user ||= 'Guest';   // Assign if falsy
user &&= 'Admin';   // Assign if truthy
```

---

[← Back to Topics](../README.md)
