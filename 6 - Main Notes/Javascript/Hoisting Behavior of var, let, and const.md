**Hoisting** is a JavaScript behavior where variable declarations are move to the  top of their **containing scope**. 

However, the way **hoisting** works **differs** for **var,** **let** and **const**

---
## 📌 hoisting with var 

 The variable **x** is **hoisted** but only initialized after the *console.log(x)* call.
prints **undefined** because it is declared but not **assigned** a value yet.

```run-js
console.log(x) //output: undefined
var x = 5 
```

--- 
## 📌 hoisting with let

The code logs **x** before it is declared with let, causing **Reference Error**. This happens because **let variables** are hoisted but **not initialized**, so they remain in **Temporal Dead Zone(TDZ)** until the **declaration** is executed.

```run-js
console.log(x)
let x=10
```

---
## 📌 hoisting with const

	The variable **x** is declared with const, which is **block-scoped**. when 