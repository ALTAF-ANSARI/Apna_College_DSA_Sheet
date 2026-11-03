# 54. Spiral Matrix

- **Day:** Day 04 — Array (Part 4)
- **Difficulty:** Medium
- **Platform:** LeetCode
- **Problem:** Spiral Matrix

## Approach

Use four boundaries to traverse the matrix layer by layer in clockwise spiral order:

1. `srow` and `erow` represent the current top and bottom rows.
2. `scol` and `ecol` represent the current left and right columns.
3. Traverse the top row from left to right.
4. Traverse the right column from top to bottom.
5. Traverse the bottom row from right to left, only if the top and bottom rows are different.
6. Traverse the left column from bottom to top, only if the left and right columns are different.
7. Move all four boundaries inward and repeat while the remaining rectangle is valid.

The boundary checks prevent duplicate visits when the remaining layer contains only one row or one column.

## Complexity

- **Time:** O(n × m) — every matrix element is visited once.
- **Space:** O(1) auxiliary space, excluding the output vector.

## Key Concept

Maintain four shrinking boundaries and process the matrix perimeter in clockwise order until all layers have been traversed.
