# Using the useReducer Hook in React

The `useReducer` hook is an alternative to `useState` that is better suited for managing complex state logic.

### When to Use `useReducer`
- You have multiple related pieces of state.
- You want to centralize state updates.
- You're building a feature that resembles Redux logic without needing the whole Redux library.

### Syntax
```jsx
const [state, dispatch] = useReducer(reducer, initialState);
```

### Reducer Function
```js
function reducer(state, action) {
  switch (action.type) {
    case 'increment':
      return { count: state.count + 1 };
    case 'decrement':
      return { count: state.count - 1 };
    default:
      return state;
  }
}
```

### Example
```jsx
import { useReducer } from 'react';

const initialState = { count: 0 };

function reducer(state, action) {
  switch (action.type) {
    case 'increment':
      return { count: state.count + 1 };
    case 'decrement':
      return { count: state.count - 1 };
    default:
      return state;
  }
}

function Counter() {
  const [state, dispatch] = useReducer(reducer, initialState);

  return (
    <>
      <p>Count: {state.count}</p>
      <button onClick={() => dispatch({ type: 'increment' })}>+</button>
      <button onClick={() => dispatch({ type: 'decrement' })}>-</button>
    </>
  );
}
```

### Benefits
- Easier state logic management.
- Predictable and scalable for complex UIs.
- Clearer intent via action types.

