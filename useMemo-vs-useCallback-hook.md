# React.memo and useCallback for Optimization

## `React.memo`
- Prevents re-rendering of a component if its props haven't changed.

### Usage
```jsx
const MyComponent = React.memo(function MyComponent({ value }) {
  return <div>{value}</div>;
});
```

### When to Use
- Component re-renders too often.
- Props are primitive and stable.

## `useCallback`
- Memoizes a callback function so it doesn’t get redefined on each render.

### Usage
```jsx
const handleClick = useCallback(() => {
  console.log('Clicked');
}, []);
```

### With Children
```jsx
function Parent() {
  const callback = useCallback(() => doSomething(), []);
  return <Child onClick={callback} />;
}
```

## Common Pitfalls
- Don’t over-optimize — use only if necessary.
- May increase complexity if used too much.

## Summary
- `React.memo` prevents unnecessary renders.
- `useCallback` ensures function references are stable.
- Helps with performance in large apps.

