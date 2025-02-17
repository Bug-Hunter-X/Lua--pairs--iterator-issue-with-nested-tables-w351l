# Lua `pairs` Iterator Issue with Nested Tables

This repository demonstrates a potential issue with Lua's `pairs` iterator when used with deeply nested tables.  The problem arises when the table's structure is modified during iteration, which can lead to unexpected behavior and even infinite loops.

## Bug Description

The `bug.lua` file contains a function `foo` that iterates through a nested table using `pairs`. However, under certain conditions (especially when modifying the table during iteration), the iterator may not behave as expected, skipping elements or entering an infinite loop.

## Solution

The solution provided in `bugSolution.lua` addresses this issue by ensuring that the table structure is not modified during iteration.  This prevents unforeseen consequences with the `pairs` function.

## How to reproduce
1. Clone the repository.
2. Run `bug.lua` using a Lua interpreter. You might observe that the script might not visit all table elements and might never exit in certain cases (especially if the nested structure is large and complex).
3. Then run `bugSolution.lua`. This shows a modified function ensuring stable table iteration using `pairs`. 