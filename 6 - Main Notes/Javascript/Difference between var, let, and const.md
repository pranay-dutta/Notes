
| **var**                                                                                                         | **let**                                                                                          | **const**                                                                                            |
| --------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------ | ---------------------------------------------------------------------------------------------------- |
| The scope of a [__var__](https://www.geeksforgeeks.org/javascript-var/) variable is functional or global scope. | The scope of a [__let__](https://www.geeksforgeeks.org/javascript-let/) variable is block scope. | The scope of a [__const__](https://www.geeksforgeeks.org/javascript-const/) variable is block scope. |
| It can be updated and re-declared in the same scope.                                                            | It can be updated but cannot be re-declared in the same scope.                                   | It can neither be updated or re-declared in any scope.                                               |
| It can be declared without initialization.                                                                      | It can be declared without initialization.                                                       | It cannot be declared without initialization.                                                        |
| It can be accessed without initialization as its default value is "undefined".                                  | It cannot be accessed without initialization otherwise it will give 'referenceError'.            | It cannot be accessed without initialization, as it cannot be declared without initialization.       |
| These variables are hoisted.                                                                                    | These variables are hoisted but stay in the **temporal dead zone** untill the initialization.    | These variables are hoisted but stays in the **temporal dead zone** until the initialization.        |

## 1. Declaring Variables with var

var is the original keyword for declaring variables in JS. It is a **function scoped** or **globally scoped** depending on where it's declared.

```js
function e() {

}
```