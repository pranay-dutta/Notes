**Hoisting** is a JavaScript behavior where variable declarations are move to the  top of their **containing scope**. 

However, the way **hoisting** works **differs** for **var,** **let** and **const**

## Hoisting with var 
- The variable **x** is **hoisted** but only initialized after the *console.log(x)* call.
prints **undefined** because it is declared but not **assigned** a value yet.

```run-js
console.log(a)
var a = 5 //undefined
```
