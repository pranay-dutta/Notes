🌐 **Website** https://vitest.dev

1. Install as development dependency, `npm i -D vitest`
2. Setup **scripts** 

```json
//package.json
{
  "scripts": {
    "test": "vitest", //or use npm t
	"test:ui": "vitest --ui" //web ui for viewing tests
    "coverage": "vitest run --coverage" //npm run coverage
  }
}
```

→ [[Unit testing in JavaScript]]