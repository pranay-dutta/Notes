
📌When using **Server-Side Rendering (SSR)** or **Static Site Generation (SSG)** in Next.js, the page is first rendered on the **server** and then sent to the **browser** as HTML.

But HTML alone can't handle interactivity like:
- Button clicks
- Form inputs
- Animations
- React state

───────────────────────────────
🔄 **What is Hydration?**
───────────────────────────────

> Hydration is the process where React takes over the static HTML sent from the server and adds interactivity to it by attaching event listeners and making it a fully functional React app on the client side.

1️⃣ **Server** renders static HTML using SSR or SSG:

```html
<div>
  <h1>Welcome, Rick</h1>
  <button>Click Me</button>
</div>
```

2️⃣ **Browser** receives HTML & loads React JS bundle:

```
Server                Browser
  │                      │
  │ ──> HTML ───────────>│
  │                      │
  │                      ▼
  │               Renders static HTML (no interactivity yet)
  │                      ▼
  │             Loads JS → React takes control (Hydration)
  │                      ▼
  │         Now: Button clicks, useEffect, state = ✅
```

────────────────────────────────────
⚙️ **What Happens During Hydration?**  
────────────────────────────────────

✅ React:

- Parses the static HTML
- Reuses the DOM already on screen
- Attaches JavaScript event listeners
- Initializes internal state
- Activates dynamic logic (like `useEffect`, `useState`, etc.)