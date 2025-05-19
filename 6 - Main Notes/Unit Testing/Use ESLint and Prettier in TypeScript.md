⚠️ By **default** ESLint **does not** lint **typescript codes**

The `.mjs` extension makes the file use the [ES modules (ESM)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Modules) format. Node interprets `.js` files in the [CommonJS (CJS)](https://nodejs.org/api/modules.html) format by default, but if you have `"type": "module"` in your `package.json`, you can also use `eslint.config.js`.

```js

typescipt-eslint.io //for installation

//if using ESM
eslint.config.mjs

//if using common js
eslint.config.js


```
