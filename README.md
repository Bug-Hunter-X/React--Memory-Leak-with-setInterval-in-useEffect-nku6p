# React useEffect setInterval Memory Leak

This repository demonstrates a common error in React applications involving the use of `setInterval` within the `useEffect` hook without proper cleanup.  This can lead to memory leaks and unexpected behavior.

## The Problem

The `bug.js` file contains a React component that uses `setInterval` to increment a counter every second. However, it lacks a cleanup function to clear the interval when the component unmounts. This means that even after the component is removed from the DOM, the interval continues to run, consuming resources and potentially leading to memory leaks.

## The Solution

The `bugSolution.js` file shows the corrected version. It uses the return value of `useEffect` to provide a cleanup function that stops the interval when the component is unmounted or when the dependency array changes.