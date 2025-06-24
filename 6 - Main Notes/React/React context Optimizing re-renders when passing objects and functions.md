
==========================================
 Optimizing re-renders when passing objects
 and functions via useContext in React
 ==========================================
 Source: https://react.dev/reference/react/useContext#optimizing-re-renders-when-passing-objects-and-functions


✅ You can pass any values via context, including objects and functions:

 ```ts
function MyApp() {
  const [currentUser, setCurrentUser] = useState(null);

  function login(response) {
    storeCredentials(response.credentials);
    setCurrentUser(response.user);
  }

  return (
    <AuthContext value={{ currentUser, login }}>
      <Page />
    </AuthContext>
  );
}
 ```

## ⚠️ Problem:

Every time MyApp re-renders (e.g. on a route change), the `value` object and the `login` function are recreated,
causing all components using useContext(AuthContext) to re-render — even if currentUser hasn't changed.

## 🛠️ Optimization:

 Use `useCallback` for functions and `useMemo` for objects
 to avoid unnecessary re-renders:

```ts
import { useCallback, useMemo } from 'react';

function MyApp() {
  const [currentUser, setCurrentUser] = useState(null);

  const login = useCallback((response) => {
    storeCredentials(response.credentials);
    setCurrentUser(response.user);
  }, []);

  const contextValue = useMemo(
    () => ({
      currentUser,
      login,
    }),
    [currentUser, login]
  );

  return (
    <AuthContext value={contextValue}>
      <Page />
    </AuthContext>
  );
}
```

 ✅ Result:
 Now, components using useContext(AuthContext)
 will only re-render if `currentUser` changes.

🔗 Read more:
 useMemo → https://react.dev/reference/react/useMemo#skipping-re-rendering-of-components  
 useCallback → https://react.dev/reference/react/useCallback#skipping-re-rendering-of-components
