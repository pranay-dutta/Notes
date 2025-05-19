🟢 Catch **type-related** issues at **compile** time
🟢 Improved code **documentation**
🟢 **Better** tooling for **refactoring**

```js
npm i -D typescript //install as dev dependency 
npx tsc --init //type scipt compiler ==> configuration

//tsconfig.json
{
	"outDir": './dist' //generated js compiled code by tsc
	__other configurations__
}

//package.json
{ "scripts": { "type-check": "tsc" } }
//tsc stands for type script compiler
```

→ [[Unit testing in JavaScript]]