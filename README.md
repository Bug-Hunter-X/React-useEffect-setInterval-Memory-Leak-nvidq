# React useEffect setInterval Memory Leak
This example demonstrates a common memory leak in React applications caused by the improper use of `setInterval` within the `useEffect` hook.  The component continuously increments a counter without stopping.

## Problem
The `setInterval` function is called within the `useEffect` hook, and the returned interval ID is not saved or cleared.  This leads to a memory leak because the interval continues to run even after the component unmounts.

## Solution
The solution involves storing the returned interval ID from `setInterval` in a `ref` and clearing it within the cleanup function of `useEffect` hook.