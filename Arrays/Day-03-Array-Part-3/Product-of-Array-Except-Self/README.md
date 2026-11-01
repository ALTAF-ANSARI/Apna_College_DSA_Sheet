# 238. Product of Array Except Self

- **Day:** Day 03 — Array (Part 3)
- **Difficulty:** Medium
- **Platform:** LeetCode
- **Problem:** Product of Array Except Self

## Approach

Use **prefix products** and **suffix products** to calculate the product of every element except the current one, without using division.

1. Build `prefix[i]`, the product of all elements from index `0` through `i`.
2. Build `suffix[i]`, the product of all elements from index `i` through `n - 1`.
3. For each index `i`, multiply the product to its left by the product to its right:
   - `left = 1` when `i == 0`; otherwise `prefix[i - 1]`.
   - `right = 1` when `i == n - 1`; otherwise `suffix[i + 1]`.
4. Store `left * right` in the answer.

This handles zero values naturally and does not use division.

## Complexity

- **Time:** O(n) — prefix construction, suffix construction, and answer construction each take linear time.
- **Space:** O(n) auxiliary space for the prefix and suffix arrays, excluding the output array.

## Key Concept

The answer at index `i` is the product of all elements before `i` multiplied by all elements after `i`.
