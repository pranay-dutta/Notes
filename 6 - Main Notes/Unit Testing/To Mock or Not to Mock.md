🔴🔴 **Mock object** is **Global** so it **accumulates** information between **different test cases**
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

🔴🔴 Don't **rely** heavily on **mocks**. Use mocks only  for mocking `@external dependencies`

→ [[Unit testing in JavaScript]]