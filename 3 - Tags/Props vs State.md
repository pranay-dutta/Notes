**Topic**: [[React]]

| Props                                                  | State                                                     |
| ------------------------------------------------------ | --------------------------------------------------------- |
| Input passed **to** a component (from parent)          | Data managed **within** the component itself              |
| Like a **function parameter**                          | Like a **local variable** that persists and updates       |
| **Immutable** (read-only from the component’s view)    | **Mutable** (can be updated with `setState` or Hooks)     |
| Updating props causes **child component** to re-render | Updating state causes the **same component** to re-render |
## Example Pseudocode 

```jsx
function Parent() {
  pass name="Rick" to Child
}

function Child(props) {
  state: age = 20

  display: props.name      // using prop
  display: age             // using state

  onClick: set age + 1     // update state
}
```

🤔Know about [[React Prop Drilling]]