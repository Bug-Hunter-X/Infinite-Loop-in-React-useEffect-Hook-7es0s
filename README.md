# React useEffect Infinite Loop Bug

This repository demonstrates a common error in React's `useEffect` hook: an infinite loop caused by a missing dependency.  The `useEffect` hook, when called without a dependency array or with an incomplete dependency array, can cause unexpected re-renders and performance issues.

## The Bug

The `bug.js` file contains a React component that uses `useEffect` to log the current count to the console. However, it is missing a crucial dependency, which leads to an infinite loop.  Each render triggers the effect, updating the console, which triggers a re-render, leading to an infinite loop. The browser console will likely show a warning indicating this error.

## The Solution

The `bugSolution.js` file demonstrates the correct implementation.  The dependency array `[count]` is added to the `useEffect` hook. This ensures the effect only runs when the `count` state variable changes, preventing the infinite loop.

## How to Reproduce

1. Clone this repository.
2. Open `bug.js` to observe the buggy code.
3. Run the React application (e.g., using `npx create-react-app my-app` and then placing the code in a component).  Observe the infinite loop behavior in the browser's developer console.
4. Open `bugSolution.js` to see the corrected code.
5. Run the corrected code to observe the proper behavior.