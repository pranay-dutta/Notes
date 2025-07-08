📌 We can use caching to improve **load/response** time.

**Cache** :- Temporary storage
- Stores Results of expensive operations
- Stores Frequently accessed data

---
Don't disturb **DB** frequently just read from **Cache**.
 💡Read through **Cache**
 
<img src="read-through-cache.png" width=600 style="border-radius: 5px" />

---
### Interacting with Cache
- Cache server provide **API's** to interact with **Cache**
### Example

```js
cache.set("my_key", "value", 3600seconds)
cache.get("my_key")
```

i