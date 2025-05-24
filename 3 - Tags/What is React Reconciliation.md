### 🧠 React Reconciliation – Remember with “**R-D-C-U**”

> **R**e-render → **D**iff → **C**alculate → **U**pdate

---

### 🔁 What is it?

When state/props change, React:

1. **R**e-renders the Virtual DOM.
    
2. **D**iffs it with the old Virtual DOM.
    
3. **C**alculates the minimal changes.
    
4. **U**pdates the Real DOM efficiently.
    

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