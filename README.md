# Stale Closure Bug in React useEffect

This repository demonstrates a common error in React's `useEffect` hook: the stale closure problem.  When a value used inside the `useEffect` callback changes, the callback may not update correctly if its dependencies aren't properly declared in the dependency array.

The `bug.js` file shows the incorrect implementation. The `count` variable is used within the `setInterval` callback, but `count` is not included in the useEffect dependency array([]). This leads to the callback always using the initial value of `count`, preventing the counter from updating.

The `bugSolution.js` provides the correct solution.  By adding `count` to the dependency array, the effect will re-run whenever `count` changes, and thus the `setInterval` callback will always have the latest value of `count`.