# Using React Hook Form for Form Handling

React Hook Form simplifies form state management, validation, and performance.

## Installation
```bash
npm install react-hook-form
```

## Basic Usage
```jsx
import { useForm } from 'react-hook-form';

function MyForm() {
  const { register, handleSubmit, formState: { errors } } = useForm();

  const onSubmit = data => console.log(data);

  return (
    <form onSubmit={handleSubmit(onSubmit)}>
      <input {...register('name', { required: true })} />
      {errors.name && <p>Name is required</p>}

      <input type="submit" />
    </form>
  );
}
```

## Features
- Tiny and fast.
- Built-in validation.
- Works with uncontrolled components.

## Advanced
- Integrates with UI libraries (MUI, Chakra).
- Supports schema-based validation (with `zod`, `yup`).

```jsx
import { zodResolver } from '@hookform/resolvers/zod';
import * as z from 'zod';

const schema = z.object({ name: z.string().min(1) });

useForm({ resolver: zodResolver(schema) });
```

## Summary
- Lightweight and performant.
- Reduces boilerplate.
- Scales well for both small and large forms.

