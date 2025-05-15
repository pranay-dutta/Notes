
```js 
//jest for 'jest'
import {vi, ...} from 'vitest'
import {foo} from '../currency'

vi.mock('../currency') //path of js or ts file | also this line gets Hoisted

describe('test suite', ()=> {
	test('test case',()=> {
	//as whole module is mocked we can use it's functions as mock functions
		vi.mocked(foo).mockReturnValue(2) 
	})
})
```

→ [[Unit testing in JavaScript]]