🙄 Automatically **lint your commit messages**, **code**, and **run tests** upon committing or pushing.

```js
typeicode.github.io/husky //documentation
 .husky //folder gets created
 precomit.sh //with bash scipt
 

npm i -D lint-staged  //only lint staged files

//configuration file for lint-staged
//lintstagedrc.json 
{ "*.+(js|ts)": ["prettier --write", "eslint"] }

```