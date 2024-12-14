# React Router v6 useNavigate Hook Error: Outside Router Context
This repository demonstrates a common error in React Router v6 when using the `useNavigate` hook outside of a routing context.  The `bug.js` file shows the incorrect implementation, resulting in the error:  "'useNavigate' hook was called outside a router context."  The `bugSolution.js` file provides the corrected implementation.

## Problem
The `useNavigate` hook requires a router context.  If you call `useNavigate` in a component that is not directly rendered within a route, you'll get this error.  This is typical when a component is nested deeply within other components or used in a context that's not part of the routing structure.

## Solution
Ensure that the component using `useNavigate` is either directly a child of a route component (e.g., `<Route path="/path" element={<MyComponent />} />`), or that the router context is explicitly passed down using a context provider if that is the use case.  If the navigation logic is more complex, it is important to ensure that the navigate function can be properly accessed.