
```js 
//jest for 'jest'
import {vi, ...} from 'vitest'
import {functions} from '../currency'

vi.mock('../currency') //path of js or ts file
describe('test suite', ()=> {
	test('test case',()=> {
		vi.mocked(functions)
	})
})


```
