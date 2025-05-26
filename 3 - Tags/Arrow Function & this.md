**Topic**: [[React]]

## 🔸 Explanation:

Arrow functions **do not have their own `this`**.  
They **inherit `this` from the surrounding (lexical) scope** where they're defined.  
Useful when you want to preserve context, like in callbacks.

---

## ✅ Use When:
- You want to keep the value of `this`
- In callbacks like setTimeout, map, or inside React components

---
## 📌 Example 1: Arrow function preserves `this`

```ts
const user = {
  name: "Rick",
  greet() {
    const sayHi = () => console.log("Hi, I'm " + this.name)
    sayHi()  // ✅ "Hi, I'm Rick"
  }
}
```

---
## 📌 Example 2: Regular function loses \`this\`

```tsx
const user = {
  name: "Rick",
  greet() {
    function sayHi() {
      console.log("Hi, I'm " + this.name)
    }
    sayHi()  // ❌ "Hi, I'm undefined"
  }
}
```

---

## 📌 Example 3: setTimeout with arrow function

```ts
const timer = {
  name: "Timer",
  start() {
    setTimeout(() => {
      console.log(this.name)  // ✅ "Timer"
    }, 1000)
  }
}
```

---

## 🧠 Summary Flashcard:

| Term            | Description                                 |
| --------------- | ------------------------------------------- |
| `this` in arrow | Inherited from the enclosing function scope |
| Best for        | Callbacks, event handlers, React components |
| Avoid when      | You need dynamic \`this\` (e.g. in methods) |
