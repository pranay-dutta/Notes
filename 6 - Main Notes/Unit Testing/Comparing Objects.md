- Although they are **same objects** be **in different memory location**
- So use **toEqual** matcher to **compare** the **value**

```js
const res = {name: "rick"}
expect(res).toBe({name: "rick"}) ❌
expect(res).toEqual({name: "rick"}) ✅
```

→ [[Unit testing in JavaScript]]