# React UseEffect setInterval Memory Leak

This repository demonstrates a common error in React applications involving memory leaks caused by the improper use of `setInterval` within the `useEffect` hook.  The example shows how failing to properly clean up the interval leads to a continuously running timer even after the component unmounts, consuming unnecessary resources.

## Bug Description:
The provided code snippet defines a React component that uses `setInterval` to update a counter every second. The problem is that the `setInterval` function is called only once and not stopped within useEffect before the component is unmounted.  This leads to an ever-increasing count and prevents garbage collection of the interval, resulting in a memory leak.

## Bug Solution
The solution addresses this issue by using a cleanup function within the `useEffect` hook to clear the interval when the component unmounts.