# React `useContext` Hook

## 📌 What is `useContext`?
`useContext` is a React hook that lets you consume values from a Context without wrapping in a `<Consumer>`.

---
```tsx
const value = useContext(MyContext);
```
---
## ✅ When to Use
- Avoid prop drilling (passing props through many layers).
- Share global data like theme, user info, auth, language, etc.
---
### 1. Create Context

```ts
import { createContext } from 'react';
export const ThemeContext = createContext('light');
```

### 2. Provide Context

```ts
<ThemeContext value="dark">
  <App />
</ThemeContext>
```

### 3. Consume Context

```ts
import { useContext } from 'react';
import { ThemeContext } from './ThemeContext';

function Button() {
  const theme = useContext(ThemeContext);
  return <button className={theme}>Click me</button>;
}
```
---
## ⚠️ Notes
- Context only updates components that **use it**.
- Don’t overuse: not for everything. Only for shared global state.
- `useContext` does **not** trigger re-renders if the parent re-renders *unless* the context value changes.

---
## 🧠 Best Practices
- Use **separate contexts** for unrelated state (e.g., ThemeContext, AuthContext).
- Memoize value passed to `<Provider>` to avoid unnecessary renders.

```ts
<ThemeContext.Provider value={useMemo(() => theme, [theme])}>
  <App />
</ThemeContext.Provider>
```

### [[React context Optimizing re-renders when passing objects and functions]]
