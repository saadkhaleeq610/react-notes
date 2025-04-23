# useEffect Hook in React

The `useEffect` hook allows you to run side effects in function components.

## Basic Usage
```jsx
useEffect(() => {
  console.log('Component mounted or updated');
});
```

## Dependency Array
```jsx
useEffect(() => {
  console.log('Runs only on mount');
}, []);

useEffect(() => {
  console.log('Runs when value changes');
}, [value]);
```

## Cleanup Function
```jsx
useEffect(() => {
  const timer = setInterval(() => console.log('tick'), 1000);
  return () => clearInterval(timer);
}, []);
```
- Runs on unmount or before re-running the effect.

## Use Cases
- Fetching data.
- Subscribing to events.
- Cleaning up timers or listeners.

## Rules
- Do not use `useEffect` inside loops or conditions.
- Keep dependencies accurate to avoid bugs.

## Summary
- `useEffect` replaces lifecycle methods like `componentDidMount`, `componentDidUpdate`, and `componentWillUnmount`.

