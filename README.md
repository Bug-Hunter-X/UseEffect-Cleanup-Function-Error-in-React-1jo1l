# useEffect Cleanup Function Error in React

This repository demonstrates a common error in React's `useEffect` hook: returning a non-function value from the cleanup function. This can lead to unexpected behavior and potentially memory leaks.

## Bug Description
The `useEffect` hook is designed to perform side effects, but it's crucial to handle cleanup properly.  The return value of the `useEffect` callback should be a cleanup function. If a value other than a function is returned, the cleanup phase will not be executed correctly. This can cause unexpected effects, especially when components unmount or re-render.

## Bug Reproduction
1. Clone the repository.
2. Run `npm install`.
3. Run `npm start`.
4. Observe the console logs. Note that the cleanup message is not logged properly, indicating the return value is not treated as a cleanup function.

## Solution
The solution involves ensuring the `useEffect` hook returns a proper cleanup function (or `null` if no cleanup is needed).