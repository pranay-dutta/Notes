📌Custom hooks in React are ==reusable functions that allow you to extract logic from components==, 
 making your code cleaner and easier to maintain. 
 They are a way to share stateful logic between components without duplicating code.


```tsx
//Suppose you have to use a person in multiple places

const usePerson(id: number) { //custom hook
	async function fetch() {
		const res = await axios.get('/person/' + id);
		return res;
	}
	const res = await fetch();
	
	return res.data;
}
```