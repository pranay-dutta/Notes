
React Router is a standard library for routing in React. It enables navigation among views of various components in a React Application, 
allows changing the browser URL, and keeps the UI in sync with the URL.

🌟 Just [Read The Official Docs](https://reactrouter.com/home) 
 
> Core Concepts:
```ts
1. <BrowserRouter> –// Wraps the app and enables routing via HTML5 history API.
2. <Routes> – //A container for all <Route> elements.
3. <Route path="..." element={<Component />} /> – //Defines which component should render for a specific path.
4. <Link to="..."> – //Used to navigate between routes without reloading the page.
```

---
> Hooks:
```ts
1. useNavigate() – //A hook to programmatically navigate to a route.
2. useParams() – //A hook to access URL parameters.
3. useLocation() – //Gives access to the current location object.
```

```tsx
import { BrowserRouter, Routes, Route, Link } from 'react-router-dom';

function App() {
  return (
    <BrowserRouter>
      <nav>
        <Link to="/">Home</Link>
        <Link to="/about">About</Link>
      </nav>
      <Routes>
        <Route path="/" element={<Home />} />
        <Route path="/about" element={<About />} />
      </Routes>
    </BrowserRouter>
  );
}
```
