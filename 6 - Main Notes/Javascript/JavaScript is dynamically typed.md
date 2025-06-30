📌 JavaScript is dynamically typed. This means that the same variable can be used to hold **different** data.

```run-js
let x;

x = 5
console.log(typeof(x))

x = "Hello"
console.log(typeof(x))

x = true
console.log(typeof(x))

x = new Promise(()=> {});
console.log(typeof(x))

x = {name: "Rick"}
console.log(typeof(x))
```

→ [[JavaScript]]