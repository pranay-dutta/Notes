In JavaScript, there are **five main types of loops**:
### 🔁 **1. `for` loop**

```js
for (let i = 0; i < 5; i++) { 
	console.log(i); 
}
```
---
### 🔁 **2. `while` loop**

```js
let i = 0; 
while (i < 5) {   
	console.log(i);   i++; 
}
```
---
 ### 🔁 **3. `do...while` loop**

```js
let i = 0; 
do {
	console.log(i);
	i++;
} while (i < 5);
```
---
### 🔁 **4. `for...of` loop**

Used to iterate over **iterables** like arrays, strings, etc.

```run-js
const arr = [12, 25, 35]; 
const str1 = "rickdutta"
for (const c of str1) console.log(c);
for(const x of arr) console.log(x)
```
---
### 🔁 **5. `for...in` loop**

Used to iterate over **object properties**.

```run-js
const obj = { catCount: 3, dogCount: 2 };
for (const key in obj) { 
	console.log(key, obj[key]); 
}
```

→ [[JavaScript]]