### Optimizing re-renders when passing objects and functions [](https://react.dev/reference/react/useContext#optimizing-re-renders-when-passing-objects-and-functions "Link for Optimizing re-renders when passing objects and functions")

You can pass any values via context, including objects and functions.

```
function MyApp() {  const [currentUser, setCurrentUser] = useState(null);  function login(response) {    storeCredentials(response.credentials);    setCurrentUser(response.user);  }  return (    <AuthContext value={{ currentUser, login }}>      <Page />    </AuthContext>  );}
```

Here, the context value is a JavaScript object with two properties, one of which is a function. Whenever `MyApp` re-renders (for example, on a route update), this will be a _different_ object pointing at a _different_ function, so React will also have to re-render all components deep in the tree that call `useContext(AuthContext)`.

In smaller apps, this is not a problem. However, there is no need to re-render them if the underlying data, like `currentUser`, has not changed. To help React take advantage of that fact, you may wrap the `login` function with [`useCallback`](https://react.dev/reference/react/useCallback) and wrap the object creation into [`useMemo`](https://react.dev/reference/react/useMemo). This is a performance optimization:

```
import { useCallback, useMemo } from 'react';function MyApp() {  const [currentUser, setCurrentUser] = useState(null);  const login = useCallback((response) => {    storeCredentials(response.credentials);    setCurrentUser(response.user);  }, []);  const contextValue = useMemo(() => ({    currentUser,    login  }), [currentUser, login]);  return (    <AuthContext value={contextValue}>      <Page />    </AuthContext>  );}
```

As a result of this change, even if `MyApp` needs to re-render, the components calling `useContext(AuthContext)` won’t need to re-render unless `currentUser` has changed.

Read more about [`useMemo`](https://react.dev/reference/react/useMemo#skipping-re-rendering-of-components) and [`useCallback`.](https://react.dev/reference/react/useCallback#skipping-re-rendering-of-components)