📌 Type conversion means, converting **one data type** to another **data type** manually by the *programmer*.

---
## 1. String to Number

We can covert a string into numbers using the *Number() function*, *parseInt()* and *parseFlot() methods.*

```run-js
let s = "123.33"

let x = Number(s);
let y = parseInt(s);
let z = parseFloat(s);

console.log("x:",x, "y:",y, "z:",z)
```

---
## 2. Number to String

We can covert a number into a string using *String()* function or we can *concat it with an empty string  "", or toString method*


```run-js
let n = 123

let s1 = String(n)
let s2 = n + ""
let s3 = n.toString()


console.log("type:", typeof s1, "value:", s1);
console.log("type:", typeof s2, "value:", s2);
console.log("type:", typeof s3, "value:", s3);
```


## 3. Boolean to Number