```run-js
let x = 16 + "Volvo"
console.log(x); //output: 16Volvo
/*
	JavaScript will treat the example above as:
	let x = "16" + "Volvo";
*/
```

> 📌 When adding a number and a string, JavaScript will treat the number as a string

```run-js
let x = "volvo" + 16
console.log(x) //output: volvo16
```

---

> 📌JavaScript evaluates expressions from left to right. Different sequences can produce different results:

```run-js
let x = 16 + 4 + "Volvo"; 
console.log(x) //output: 20Volvo
```

```run-js
let x =  "Volvo" + 16 + 24
console.log(x) //output: Volvo1620
```

```run-js
let x = 16 + "Volvo" + 4 
console.log(x) //output: 16Volvo4
```

[[JavaScript]]