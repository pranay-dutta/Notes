📌 A **testing technique** where we focus on the **edges** or **boundaries** of  **input values.**

```js
 describe('isPriceInRange', () => {
	//Negative testing
   it('should return false when price is outside the range', () => {
     expect(isPriceInRange(-1, 0, 10)).toBe(false)
     expect(isPriceInRange(11, 0, 10)).toBe(false)
   })
   
   //Positve testing
   it('should return true when price is within the range', () => {
     expect(isPriceInRange(2, 0, 10)).toBe(true)
   })
 })
```

→ [[Unit testing in JavaScript]]