## ✅ Pure Function

- Always returns the **same output** for the same input.
- **No side effects** (doesn’t modify external state, I/O, etc.).

```cpp
int add(int a, int b) return a + b;
```

❌ Impure Function
- May return different outputs for same inputs.
- Has side effects (e.g., modifies global variables, logs output).

cpp
Copy
Edit
int x = 0;
int addAndLog(int a, int b) {
    std::cout << a + b;
    x++;
    return a + b;
}
✅ Pure Component (React)
Renders same UI for the same props/state.

No side effects during render.

tsx
Copy
Edit
function Greeting({ name }) {
  return <h1>Hello, {name}</h1>;
}
❌ Impure Component (React)
Depends on or mutates external state.

May cause side effects.

tsx
Copy
Edit
let count = 0;
function Greeting({ name }) {
  count++;
  return <h1>Hello, {name}</h1>;
}
🧠 Summary
Type	Pure	Impure
Function	Deterministic, no side effects	Varies output, has side effects
Component	Predictable render, isolated	Affected by external state

vbnet
Copy
Edit
