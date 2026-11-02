# 3. Longest Substring Without Repeating Characters

- **Day:** Day 03 — Array (Part 3), final problem in the scheduled set
- **Difficulty:** Medium
- **Platform:** LeetCode
- **Problem:** Longest Substring Without Repeating Characters

## Approach

Use the **sliding window + unordered set** technique to maintain a substring with no repeated characters.

1. Keep two pointers, `left` and `right`, to represent the current window.
2. Expand the window by moving `right` one character at a time.
3. If `s[right]` is already present in the set, shrink the window from the left: erase `s[left]` and increment `left` until the repeated character is removed.
4. Insert the current character into the set.
5. Update the maximum window length using `right - left + 1`.

The set always contains the distinct characters in the current window.

## Complexity

- **Time:** O(n) average — each character is inserted and removed from the set at most once.
- **Space:** O(min(n, k)) — the set stores at most the number of distinct characters in the input alphabet (`k`), bounded by the string length `n`.

## Key Concept

Maintain a valid window with no duplicate characters. Expand it when possible and move the left boundary forward whenever a duplicate appears.
