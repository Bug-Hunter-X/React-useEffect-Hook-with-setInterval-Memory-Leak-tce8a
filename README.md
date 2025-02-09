# React useEffect Hook with setInterval Memory Leak

This repository demonstrates a common error in React applications involving the `useEffect` hook and the `setInterval` function.  Failure to properly clean up the interval can lead to memory leaks and unexpected behavior.

The `bug.js` file contains the faulty code, while `bugSolution.js` provides the corrected version.

## Problem

The issue stems from the improper use of `setInterval` within the `useEffect` hook.  Without a cleanup function to stop the interval when the component unmounts, the interval continues to run, causing unnecessary state updates and potentially consuming resources even after the component is no longer needed.

## Solution

The solution involves adding a return statement to the `useEffect` hook. This function is called when the component unmounts. This return statement should use `clearInterval` to stop the interval, preventing the memory leak.