>**Re-render** → **Diff** → **Calculate** → **Update**
---
<img src="placeholder" width=500 style="border-radius: 10px" />

### 🔁 What is it?

When state/props change, React:

1. **Re-renders** the Virtual DOM.
2. **Diffs** it with the old Virtual DOM.
3. **Calculates** the minimal changes.
4. **Updates** the Real DOM efficiently.

---
### 🎯 Why?

- Direct DOM changes are **slow**.
- Virtual DOM + diffing = **fast updates**.

---
### 🧩 Key Concepts to Lock In:

- **Keys** help track list items → Avoid wrong deletions.
- **Same component type** → React reuses it.
- **Different component type** → React replaces it.

---
### 📝 Quick Trigger Word:

**"React Really Doesn’t Change Unnecessarily"**
> Think of it like: "React is smart — it avoids extra work!"

---
### 🌟Key Optimizations in Reconciliation:

- **Keys**: When rendering lists, React uses `key` props to identify which items changed, were added, or removed.
- **Component Type Check**: If a component’s type changes (`<A />` to `<B />`), React destroys the old one and creates a new one.
- **Same Component**: If it’s the same component with different props/state, React tries to update it in place (instead of re-creating).