**Topic**: [[React]] [[React Hooks]]
# 🌀 React Query (TanStack Query)

<img src="react-query.png" width=200 style="border-radius: 10px" />

React Query is a **powerful data-fetching and caching library** for React.  
It helps you manage **server state** easily—fetching, caching, updating, and syncing data with minimal boilerplate.

---
## 🌟 Why Use React Query?

- ✅ Handles loading, error, and success states automatically
- 🚀 Caches data and keeps it fresh with background updates
- 🔄 Auto-refetches stale data when needed
- 🎯 Reduces manual useEffect + useState code
- 🛠 Devtools for debugging queries/mutations
- 💥 Works with any API (REST/GraphQL)

---

## ⚒️ Key Hooks: `useQuery` vs `useMutation`

| Feature        | `useQuery`                             | `useMutation`                             |
|----------------|------------------------------------------|--------------------------------------------|
| Purpose        | **Fetch (GET)** data                    | **Send/modify (POST/PUT/DELETE)** data     |
| Trigger        | Auto on mount or key change             | Manual (e.g., button click, form submit)   |
| Caching        | ✅ Yes (auto)                            | ❌ No (but can invalidate queries manually) |
| State Handling | ✅ Built-in (loading, error, etc.)      | ✅ Built-in                                 |
| Example        | Fetching user list                      | Adding a new user                          |
### `useQuery` Example

```tsx
const { data, isLoading } = useQuery({
  queryKey: ['users'],
  queryFn: () => fetch('/api/users').then(res => res.json())
})
```
### `useMutation` Example

```tsx
const mutation = useMutation({
  mutationFn: (newUser) =>
    fetch('/api/users', {
      method: 'POST',
      body: JSON.stringify(newUser),
    }),
})
```

## 🧠 Remember This

> **"useQuery = fetch data"**  
> **"useMutation = send data"**  
> **React Query = smart server state management 🔥**