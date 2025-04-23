# Code Splitting and Lazy Loading in React

React supports built-in code splitting via `React.lazy` and `Suspense`.

## Why Code Splitting?
- Load only the code needed for initial render.
- Improve performance by reducing bundle size.

## React.lazy
- Dynamically import components.

### Example
```jsx
import React, { Suspense } from 'react';
const LazyComponent = React.lazy(() => import('./LazyComponent'));

function App() {
  return (
    <Suspense fallback={<div>Loading...</div>}>
      <LazyComponent />
    </Suspense>
  );
}
```

## Best Practices
- Use for routes and large components.
- Keep fallback UI simple.

## Code Splitting with React Router
```jsx
const Home = lazy(() => import('./Home'));

<Route path="/" element={
  <Suspense fallback={<div>Loading...</div>}>
    <Home />
  </Suspense>
} />
```

## Summary
- Use `React.lazy` for on-demand component loading.
- Wrap with `Suspense` to handle loading state.
- Improves load times and user experience.

