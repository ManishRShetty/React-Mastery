# Operators

[← Back to Topics](../README.md)

---

### 💡 What Are Operators?

Operators perform operations on values. Here are the essential ones.

### Arithmetic Operators

```javascript
5 + 3    // 8   — Addition
5 - 3    // 2   — Subtraction
5 * 3    // 15  — Multiplication
5 / 3    // 1.66— Division
5 % 3    // 2   — Remainder (Modulo)
5 ** 3   // 125 — Exponentiation
```

### Assignment Operators

```javascript
let x = 10;
x += 5;   // x = 15  (same as x = x + 5)
x -= 3;   // x = 12
x *= 2;   // x = 24
x /= 4;   // x = 6
x %= 4;   // x = 2
```

### Comparison Operators

```javascript
5 == '5'    // true  — Loose equality (type coercion ⚠️)
5 === '5'   // false — Strict equality (no coercion ✅)
5 != '5'    // false — Loose inequality
5 !== '5'   // true  — Strict inequality
5 > 3       // true
5 < 3       // false
5 >= 5      // true
5 <= 4      // false
```

### Logical Operators

```javascript
true && true     // true  — AND (both must be true)
true || false    // true  — OR (at least one must be true)
!true            // false — NOT (inverts the value)
```

### 🔑 Short-Circuit Evaluation

Logical operators don't always evaluate both sides:

```javascript
// && returns the first falsy value, or the last value
0 && 'hello'        // 0 (stopped at falsy)
'hi' && 'hello'     // 'hello' (both truthy, returns last)

// || returns the first truthy value, or the last value
0 || 'fallback'     // 'fallback'
'value' || 'other'  // 'value'
```

### 🔑 Nullish Coalescing (`??`)

Returns the right side **only** if the left side is `null` or `undefined`:

```javascript
null ?? 'default'      // 'default'
undefined ?? 'default' // 'default'
0 ?? 'default'         // 0 (0 is not null/undefined!)
'' ?? 'default'        // '' (empty string is not null/undefined!)

// Compare with ||
0 || 'default'         // 'default' (0 is falsy)
'' || 'default'        // 'default' ('' is falsy)
```

### 🔑 Optional Chaining (`?.`)

Safely access deeply nested properties without crashing:

```javascript
const user = { address: { city: 'Mumbai' } };

user.address.city       // 'Mumbai'
user.phone.number       // ❌ TypeError: Cannot read property of undefined
user.phone?.number      // undefined ✅ (no crash)
```

### Ternary Operator

A shorthand `if/else` that returns a value:

```javascript
const age = 20;
const status = age >= 18 ? 'Adult' : 'Minor';
// status = 'Adult'
```

---

[← Back to Topics](../README.md)
