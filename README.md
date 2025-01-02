# React useEffect Runs on Every Render

This repository demonstrates a common misconception about the `useEffect` hook in React.  The example code incorrectly attempts to distinguish between the initial mount and subsequent updates of a component by checking the value of a state variable inside the `useEffect` dependency array. This results in unexpected behavior and incorrect logging.

## Bug Description
The provided `bug.js` file contains a component that uses `useEffect` to log messages on mount and update. However, the condition `if (count === 0)` is flawed because `count` changes on every click, causing the "Component updated" message to be logged unnecessarily on the first click.

## Solution
The `bugSolution.js` file provides the corrected implementation.  Instead of relying on a state variable to check for the initial render, it leverages the second argument of `useEffect`, a dependency array, to only run the effect once on mount.  An empty dependency array `[]` ensures that the effect only executes after the initial render.