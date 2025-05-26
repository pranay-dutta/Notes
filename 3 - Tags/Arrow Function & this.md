## 🏹 Arrow Functions & `this`  

### 🔸 Explanation:

Arrow functions **don’t have their own `this`**.  
They **capture `this` from the surrounding scope** where they're defined.  
This makes them useful when you want to **preserve context**—especially in callbacks.

```tsx
const user = {
  name: "Rick",
  greet: function () {
    const sayHi = () => {
      console.log(`Hi, I'm ${this.name}`)  // ✅ 'Rick'
    }
    sayHi()
  }
}

user.greet()
```