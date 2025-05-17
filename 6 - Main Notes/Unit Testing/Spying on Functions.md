📌 To **monitor** the **behavior** of **functions** during test **execution**

**A spy** is **someone** of **something** that secretly collects information

```js
it('should email the one-time login code', ()=> {
	const email = 'name@email.com';
	const spy = vi.spyOn(security, "generateCode"); //spy function
	await login();

	const securityCode = spy.mock.results[0].value.toSring();

	expect(sendEmail).toHaveBeenCalledWith(email, securityCode);
})

```

