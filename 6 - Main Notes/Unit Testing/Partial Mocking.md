🔴 When we use `vi.mock(path_of_module)` **vitest** replaces every **exported**  function of the **module** as  **Mock** function 

🟢 But sometimes we want to keep **some** function.  For **those** moments we use **Partial Mocking**

```js
vi.mock(_path_, (importOriginal)=> { 
	const originalModule = importOriginal();
	//if we don't return by deafult all exported 
	//functions are treated as mock function
	return {
		...originalModule;
		foo: vi.fn() 
	}
})

describe('test suite', ()=> {
	it('should call the foo', async ()=> {
		await bar()
		const args = vi.mocked(foo).mock.calls[0]
		expect(args[0]).toBe('rick') //first argument of foo
	})
})

```

→ [[Unit testing in JavaScript]]