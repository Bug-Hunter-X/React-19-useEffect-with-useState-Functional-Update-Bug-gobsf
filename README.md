# React 19 useEffect and useState Functional Update Bug

This repository demonstrates a subtle bug that can occur when using the `useState` hook with functional updates inside the `useEffect` hook in React 19. The issue arises from incorrectly accessing the previous state within the functional update, potentially leading to unexpected behavior or infinite loops.

## Bug Description

The `bug.js` file contains a component that demonstrates the incorrect usage. The `useEffect` hook attempts to increment the count, but it might not use the latest value due to closure over the initial value of `prevCount`.  In React 18 and earlier, this might've worked serendipitously, but with React 19's optimizations this can now break more predictably and lead to bugs.

## Bug Solution

The `bugSolution.js` file provides a corrected version that uses the functional update correctly, ensuring the latest state value is used for the update.