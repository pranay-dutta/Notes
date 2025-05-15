# 📌 Mock Function

A **mock function** is a **function** that **imitates/copies** the **behavior** of a **real function**  
to use **a unit** in **isolation**.

---

### 🔴 3 Ways to Write Mock Functions

 1. **Mock Return Value**
```js
const foo = vi.fn(); 
foo.mockReturnValue("fixed");
console.log(foo()); // Output: fixed
```

2. **Mock Resolved Value**
```js
const foo = vi.fn(); 
foo.mockResolvedValue("resolved");
foo().then(console.log); // Output: resolved
```
   
3. **Mock Implementation**
   
    
    `const foo = vi.fn(); foo.mockImplementation(name => "Hello " + name); console.log(foo("rick")); // Output: Hello rick`