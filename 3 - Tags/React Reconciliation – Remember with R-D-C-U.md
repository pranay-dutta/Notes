🧠 **Remember this with:** `R-D-C-U` ➟ `!React Doesn’t Change Unnecessarily`

When a component’s **state or props** change, React: 

| 🔑 Mnemonic | Step      | Description                                          |
| ----------- | --------- | ---------------------------------------------------- |
| **R**       | Re-render | React re-renders the **Virtual DOM**.                |
| **D**       | Diff      | Compares new Virtual DOM with the old one.           |
| **C**       | Calculate | Figures out the **minimal set of changes**.          |
| **U**       | Update    | Applies the changes efficiently to the **Real DOM**. |
## 🎯 Why is Reconciliation Important?

| Reason            | Description                                  |
| ----------------- | -------------------------------------------- |
| DOM is slow       | Direct DOM manipulation is expensive.        |
| Virtual DOM helps | React avoids full DOM updates using diffing. |
## 🧩 Key Concepts

| Concept                 | Description                                                  |
| ----------------------- | ------------------------------------------------------------ |
| **Keys** in lists       | Helps React track items → avoids wrong deletions or updates. |
| **Same component type** | React reuses the existing component instance.                |
| **Different type**      | React replaces it entirely with a new component.             |

### 🌟 Key Optimizations in Reconciliation

| Optimization             | Description                                                                  |
| ------------------------ | ---------------------------------------------------------------------------- |
| **Keys**                 | React uses `key` props in lists to track changes, additions, and removals.   |
| **Component Type Check** | If component type changes (`<A />` → `<B />`), React replaces it completely. |
| **Same Component**       | If type is the same, React updates in place with new props/state.            |












<div style="display: flex; align-items: flex-start; gap: 30px;">

<!-- Left section: All your tables and content -->
<div style="flex: 1;">

### 🧠 Remember this with: `R-D-C-U` ➟ `!React Doesn’t Change Unnecessarily`

When a component’s **state or props** change, React: 

| 🔑 Mnemonic | Step      | Description                                          |
| ----------- | --------- | ---------------------------------------------------- |
| **R**       | Re-render | React re-renders the **Virtual DOM**.                |
| **D**       | Diff      | Compares new Virtual DOM with the old one.           |
| **C**       | Calculate | Figures out the **minimal set of changes**.          |
| **U**       | Update    | Applies the changes efficiently to the **Real DOM**. |

---

### 🎯 Why is Reconciliation Important?

| Reason            | Description                                  |
| ----------------- | -------------------------------------------- |
| DOM is slow       | Direct DOM manipulation is expensive.        |
| Virtual DOM helps | React avoids full DOM updates using diffing. |

---

### 🧩 Key Concepts

| Concept                 | Description                                                  |
| ----------------------- | ------------------------------------------------------------ |
| **Keys** in lists       | Helps React track items → avoids wrong deletions or updates. |
| **Same component type** | React reuses the existing component instance.                |
| **Different type**      | React replaces it entirely with a new component.             |

---

### 🌟 Key Optimizations in Reconciliation

| Optimization             | Description                                                                  |
| ------------------------ | ---------------------------------------------------------------------------- |
| **Keys**                 | React uses `key` props in lists to track changes, additions, and removals.   |
| **Component Type Check** | If component type changes (`<A />` → `<B />`), React replaces it completely. |
| **Same Component**       | If type is the same, React updates in place with new props/state.            |

</div>

<!-- Right section: The image -->
<div style="flex: 0.8;">
  <img src="https://upload.wikimedia.org/wikipedia/commons/a/a7/React-icon.svg" alt="React Reconciliation" width="300">
</div>

</div>

