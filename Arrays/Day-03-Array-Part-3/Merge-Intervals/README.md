# 56. Merge Intervals

- **Day:** Day 03 — Array (Part 3)
- **Difficulty:** Medium
- **Platform:** LeetCode
- **Problem:** Merge Intervals

## Approach

Use **sorting + a greedy merge**:

1. Sort all intervals by their starting point.
2. Add the first interval to the result.
3. Iterate over the remaining intervals and compare each interval with the last interval in the result.
4. If the current interval starts before or at the end of the last interval (`curr[0] <= last[1]`), the intervals overlap. Extend the last interval's end using `max(last[1], curr[1])`.
5. Otherwise, add the current interval as a new, separate interval.

Sorting ensures that any overlapping intervals appear next to one another, so a single pass is enough to merge them.

## Complexity

- **Time:** O(n log n) — sorting dominates the linear scan.
- **Space:** O(n) for the merged result. Sorting may also use implementation-dependent auxiliary stack space.

## Key Concept

After sorting by start time, compare each interval with the most recently merged interval. Merge when they overlap; otherwise, start a new interval.

## Note

The given implementation assumes `intervals` is non-empty, as guaranteed by the usual LeetCode constraints for this problem.
