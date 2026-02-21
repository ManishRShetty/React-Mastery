# Promises & Async/Await

[← Back to Topics](../README.md)

---

### 💡 What Is Asynchronous Code?

JavaScript is **single-threaded** — it can only do one thing at a time. Async code lets you start a long-running task (like fetching data) without blocking everything else.

### Callbacks (The Old Way ❌)

```javascript
// "Callback hell" — nested and hard to read
getData(function(a) {
  processData(a, function(b) {
    saveData(b, function(c) {
      console.log('Done!');
    });
  });
});
```

### Promises (Better ✅)

A Promise represents a future value — it's either **pending**, **fulfilled**, or **rejected**.

```javascript
const fetchUser = () => {
  return new Promise((resolve, reject) => {
    setTimeout(() => {
      const user = { name: 'Alice' };
      resolve(user);      // ✅ Success
      // reject('Error'); // ❌ Failure
    }, 1000);
  });
};
```

#### Consuming Promises with `.then()` / `.catch()`

```javascript
fetchUser()
  .then(user => console.log(user.name))  // 'Alice'
  .catch(error => console.error(error))
  .finally(() => console.log('Done'));    // Always runs
```

#### Chaining Promises

```javascript
fetch('https://api.example.com/user')
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error(error));
```

### Async / Await (Best ✅✅)

Syntactic sugar over Promises — reads like synchronous code:

```javascript
const getUser = async () => {
  try {
    const response = await fetch('https://api.example.com/user');
    const data = await response.json();
    console.log(data);
  } catch (error) {
    console.error('Failed:', error);
  } finally {
    console.log('Done');
  }
};
```

> `await` **pauses** the function until the Promise resolves. It can only be used inside an `async` function.

### 🔑 Parallel Execution

When tasks are independent, run them in **parallel** instead of sequentially:

```javascript
// ❌ Sequential (slow) — each waits for the previous
const user = await fetchUser();
const posts = await fetchPosts();

// ✅ Parallel (fast) — both start at the same time
const [user, posts] = await Promise.all([
  fetchUser(),
  fetchPosts()
]);
```

### 🔑 Promise Utilities

```javascript
// Wait for ALL to succeed
const results = await Promise.all([p1, p2, p3]);

// Wait for the FIRST to settle (succeed or fail)
const fastest = await Promise.race([p1, p2, p3]);

// Wait for ALL to settle, get status of each
const outcomes = await Promise.allSettled([p1, p2, p3]);
// [{ status: 'fulfilled', value: ... }, { status: 'rejected', reason: ... }]

// First to SUCCEED (ignores rejections)
const first = await Promise.any([p1, p2, p3]);
```

### 📝 Quick Reference

| Concept | Syntax |
|---------|--------|
| Create a promise | `new Promise((resolve, reject) => { ... })` |
| Consume with .then | `promise.then(val => ...).catch(err => ...)` |
| Async function | `const fn = async () => { ... }` |
| Await a promise | `const result = await promise` |
| Parallel execution | `await Promise.all([p1, p2])` |
| Error handling | `try { await ... } catch (e) { ... }` |

---

[← Back to Topics](../README.md)
