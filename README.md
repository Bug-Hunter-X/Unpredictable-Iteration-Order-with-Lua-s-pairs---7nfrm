# Lua pairs() Iteration Order

This example demonstrates a potential issue with Lua's `pairs()` iterator.  The order in which `pairs()` iterates over a table's entries is not guaranteed to be consistent across different Lua versions or implementations.  This can lead to unexpected behavior if your code relies on a specific iteration order.

## Reproducing the Issue

The `bug.lua` file contains a simple function `foo()` that recursively iterates through a nested table using `pairs()`. The output may vary depending on the Lua version and implementation.

## Solution

The `bugSolution.lua` file offers a solution using `ipairs()` for tables with sequential integer keys, or a custom iteration function with a sorted key list for tables with non-sequential keys, to ensure a consistent and predictable order.