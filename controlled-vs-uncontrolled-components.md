# Controlled vs Uncontrolled Components

## Controlled Components
- React controls the input element.
- The form data is handled by the component's state.

### Example
```jsx
const [value, setValue] = useState('');

<input value={value} onChange={e => setValue(e.target.value)} />
```

### Pros
- Easy to implement validation.
- Centralized form data.
- Easier to test and debug.

## Uncontrolled Components
- DOM handles the form data.
- Access values using `ref`.

### Example
```jsx
const inputRef = useRef();

<input ref={inputRef} />
<button onClick={() => alert(inputRef.current.value)}>Submit</button>
```

### Pros
- Less code for simple forms.
- Useful for third-party libraries.

## Summary
- Use **controlled components** for better control, validation, and integration.
- Use **uncontrolled components** for simpler use cases and minimal React involvement.

