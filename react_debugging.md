# Debugging Techniques for Python

## Most Common Debugging Techniques in Python

- print statements
- using pdb (python debugger)
- assert statements
- excpetion handling (try/except)
- Jupyter magics (%debug, %pdb, $run -d)

## Most Effective Tools for Python Debugging

- pdb and ipdb for complex code paths.
- logging module for scalable debugging across large projects.
- Jupyter %debug magic to drop into post-mortem debugging
- profiling tools such as %timeit, cProfile, line_profiler to catch performance related bugs.

## How to Debug Issues in Large Python/Jupyter Codebases

- isolate failing components to reduce the problem into a minimal smippet
- use unit tests (pytest)
- refactor and modularise to test smaller parts independently
- track changes with version control (git bisect) to identify when the bug was introduced
- consistent logging
