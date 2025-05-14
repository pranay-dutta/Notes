📌A way to to **run same test** multiple times with **different** sets of **input data**
- So instead of writing **multiple tests** of same **characteristics** we use **Parameterized tests**

```js
//vitest parameterized test
describe('canDrive', ()=> {
	it.each([
	 {age: 22, country: 'UK', result: true}, //muliple inputs
	 {age: 21, country: 'IN', result: true},
	 {age: 15, country: 'UK', result: false},
	 {age: 17, country: 'IN', result: false}
	]).('should return $result for $age and $country' ({age, country, result})=>{
		expect(canDrive(age, country)).toBe(result)
	})
})
```

→ [[Unit testing in JavaScript]]