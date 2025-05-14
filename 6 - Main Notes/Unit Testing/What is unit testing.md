
* 📝 Unit testing is a **form** of *automated testing* where we write code to test our **code**.
* If we don't use *automated testing* then we have to *manually check* the code which is very `!time consuming`


#### Example

```js
const max(a, b) {
	return a > b ? a : b;
}

//exmple test: using v-test, a testing framework
descibe(()=> {
	it('should return the first value if greater') {
		const a = 1, b = 2;    //Arrange
		const res = max(a, b); //Act 
		expect(res).toBe(1)    //Assert
	}
})
```

→ [[Unit testing in JavaScript]]