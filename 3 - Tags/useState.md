# ⚛️ React State Update Batching

React batches state updates inside event handlers to avoid unnecessary re-renders and improve performance.


## ✅ Correct Behavior
When calling `setState` multiple times inside an event handler, React combines (batches) the updates and performs **a single re-render** after the handler finishes.

### 🧪 Example:

```jsx
import React, { useState } from 'react';

function Counter() {
  const [count, setCount] = useState(0);

  const handleClick = () => {
    setCount(count + 1);
    setCount(count + 2);
    setCount(count + 3);
    console.log('Clicked!');
	// Even though 3 setState calls are made, React may batch them and only re-render once.
  };

  return <button onClick={handleClick}>Count: {count}</button>;
}