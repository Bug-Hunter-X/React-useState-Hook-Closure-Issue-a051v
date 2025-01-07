# React useState Hook Closure Issue

This repository demonstrates a common error when using the `useState` hook in React: incorrect updating of state variables due to closure issues.

## Problem Description
The `MyComponent` component uses `useState` to track a count. Inside a `useEffect` hook with an empty dependency array, it attempts to update the count. However, it incorrectly references the initial value of `count` due to a closure over the initial value of count in the useEffect's callback, leading to unexpected behavior; the count will never increment.

## Solution
The solution uses a functional update within `setCount`, ensuring that the update uses the latest value of `count`. This approach correctly increments the count.