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

🔴🔴 **Mock object** is **Global** so it **accumulates** information between **different test cases**
🔴🔴 Don't **rely** heavily on **mocks**. Use mocks only  for **Mocking** **external** dependencies

🟢🟢 So it's **best** to **clear** mock functions **before** or **after each test case**

```js
mockClear()
mockReset() //resets implementation
mockRestore() //restore original implemetation

//
1. vi.mock(foo).mockClear();
2. vi.clearAllMocks(); //clear all mock function states

3. //or use vitest config
//vite.config.js or ts
import {definConfit} from "vitest/config"

export default defineConfig {
	test: {
		clearMocks: true
	}
}

```
