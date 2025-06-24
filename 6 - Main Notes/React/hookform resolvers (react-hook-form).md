**Topic**: [[React]]

A utility package that connects **React Hook Form** with external **schema validation libraries** like **Yup**, **Zod**, **Joi**, etc., via _resolvers_.
#### ✅ Purpose:
 Enables schema-based validation inside `useForm()` using the `resolver` option.
#### 📦 Example:

```tsx
useForm({ resolver: yupResolver(schema) });
```

#### 📚 Supported:

- `yupResolver`
- `zodResolver`
- `joiResolver`
- `superstructResolver`
- `classValidatorResolver` (and more)