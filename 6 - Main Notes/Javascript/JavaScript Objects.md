**Topic**: [[JavaScript]]

📘 JavaScript Objects (Basics)

- An object is a collection of key-value pairs.
- Keys are strings (or symbols), and values can be any type.

Example:

```run-js
let person = {
  name: 'Rick',
  age: 25,
  isStudent: true
};

// Access values using dot notation or bracket notation:
console.log(person.name);      // 'Rick'
console.log(person['age']);    // 25

// Add or update properties:
person.city = 'Delhi';         // add
person.age = 26;               // update

// Delete properties:
delete person.isStudent;

// Objects can store arrays, functions, or other objects:
let user = {
  name: 'ana',
  hobbies: ['music', 'reading'],
  greet: function() { console.log('hello'); }
}; 
```

→ [[JavaScript]]