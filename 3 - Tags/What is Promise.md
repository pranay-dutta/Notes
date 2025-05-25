**Topic**: [[JavaScript]]

A **Promise** is an object representing the **eventual completion (or failure)** of an **asynchronous operation** and its resulting value.
<img src="javascript-promise.png" width=300 style="border-radius: 10px" />

**States of a Promise:**

1. `pending` – Initial state, neither fulfilled nor rejected.
2. `fulfilled` – The operation completed successfully.
3. `rejected` – The operation failed.

```js
let promise = new Promise((resolve, reject) => {   
	// async code 
});
```

