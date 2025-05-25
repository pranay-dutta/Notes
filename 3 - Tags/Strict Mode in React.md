### 🛡️Strict Mode 
- **Strict mode** renders a component **twice** to catch **impure functions** in **development** mode.

```scss
[⬆️ Initial Render] ──▶ [⬇️ Unmount] ──▶ [⬆️ Second Render]
     (useEffect)           (cleanup)        (useEffect again)
```

## ❓ Does React Cancel the First Render in Strict Mode?

**No**, React does **not cancel** the first render.  
Instead, in **development mode only**, React **intentionally re-renders** components to help you catch potential bugs.

---
## 🔁 What Really Happens?

In `StrictMode`, React **intentionally double-invokes**:

- `render()`
- `useEffect`
- `useState` initializers
- Class component lifecycle methods (`constructor`, `componentDidMount`, etc.)

This only happens in **development** and **does not affect production builds**.

---
## 🧪 Example:

```jsx
function MyComponent() {
  useEffect(() => {
    console.log("Mounted");
    return () => console.log("Unmounted");
  }, []);

  return <div>Hello</div>;
}

export default function App() {
  return (
    <React.StrictMode>
      <MyComponent />
    </React.StrictMode>
  );
}
//Output: ---
//Mounted
//Unmounted
//Mounted
```


