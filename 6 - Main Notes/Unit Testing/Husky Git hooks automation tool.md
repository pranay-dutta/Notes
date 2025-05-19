🙄 Automatically **lint your commit messages**, **code**, and **run tests** upon committing or pushing.

```js
typeicode.github.io/husky //documentation
 .husky //folder gets created
 precomit.sh //with bash scipt
 

npm i -D lint-staged  //only lint staged files
//lintstagedrc.json  
{ "*.+(js|ts)": ["prettier --write", "eslint"] } 🤯
```

→ [[Unit testing in JavaScript]]