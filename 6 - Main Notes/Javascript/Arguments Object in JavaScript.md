### ✅ Regular function example

```run-js
function showArgs() {
	console.log(arguments)
	console.log(arguments[0])
	console.log(arguments.length)
}
showArgs("Rick", 42, true);
```

---
### ❌ Not available in arrow functions

```run-js
const showArgs = () => {
	console.log(arguments) //ReferenceError: arguments is not defined
}
showArgs("Rick")
```

### ✅ How to handle arguments in arrow functions?

Use **rest parameters** instead:

```run-js
const showArgs = (...args) => {
  console.log(args); // ['Rick', 42, true]
};

showArgs("Rick", 42, true);
```

--- 

| Feature        | Regular Function | Arrow Function  |
| -------------- | ---------------- | --------------- |
| `arguments`    | ✅ Available      | ❌ Not available |
| Rest `...args` | ✅ Works          | ✅ Works         |

→ [[JavaScript]]