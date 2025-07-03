Conditionals are way to write certain parts of the code conditionally.

📌 **if else** 

```run-js
let score = 92
if(score >= 90) {
	console.log("pass");
} else {
	consol.log("fail")
}
```

📌**switch**

```run-js
const subject = "English";
switch(subject) {
	case "Bengali": {
		console.log("Bengali");
		break;
	}
	
	case "English": {
		console.log("English");
		break;
	}
	
	default: {
		console.log("No subject mentioned");
		break;
	}
}
```