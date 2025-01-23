# React setInterval Memory Leak
This example demonstrates a common mistake in React: using `setInterval` within a `useEffect` hook without proper cleanup. This leads to memory leaks because the interval continues to run even after the component unmounts.

## Bug
The `bug.js` file contains a React component that uses `setInterval` to update a counter every second. However, it lacks the necessary cleanup function to stop the interval when the component is unmounted. This results in the interval continuing to run indefinitely, causing a memory leak.

## Solution
The `bugSolution.js` file provides a corrected version.  It uses the return value of `useEffect` to provide a cleanup function.  This function clears the interval when the component is unmounted, preventing the memory leak.  The corrected code uses `clearInterval` to stop the interval.