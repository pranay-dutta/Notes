# 📘 JavaScript Functions: Declaration, Expression & Arrow

## 🔹 1. Function Declaration

Also called **function statement**.

```run-js
function greet(name) {
  return `Hello, ${name}!`;
}
console.log(greet("Rick")); // Hello, Rick!
```

✅ **Hoisted** — Can be called before they are defined.

---

## 🔹 2. Function Expression

Assigning a function to a variable.

 ```run-js
const greet = function(name) {
  return `Hi, ${name}`;
};
console.log(greet("Dutta")); // Hi, Dutta
```

❌ **Not hoisted** — Must be defined before use.

Can be:
- **Anonymous** (as above)
- **Named** (useful for recursion/debugging):

 ```js
const factorial = function fact(n) {
  return n <= 1 ? 1 : n * fact(n - 1);
};
 ```

---

## 🔹 3. Arrow Functions

Shorter syntax introduced in ES6.

 ```js
const greet = (name) => {
  return `Hey, ${name}`;
};
console.log(greet("ChatGPT")); // Hey, ChatGPT
```

### 🧠 Shortcut (for one-liners):

```js
const square = x => x * x;
 ```

### ⚠️ Key Differences:
| Feature            | Arrow Function                | Regular Function                            |
| ------------------ | ----------------------------- | ------------------------------------------- |
| `this` binding     | Lexical (`this` is inherited) | Dynamic (`this` depends on how it's called) |
| `arguments` object | ❌ Not available               | ✅ Available                                 |
| Syntax             | Concise                       | Verbose                                     |
|                    |                               |                                             |
[[Arguments Object in JavaScript]]

---
## 🔚 Summary

| Type                 | Hoisted | `this` Binding | Syntax                 |
| -------------------- | ------- | -------------- | ---------------------- |
| Function Declaration | ✅       | Dynamic        | `function x()`         |
| Function Expression  | ❌       | Dynamic        | `const x = function()` |
| Arrow Function       | ❌       | Lexical        | `const x = () =>`      |

→ [[JavaScript]]