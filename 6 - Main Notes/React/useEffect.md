**Topic**: [[React]] [[React Hooks]]

📌Runs side effects in functional components (e.g. data fetch, event listeners).

- Runs after render
- Re-runs when dependencies change
- Empty deps array `[]` → runs once on mount

```tsx
useEffect(() => {   
	// effect code 
	return () => {     
	// cleanup function (optional) 
	
	//ex: cancel the http request
		const controller = new AbortController(); //can cancel any async operation https://developer.mozilla.org/en-US/docs/Web/API/AbortController
		controller.abort();
	}; 
	
}, [deps]);
```

