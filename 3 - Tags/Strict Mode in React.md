**Topic**: [[React]]

[[React Strict Mode Double Invoking vs Canceling First Render]]

```scss
[⬆️ Initial Render] ──▶ [⬇️ Unmount] ──▶ [⬆️ Second Render]
     (useEffect)           (cleanup)        (useEffect again)
```
---
In `StrictMode`, React **intentionally double-invokes** in development only:

- `render()`
- `useEffect`
- `useState` initializers
- Class component lifecycle methods (`constructor`, `componentDidMount`, etc.)
---
```jsx
//Example:
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
