## 🔎 Summary

- React does **not cancel** the first render.
- It **runs the full mount → unmount → re-mount cycle** in development under `StrictMode`.
- This is called **double invocation**, and it helps you write **resilient components**.

> 🛠️ Dev only: This behavior does **not** happen in production builds.

---

| 🔍 Behavior                 | Description                                                                | Happens in Dev? | Happens in Prod? | Purpose                                                  |
| --------------------------- | -------------------------------------------------------------------------- | --------------- | ---------------- | -------------------------------------------------------- |
| ✅ First Render              | React mounts the component and runs all effects.                           | ✅ Yes           | ✅ Yes            | Normal mounting behavior                                 |
| 🔁 Unmount After First      | React immediately unmounts the component after first mount.                | ✅ Yes           | ❌ No             | Test cleanup and remount safety                          |
| 🔁 Second Render (Re-mount) | React mounts the component again (render + effects).                       | ✅ Yes           | ❌ No             | Ensures side-effects are safe and cleanup logic is solid |
| ❌ Cancel First Render       | ⚠️ This does **NOT** happen — React doesn’t skip or undo the first render. | ❌ No            | ❌ No             | Misconception — render actually completes fully          |

