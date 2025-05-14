#### Loose assertion👎:
- Loose assertions are too **general** and it will **always** pass.

```js
//Loose (too general)
const res = '...'
expect(res).toBeDefined() //although a fn returns ... our test passes
```

#### Tight assertion👎:
- Tight assertions are too **specific** and will not pass in **most** cases

```js
//Tight (too specific)
const res = 'requeted file not found!'
expect(res).toBe('requeted file not found') 
//fn returns proper error but only '!' will cause the test fail.

//Better way
expect(res).toMatch(/not found/i) //check regex exp. 'i' stands for "case insensitive"
```

→ [[Unit testing in JavaScript]]