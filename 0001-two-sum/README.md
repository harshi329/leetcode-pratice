# 1. Two Sum

**LeetCode Problem:** [Two Sum](https://leetcode.com/problems/two-sum/)  
**Difficulty:** Easy  
**Topic:** Array, Hash Map  
**Language:** Python

## Problem Statement

Given an array of integers `nums` and an integer `target`, find the indices of two numbers whose sum equals the target.

**Conditions:**
- Exactly one valid answer exists.
- The same element cannot be used twice.
- The answer can be returned in any order.

## Examples

### Example 1
```python
nums = [2, 7, 11, 15]
target = 9
Output = [0, 1]
```
Explanation: `nums[0] + nums[1] = 2 + 7 = 9`.

### Example 2
```python
nums = [3, 2, 4]
target = 6
Output = [1, 2]
```
Explanation: `nums[1] + nums[2] = 2 + 4 = 6`.

### Example 3
```python
nums = [3, 3]
target = 6
Output = [0, 1]
```
Explanation: The two elements at different indices add up to `6`.

## My Approach: Hash Map

1. Create an empty dictionary called `seen`.
2. Traverse the list using `enumerate()` to get each number and its index.
3. Calculate the complement using `target - num`.
4. Check whether the complement exists in the dictionary.
5. If it exists, return the two indices.
6. Otherwise, store the current number and its index.

## Python Solution

```python
class Solution:
    def twoSum(self, nums: list[int], target: int) -> list[int]:
        seen = {}

        for i, num in enumerate(nums):
            complement = target - num

            if complement in seen:
                return [seen[complement], i]

            seen[num] = i
```

## Complexity Analysis

- **Time Complexity:** O(n) average
- **Space Complexity:** O(n)

Here, `n` is the number of elements in the array.

## Key Learnings

- List indices start from `0`.
- Return indices, not the values themselves.
- `enumerate()` provides both index and value.
- A dictionary helps find the required number efficiently.
- Check for the complement before storing the current number.

## Handwritten Notes

[Handwritten Two Sum Notes] (two-sum-notes.jpg.png)
