🧠 **Remember this with:** `R-D-C-U` ➟ `!React Doesn’t Change Unnecessarily`
When a component’s **state or props** change, React: 

<img src="react-reconciliation.png" width=500 style="border-radius: 10px" />

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