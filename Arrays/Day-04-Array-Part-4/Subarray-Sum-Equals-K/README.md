# 560. Subarray Sum Equals K

- **Day:** Day 04 — Array (Part 4)
- **Difficulty:** Medium
- **Platform:** LeetCode
- **Problem:** Subarray Sum Equals K

## Approach

Use **prefix sum + unordered map (frequency counting)** to count the number of contiguous subarrays whose sum equals `k`.

1. Initialize a prefix sum `prefixsum = 0` and a frequency map `mp`.
2. Set `mp[0] = 1` to account for a subarray whose sum from the beginning is exactly `k`.
3. Traverse the array and add the current element to `prefixsum`.
4. Look for `prefixsum - k` in the map. Every occurrence represents a previous prefix sum that forms a subarray ending at the current index with sum `k`.
5. Add its frequency to `count`, then record the current prefix sum with `mp[prefixsum]++`.
6. Return `count` after processing all elements.

The current prefix sum is added to the map only after checking `prefixsum - k`, ensuring that only earlier prefix positions are counted.

## Complexity

- **Time:** O(n) average — one pass through the array with average O(1) hash-map operations.
- **Space:** O(n) — the frequency map can store up to O(n) distinct prefix sums.

## Key Concept

If `prefixSum[j] - prefixSum[i] = k`, then the subarray between those prefix positions has sum `k`. Store prefix-sum frequencies so all valid earlier positions can be counted efficiently.
