# Modules (import / export)

[← Back to Topics](../README.md)

---

### 💡 What Are Modules?

Modules let you **split code into separate files** and share functionality between them. React projects use modules everywhere.

### Named Exports

Export multiple things from a file:

```javascript
// math.js
export const PI = 3.14159;
export const add = (a, b) => a + b;
export const subtract = (a, b) => a - b;
```

```javascript
// app.js — import by exact name
import { PI, add } from './math.js';

add(2, 3); // 5
```

### Default Export

One default export per file:

```javascript
// Button.js
const Button = ({ label }) => `<button>${label}</button>`;
export default Button;
```

```javascript
// app.js — import with any name
import Button from './Button.js';
import MyButton from './Button.js'; // Also works — your choice of name
```

### 🔑 Mixing Named & Default

```javascript
// utils.js
export const formatDate = (d) => d.toLocaleDateString();
export const formatCurrency = (n) => `$${n.toFixed(2)}`;

const Utils = { formatDate, formatCurrency };
export default Utils;
```

```javascript
// Import both
import Utils, { formatDate } from './utils.js';
```

### 🔑 Renaming Imports

```javascript
import { add as sum, subtract as minus } from './math.js';

sum(2, 3);   // 5
minus(5, 2); // 3
```

### 🔑 Import Everything

```javascript
import * as Math from './math.js';

Math.add(2, 3);  // 5
Math.PI;         // 3.14159
```

### 🔑 Re-exporting

Barrel files combine exports from multiple modules:

```javascript
// components/index.js
export { default as Button } from './Button.js';
export { default as Card } from './Card.js';
export { default as Modal } from './Modal.js';
```

```javascript
// Now import from one place
import { Button, Card, Modal } from './components';
```

### 📝 Quick Reference

| Syntax | Use Case |
|--------|----------|
| `export const foo` | Named export |
| `export default foo` | Default export (one per file) |
| `import { foo }` | Import named export |
| `import Foo` | Import default export |
| `import { foo as bar }` | Rename on import |
| `import * as Mod` | Import all as namespace |
| `export { default } from` | Re-export |

---

[← Back to Topics](../README.md)
