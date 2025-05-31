**Topic**: [[React]]

📌React lifecycle methods are functions you can use at specific stages of a component’s life (mounting, updating, unmounting) to control behavior and side effects.

There are two types of components in React:
1. Class Components (use traditional lifecycle methods)
2. Function Components (including arrow function components, use hooks like useEffect)

Class Components vs Function (Arrow) Components
==================================================

- Class Components use lifecycle methods such as:
  - componentDidMount
  - componentDidUpdate
  - componentWillUnmount

- Function Components use React hooks (e.g., useEffect) to simulate lifecycle behavior.

Example of a class component:

 ```jsx
import react from "react";

class mycomponent extends react.component {
  constructor(props) {
    super(props);
    this.state = { count: 0 };
    console.log("constructor called");
 }

  componentdidmount() console.log("component mounted");

  componentdidupdate() console.log("component updated");

  componentwillunmount() console.log("component will unmount");

  render() return <h1>hello, react!</h1>;
}
```

Example of a function (arrow) component:

 ```jsx
import React, { useEffect, useState } from "react";

const MyComponent = () => {
  const [count, setCount] = useState(0);

  useEffect(() => {
    console.log("Component mounted");

    return () => {
      console.log("Component will unmount");
    };
  }, []);

  useEffect(() => {
    console.log("Component updated");
  }, [count]);

  return (
    <div>
      <p>{count}</p>
      <button onClick={() => setCount(count + 1)}>Increment</button>
    </div>
  );
};
 ```

Summary
==================================================

- ✅ Yes, arrow function components are valid React components.
- 🧠 They are called "function components" and use hooks instead of lifecycle methods.
- 🛠️ `useEffect` is used in place of `componentDidMount`, `componentDidUpdate`, and `componentWillUnmount`.
