# React Native useRef Hook Error: Component Unmounts Before Callback

This repository demonstrates a common error in React Native applications when using the `useRef` hook. The error occurs when a component unmounts before a callback function within a `useEffect` hook that uses the ref completes, attempting to access a DOM element that no longer exists.

## Problem

The provided `bug.js` file shows an example of a component using `useRef` to focus on a TextInput. If the component unmounts before the `focus()` method is executed (e.g., during rapid navigation or state changes), an error will occur because the ref's `current` property will attempt to access a DOM element that is no longer in the DOM.

## Solution

The `bugSolution.js` file provides a solution by adding a check inside the `useEffect` hook to verify that the component is still mounted before executing the callback function. This prevents the error by safely handling situations where the component has already been unmounted.  This utilizes a flag to track the component's mounted state.