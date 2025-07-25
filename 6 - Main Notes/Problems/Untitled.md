# 

## ❌ Problem

When testing components that use `useNavigate()` from `react-router-dom`, you might see this error:

> `useNavigate() may be used only in the context of a <Router> component.`

---

## 🔍 Why It Happens

### ✅ App Code
Uses:

//```tsx
<RouterProvider router={router} />
//```

- `router` is created using `createBrowserRouter()` or similar
- Designed for **real browser navigation**

### ❌ In Test Code
If you're also wrapping with `<RouterProvider>` (intended for the full app), then:

- Routing context may be **missing or mismatched**
- `useNavigate()` fails
- You may also be duplicating router contexts

---

## ✅ Solution

- Remove `<RouterProvider>` from your shared `Providers.tsx`
- Use `<MemoryRouter>` in your test utilities (MemoryRouter = test-safe)
- Wrap components like this in your test setup:

//```tsx
<MemoryRouter>
  <Providers>
    <YourComponent />
  </Providers>
</MemoryRouter>
//```

---

## ✅ Updated `Providers.tsx`

Make it generic (no hardcoded router):

//```tsx
const Providers = ({ children }: { children: React.ReactNode }) => (
  <QueryClientProvider client={queryClient}>
    <Provider defaultTheme="light">
      {children}
      <ReactQueryDevtools />
    </Provider>
  </QueryClientProvider>
);
//```

---

## ✅ Updated `renderSetup.tsx` (Test Utility)

//```tsx
import { render, screen } from "@testing-library/react";
import userEvent from "@testing-library/user-event";
import { MemoryRouter } from "react-router-dom";
import Providers from "@/providers";

function setup(jsx: React.ReactElement) {
  return {
    user: userEvent.setup(),
    ...render(
      <MemoryRouter>
        <Providers>{jsx}</Providers>
      </MemoryRouter>
    ),
  };
}

export { screen, setup };
//```

---

## ✅ Summary

- `RouterProvider` is for real routing (don't use in tests)
- `MemoryRouter` is lightweight and test-safe
- Always wrap your tested components with a **single valid `<Router>` context**

---

Let me know if you want to include redirects, route params, or mocking `useNavigate()` in tests too!
