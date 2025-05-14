In **testing**, **setup** and **teardown** refer to code that runs **before** and **after** each test (or test suite) to prepare and clean up the testing environment.

---
### ✅ **General Concept**

- **Setup**: Prepare state/data/resources before a test runs (e.g., database connection, mock data).
- **Teardown**: Clean up after the test (e.g., delete files, close connections).

```js
//vitest methods
beforeEach() //before each test method is called
beforeAll() //before all test method is called

afterEach()  //after each test method is called
afterAll() //after all test method is called
```

→ [[Unit testing in JavaScript]]