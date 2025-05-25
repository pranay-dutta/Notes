**Topic**: [[React]]

📌Performant, flexible and extensible forms with easy-to-use validation.
Learn about react hook form <a href="https://react-hook-form.com/">in </a>

```tsx
import useForm from 'react-hook-form' 
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