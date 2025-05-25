**Topic**: [[React]]

---
✅ **Pure Function**

- Always returns the **same output** for the same input.
- **No side effects** (doesn’t modify external state, I/O, etc.).

```cpp
int add(int a, int b) return a + b;
```
---
❌ **Impure Function**

- May return **different outputs** for **same inputs**. (returns different output if given same input).
- Has **side effects**.

```cpp
int x = 0;
int addWithX(int a, int b) return a + b + x++;
```
---
✅ **Pure Component (React)**

- **Renders** same UI for the **same props/state**.
- **No side effects** during render.

``` tsx
function Greeting({ name }) {
  return <h1>Hello, {name}</h1>;
}
```
---
❌ **Impure Component (React)**

- Depends on or **mutates** external state.
- May cause **side effects**.

```jsx
let count = 0;
function Greeting({ name }) {
  count++;
  return <h1>Hello, {name}</h1>;
}
```
---
🧠 **Summary**

| Aspect                 | Pure                     | Impure                       |
| ---------------------- | ------------------------ | ---------------------------- |
| **Functions**          | Same input → same output | May vary output              |
|                        | No side effects          | Has side effects             |
| **Components (React)** | Deterministic render     | May depend on external state |
|                        | No mutations in render   | May cause side effects       |
