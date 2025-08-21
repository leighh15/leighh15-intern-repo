# Debugging Techniques for Python

## Most Common Debugging Techniques

- reproduce reliably; create a minimal repro
- read console warnings and errors first
- use React DevTools to inspect props/state and renders
- use breakpoints and logpoints
- regression test before and after bug fix

## Most Effective Tools for React Debugging

- React DevTools
- Browser DevTools
- VS Code Debugger
- Error monitoring with source maps

## How to Debug Issues in Large React Codebases

- Isolate the problem
- Use git bisect (find specific commit introducing bug)
- add logging across client/server to follow a request
- guard via feature flags
- land a minimal fix with regression test; document ownership
