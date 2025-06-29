**Topic**: [[JavaScript]]

A **Promise** is an object representing the **eventual completion (or failure)** of an **asynchronous operation** and its resulting value.

<img src="promise-in-javascript.png" width=500 style="border-radius: 10px" />

**States of a Promise:**

1. `pending` – Initial state, neither fulfilled nor rejected.
2. `fulfilled` – The operation completed successfully.
3. `rejected` – The operation failed.

```run-js
let promise = new Promise((resolve, reject) => {   
	// async code 
});
console.log(promise); //state: pending

let p2 = new Promise((_, rej)=> {
	resolve("p2 resolved")
})
p2.then((res)=> console.log(res)).catch((err)=> console.log("Error": err))

let p3 = new Promise((_, rej)=> {
	resolve(new Error("p3 rejected")) //Always reject the promoise with an e
})
p2.then((res)=> console.log(res)).catch((err)=> console.log("Error": err))

```
