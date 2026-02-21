# Data Types

[← Back to Topics](../README.md)

---

### 💡 Two Categories

JavaScript has **primitive** and **reference** types.

### Primitive Types (Immutable)

| Type | Example | Notes |
|------|---------|-------|
| `String` | `'hello'`, `"world"` | Text |
| `Number` | `42`, `3.14`, `NaN` | Integers & floats (no separate types) |
| `Boolean` | `true`, `false` | Logical values |
| `undefined` | `undefined` | Variable declared but not assigned |
| `null` | `null` | Intentional absence of value |
| `BigInt` | `9007199254740991n` | For very large integers |
| `Symbol` | `Symbol('id')` | Unique identifiers |

```javascript
let name = 'Alice';        // String
let age = 25;              // Number
let isOnline = true;       // Boolean
let address = undefined;   // Undefined
let salary = null;         // Null
```

### Reference Types (Mutable)

| Type | Example |
|------|---------|
| `Object` | `{ name: 'Alice' }` |
| `Array` | `[1, 2, 3]` |
| `Function` | `function() {}` |

```javascript
const user = { name: 'Alice' };  // Object
const nums = [1, 2, 3];          // Array
const greet = () => 'Hi!';       // Function
```

### 🔑 typeof Operator

Use `typeof` to check a value's type:

```javascript
typeof 'hello'     // 'string'
typeof 42          // 'number'
typeof true        // 'boolean'
typeof undefined   // 'undefined'
typeof null        // 'object'  ⚠️ This is a known JS bug!
typeof [1, 2]      // 'object'  ⚠️ Arrays are objects
typeof {}          // 'object'

// Better way to check for arrays
Array.isArray([1, 2]); // true
```

### 🔑 Type Coercion

JavaScript will **automatically convert** types in certain situations — this can be confusing:

```javascript
// String + Number = String (concatenation)
'5' + 3        // '53' (not 8!)

// Other operators convert to Number
'5' - 3        // 2
'5' * 2        // 10

// Equality gotchas
0 == false      // true  ⚠️ (loose equality)
0 === false     // false ✅ (strict equality)
'' == false     // true  ⚠️
null == undefined // true ⚠️
```

### 📝 Rule of Thumb

> Always use `===` (strict equality) instead of `==` to avoid coercion bugs.

---

[← Back to Topics](../README.md)
