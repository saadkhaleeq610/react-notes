# Custom Hooks in React

Custom hooks allow you to extract and reuse component logic.

## Why Custom Hooks?
- Share logic between components without duplicating code.
- Keep components clean and readable.

## Creating a Custom Hook
```jsx
function useCounter(initialValue = 0) {
  const [count, setCount] = useState(initialValue);
  const increment = () => setCount(c => c + 1);
  const decrement = () => setCount(c => c - 1);

  return { count, increment, decrement };
}

function CounterComponent() {
  const { count, increment, decrement } = useCounter(10);
  return (
    <div>
      <p>{count}</p>
      <button onClick={increment}>+</button>
      <button onClick={decrement}>-</button>
    </div>
  );
}
```

## Guidelines
- Name starts with `use` (e.g., `useSomething`).
- Can call other hooks inside.

## Use Cases
- Fetching data (`useFetch`)
- Managing forms (`useForm`)
- Local storage sync (`useLocalStorage`)

## Summary
- Custom hooks are JavaScript functions that follow React's hook rules.
- Encourage reusability and separation of concerns.

