**Topic**: [[React]] [[React Hooks]]

📌 Holds a mutable `.current` value that persists across renders.
 - Useful for accessing DOM nodes or storing mutable values without causing re-renders.
 
## Example

```jsx
import { useRef } from 'react';

function FocusInput() {
  const inputRef = useRef();
  return (
    <>
      <input ref={inputRef} />
      <button onClick={() => inputRef.current.focus()}>Focus</button>
    </>
  );
}
