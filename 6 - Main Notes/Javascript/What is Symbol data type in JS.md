 📌A `Symbol` is a **unique, hidden value** used mostly as an **object property key** — 
 and it **won’t conflict** with other keys.

**Think like this way**
> "I want to add something to an object, but I don’t want it to interfere with or be seen by others."

```run-js
const id = Symbol("id");
const id2 = Symbol("id");


const user = { name: "Jhon", id: 22 };

user[id] = 2e9;
user[id2] = 3e9; 

console.log(user)
console.log(user.id)
console.log(user[id])
console.log(user[id2])

```

→ [[JavaScript]]