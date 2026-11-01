# 73. Set Matrix Zeroes

- **Day:** Day 03 — Array (Part 3)
- **Difficulty:** Medium
- **Platform:** LeetCode
- **Problem:** Set Matrix Zeroes

## Approach

Use two auxiliary arrays to remember which rows and columns must become zero:

1. Create a `row` array of size `n` and a `col` array of size `m`, initialized to `0`.
2. Traverse the matrix. Whenever `matrix[i][j]` is `0`, mark `row[i]` and `col[j]` as `1`.
3. Traverse the matrix again. If `row[i]` or `col[j]` is marked, set `matrix[i][j]` to `0`.

The first traversal records all original zero positions before any matrix values are modified, preventing newly written zeroes from affecting the result.

## Complexity

- **Time:** O(n × m) — two complete matrix traversals.
- **Space:** O(n + m) — auxiliary row and column marker arrays.

## Key Concept

Separate identification from modification: first record which rows and columns need to be zeroed, then update the matrix in a second pass.
