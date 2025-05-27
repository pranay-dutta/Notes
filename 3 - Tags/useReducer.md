# Create a .txt file explaining the useReducer hook with code blocks commented out using //

✅ What is useReducer Hook?

`useReducer` is a React Hook used for managing complex state logic in functional components.
It is an alternative to `useState` and is often preferable when:
- The state logic involves multiple sub-values.
- The next state depends on the previous one.
- You want a cleaner and more scalable structure for managing state.

It is inspired by the reducer pattern found in Redux.

🔹 Syntax:
// ```js
// const [state, dispatch] = useReducer(reducer, initialState);
// ```

- `reducer`: A function that takes the current state and an action, and returns the new state.
- `initialState`: The initial value of the state.
- `dispatch`: A function to send actions to the reducer.

🔸 Example:
// ```js
// import React, { useReducer } from 'react';

// const initialState = { count: 0 };

// function reducer(state, action) {
//   switch (action.type) {
//     case 'increment':
//       return { count: state.count + 1 };
//     case 'decrement':
//       return { count: state.count - 1 };
//     default:
//       return state;
//   }
// }

// function Counter() {
//   const [state, dispatch] = useReducer(reducer, initialState);

//   return (
//     <div>
//       <p>Count: {state.count}</p>
//       <button onClick={() => dispatch({ type: 'increment' })}>+</button>
//       <button onClick={() => dispatch({ type: 'decrement' })}>-</button>
//     </div>
//   );
// }
// ```

📝 Summary:
- `useReducer` helps manage complex or interrelated state transitions.
- It separates logic from component UI, making code easier to maintain.
"""

# Save the content to a .txt file
file_path = "/mnt/data/useReducer_note.txt"
with open(file_path, "w") as file:
    file.write(content)

file_path
