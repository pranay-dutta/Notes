# 📌 Template Literals in JavaScript

Template literals (introduced in ES6) allow for:
- Multi-line strings
- String interpolation
- Embedded expressions

---

## 🔹 1. Syntax

Use **backticks** instead of quotes:

```js
const name = "Rick";
const greet = `Hello, ${name}!`;
console.log(greet); // Hello, Rick!
```

---

## 🔹 2. Expression Embedding

You can insert variables or any JS expression:

```js
const a = 10;
const b = 5;
console.log(`Sum: ${a + b}`); // Sum: 15
```

---

## 🔹 3. Multi-line Strings

No need for `\n` or string concatenation:

```js
const poem = `Roses are red,
Violets are blue,
Code is fun,
And so are you.`;
console.log(poem);
```

---

## 🔹 4. Tagged Templates (Advanced)

You can pass a template literal to a function:

```js
function tag(strings, value) {
  return strings[0] + value.toUpperCase();
}
const result = tag`Hello, ${"rick"}`;
console.log(result); // Hello, RICK
```

---

## 🧠 Tip

Template literals are super useful for building dynamic strings, HTML, SQL queries, etc.

```js
const user = "admin";
const html = `<div>Welcome, ${user}</div>`;
```

---

✅ Use backticks `` ` ``  
✅ Embed values using `${}`  
✅ Ideal for clean and readable string building

---
→ [[JavaScript]]
