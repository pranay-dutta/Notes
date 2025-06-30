📌 Type coercion means conversation of **one datatype to another by JavaScript** during operations.

- **Implicit Type Conversion (Coercion):** Implicit Type Conversion occurs automatically by the JavaScript.

# Examples or Type Coercion
---
## 1. String + Number

When we add a **string** with the **number**, the **JavaScript** **automatically** **converts** the number into a string and **performs string concatenation.**

```run-js
let n = 5
let s = "5"
let res = n + s; //n gets coerced to string

console.log(typeof res, res);
```

---
## 2. Boolean to Number

When we perform the mathematical operations, then JavaScript automatically converts true to 1 and false to 0

```run-js
let res = true + 1;



```

→ [[Practicing Type Coercion in JavaScript]]
