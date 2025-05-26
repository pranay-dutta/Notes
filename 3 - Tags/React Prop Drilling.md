**Topic**: [[React]]

🤔 [[Prop Drilling vs React Context API]]

👎**Prop Drilling** is the process where you **pass data** from a **parent** component to a **deeply nested child** component 
through **intermediate components** that do not need the data themselves.

This often leads to **cluttered code** and makes it **harder to maintain**, especially in large applications.

```ts
function App() {
  return <Parent />;
}

function Parent() {
  const user = "Rick";
  return <Child user={user} />;
}

function Child({ user }) {
  return <GrandChild user={user} />;
}

function GrandChild({ user }) {
  return <h1>Hello, {user}!</h1>;
}

Here, `user` is passed from `Parent` → `Child` → `GrandChild`, even though only `GrandChild` needs it.
```

