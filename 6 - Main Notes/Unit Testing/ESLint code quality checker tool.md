🟢 Catch **common** coding **mistakes** early in **development**
🟢 **Enforce** coding **standards** and **best** practices
🟢 **Improve** code **consistency** and **readability**
🟢 **Facilitate** collaboration within **teams**

⚠️ By **default** ESLint **does not** lint **typescript codes**

```js
npm init @eslint/config@latest
//eslint.config.js or ts ===> watch documentaton
npx eslint . //to check linting errors
npx eslint --fix //to fix 'fixable errors'

//package.json
{ "scripts": { "lint": "eslint ." } }
```

→ [[Unit testing in JavaScript]]