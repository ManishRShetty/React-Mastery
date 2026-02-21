# Error Handling

[← Back to Topics](../README.md)

---

### 💡 Why Handle Errors?

Unhandled errors **crash your app**. Proper error handling keeps your application running and gives users helpful feedback.

### try / catch / finally

```javascript
try {
  // Code that might fail
  const data = JSON.parse('invalid json');
} catch (error) {
  // Runs if an error occurs
  console.error('Parse failed:', error.message);
} finally {
  // Always runs, regardless of success or failure
  console.log('Cleanup done');
}
```

### Throwing Errors

```javascript
const divide = (a, b) => {
  if (b === 0) {
    throw new Error('Cannot divide by zero');
  }
  return a / b;
};

try {
  divide(10, 0);
} catch (error) {
  console.error(error.message); // 'Cannot divide by zero'
}
```

### Error Types

```javascript
// Built-in error types
new Error('Generic error');
new TypeError('Expected a string');
new RangeError('Value out of range');
new ReferenceError('Variable not defined');
new SyntaxError('Invalid syntax');
```

### 🔑 Async Error Handling

#### With async/await

```javascript
const fetchData = async () => {
  try {
    const res = await fetch('https://api.example.com/data');

    if (!res.ok) {
      throw new Error(`HTTP Error: ${res.status}`);
    }

    const data = await res.json();
    return data;
  } catch (error) {
    console.error('Fetch failed:', error.message);
    return null; // Return a fallback value
  }
};
```

#### With Promises

```javascript
fetch('https://api.example.com/data')
  .then(res => {
    if (!res.ok) throw new Error(`HTTP ${res.status}`);
    return res.json();
  })
  .then(data => console.log(data))
  .catch(error => console.error(error.message));
```

### 🔑 Custom Errors

```javascript
class ValidationError extends Error {
  constructor(field, message) {
    super(message);
    this.name = 'ValidationError';
    this.field = field;
  }
}

const validateAge = (age) => {
  if (age < 0) {
    throw new ValidationError('age', 'Age cannot be negative');
  }
};

try {
  validateAge(-5);
} catch (error) {
  if (error instanceof ValidationError) {
    console.error(`${error.field}: ${error.message}`);
    // 'age: Age cannot be negative'
  }
}
```

### 🔑 Optional catch Binding

If you don't need the error object:

```javascript
try {
  JSON.parse('bad');
} catch {
  console.log('Parse failed'); // No (error) needed
}
```

### 📝 Best Practices

| ✅ Do | ❌ Don't |
|-------|----------|
| Catch specific errors | Catch and silently ignore |
| Provide fallback values | Let the app crash |
| Log meaningful messages | Use generic "Error occurred" |
| Use `finally` for cleanup | Forget to release resources |
| Throw early, catch late | Wrap everything in try/catch |

---

[← Back to Topics](../README.md)
