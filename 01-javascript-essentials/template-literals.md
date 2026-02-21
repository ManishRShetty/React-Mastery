# Template Literals

[← Back to Topics](../README.md)

---

### 💡 What Are Template Literals?

Template literals use **backticks** `` ` `` instead of quotes and let you embed expressions directly inside strings.

### The Old Way ❌

```javascript
const name = 'Alice';
const age = 25;

const greeting = 'Hello, ' + name + '! You are ' + age + ' years old.';
```

### The Modern Way ✅

```javascript
const name = 'Alice';
const age = 25;

const greeting = `Hello, ${name}! You are ${age} years old.`;
```

### 🔑 Key Features

#### Expressions Inside `${}`

You can put **any JavaScript expression** inside `${}`:

```javascript
const price = 19.99;
const qty = 3;

`Total: $${price * qty}`;        // 'Total: $59.97'
`Status: ${age >= 18 ? 'Adult' : 'Minor'}`; // 'Status: Adult'
`Items: ${[1,2,3].join(', ')}`;  // 'Items: 1, 2, 3'
```

#### Multi-Line Strings

No more `\n` or string concatenation for multi-line:

```javascript
// Old way ❌
const html = '<div>\n' +
  '  <h1>Hello</h1>\n' +
  '</div>';

// Template literal ✅
const html = `
  <div>
    <h1>Hello</h1>
  </div>
`;
```

#### Nested Templates

```javascript
const items = ['apple', 'banana', 'cherry'];

const list = `
  <ul>
    ${items.map(item => `<li>${item}</li>`).join('')}
  </ul>
`;
```

### 🔑 Tagged Templates (Advanced)

Functions that process template literals:

```javascript
const highlight = (strings, ...values) => {
  return strings.reduce((result, str, i) => {
    return result + str + (values[i] ? `<mark>${values[i]}</mark>` : '');
  }, '');
};

const name = 'Alice';
highlight`Hello, ${name}!`; // 'Hello, <mark>Alice</mark>!'
```

---

[← Back to Topics](../README.md)
