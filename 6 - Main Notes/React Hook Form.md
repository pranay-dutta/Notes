**Topic**: [[React]]

```tsx
import useFrom from 'react-hook-form'
import z from 'zod' //zod is validation library

const schema = z.object({
	name: "validation rules"
	age: "validation rules"
})
type FormData = z.infer<typeof schema>

const {register, handleSubmit, formState}=useForm<FormData>(); //FormData is an interface
<intput {...register('name', options?)} />
```

🤔Know brief about [[Data Validation Libraries]]