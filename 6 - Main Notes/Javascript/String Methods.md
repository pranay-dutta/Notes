There are tons of methods in of Strings in JS

```run-js
//String methods in JavaScript
let person = "Rick Dutta";

console.log(person.at(0)); // "R"
console.log(person.at(-1)); // "k"
console.log(person.charAt(0)); // "R"
console.log(person.charAt(-1)); // "" (empty string, as negative index is not valid)
console.log(person.charCodeAt(0)); // 82 (ASCII code for 'R')
console.log(person.charCodeAt(-1)); // NaN (negative index is not valid)
console.log(person.concat(" Dutta")); // "Rick Dutta"
console.log(person.endsWith(" Dutta")); // true
console.log(person.includes("Rick")); // true
console.log(person.indexOf("c")); // 2
console.log(person.lastIndexOf("c")); // 2
console.log(person.match(/ck/));  // ["ck"]

const it = person.matchAll(/t/g);
console.log([...it]); // [Array(1)]

console.log('é'.normalize() === 'e\u0301'.normalize()); //True
console.log(person.padEnd(15, '.')) // "Rick Dutta...."
console.log(person.padStart(15, '.')) // "....Rick Dutta"
console.log(person.repeat(2)); // "Rick DuttaRick Dutta"
console.log(person.replace("Rick", "John")); // "John Dutta"
console.log(person.replaceAll("t", "T")); // "Rick DuTTa"
console.log(person.search("Dutta")); // 5

console.log(person)

console.log(person.slice(0, 4)); // "Rick"
console.log(person.split(" ")); // ["Rick", "Dutta"]
console.log(person.startsWith("Rick")); // true
console.log(person.toLowerCase()); // "rick dutta"
console.log(person.toUpperCase()); // "RICK DUTTA"
console.log(person.trim()); // "Rick Dutta" (no leading/trailing spaces)
console.log(person.trimStart()); // "Rick Dutta" (no leading spaces)
console.log(person.trimEnd()); // "Rick Dutta" (no trailing spaces)
console.log(person.valueOf()); // "Rick Dutta"

```