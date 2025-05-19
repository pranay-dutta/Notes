🙄 Automatically **lint your commit messages**, **code**, and **run tests** upon committing or pushing.

```js
typeicode.github.io/husky //documentation
 .husky //folder gets created
 precomit.sh //with bash scipt
 

npm i -D lint-staged  //only lint staged files
//lintstagedrc.json  
{ "*.+(js|ts)": ["prettier --write", "eslint"] } 🤯
```

📌 **There** are **hooks** like **pre-commit** or **pre-push** 

```⚠️Important to note!

.husky/pre-push //pre push script or hook
npx vitest run //to run vitest only once

.husky/pre-commit //pre comit hook 
npx lint-staged //
```

→ [[Unit testing in JavaScript]]