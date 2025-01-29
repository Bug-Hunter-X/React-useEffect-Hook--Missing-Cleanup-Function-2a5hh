# React useEffect Hook: Missing Cleanup Function

This repository demonstrates a common error in React applications involving the `useEffect` hook:  missing a cleanup function to prevent memory leaks.

## The Bug
The `bug.js` file contains a component that uses `setInterval` within a `useEffect` hook to update a counter every second. However, it lacks a cleanup function to clear the interval when the component unmounts.  This leads to continued updates even after the component is no longer rendered, resulting in a memory leak.

## The Solution
The `bugSolution.js` file provides the corrected code. The `useEffect` hook now includes a return function. This return function, executed when the component unmounts or when the dependencies change, clears the `setInterval` using `clearInterval`, preventing the memory leak. 

## How to Reproduce
1. Clone this repository.
2. Navigate to the directory in your terminal.
3. Run `npm install` to install the required dependencies.
4. Run `npm start` to start the development server.
5. Observe the behavior in your browser's console. The original buggy component will produce a warning, while the corrected component should execute without issues. 