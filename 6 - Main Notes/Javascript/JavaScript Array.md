### 📘 Arrays in JavaScript

- An **array** is a list-like object used to store **multiple values** in a single variable.
- Arrays can hold **any data type**, even mixed types.


```run-js
const arr = [2, "3", { name: "John" }, [1, 2, 3], true, null];
console.log(arr[0]); // 'apple'`
console.log(arr.length); // 3`

for(const element of arr) {
	console.log(element);
}
```

- Arrays are **dynamic**—you can change, add, or remove items.
- Use `.length` to get the number of elements.
- You can loop over arrays using `for`, `for...of`, etc.

→ [[JavaScript]]