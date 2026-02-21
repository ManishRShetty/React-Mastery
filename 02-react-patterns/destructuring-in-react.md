# Destructuring in React

[← Back to Topics](../README.md)

---

### 💡 Why It Matters in React

In React, **destructuring** is used *everywhere* — to extract data from `props`, `state`, context, and hook return values — without repetitive dot notation like `props.user.name`.

### Destructuring Props

**Before — Messy ❌**

```jsx
const UserCard = (props) => {
  return `User: ${props.user.name}, Age: ${props.user.age}`;
};
```

**After — Clean ✅**

```jsx
const UserCard = ({ user: { name, age } }) => {
  return `User: ${name}, Age: ${age}`;
};
```

> **What changed?** Instead of receiving the entire `props` object and drilling into it with dot notation, we destructure `user` from props and then further destructure `name` and `age` from `user` — all in the function signature.

### Destructuring Hook Returns

React hooks return arrays — destructuring makes them usable:

```jsx
// useState returns [value, setter]
const [count, setCount] = useState(0);

// useReducer returns [state, dispatch]
const [state, dispatch] = useReducer(reducer, initialState);
```

### Destructuring Context

```jsx
const { theme, toggleTheme } = useContext(ThemeContext);
```

### 🏋️ Drill: Refactor This Component

Take this component and refactor it to destructure props cleanly:

```jsx
// ❌ Before
const ProfileHeader = (props) => {
  return (
    <div>
      <h1>{props.name}</h1>
      <p>{props.bio}</p>
      <span>{props.location}</span>
    </div>
  );
};

// ✅ After
const ProfileHeader = ({ name, bio, location }) => {
  return (
    <div>
      <h1>{name}</h1>
      <p>{bio}</p>
      <span>{location}</span>
    </div>
  );
};
```

---

[← Back to Topics](../README.md)
