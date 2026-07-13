# 724. Find Pivot Index

## Description

Given an integer array `nums`, return the **pivot index** of the array.

The **pivot index** is the index where the sum of all the elements strictly to the left of the index is equal to the sum of all the elements strictly to the right.

* If the pivot index is the first index, the left sum is `0`.
* If the pivot index is the last index, the right sum is `0`.

Return the **leftmost** pivot index. If no such index exists, return `-1`.

### Constraints

* `1 <= nums.length <= 10^4`
* `-1000 <= nums[i] <= 1000`

---

## Approach

The idea is to avoid recalculating the left and right sums for every index.

1. Calculate the **total sum** of all elements in the array.

2. Initialize `leftSum = 0`.

3. Traverse the array from left to right.

4. For each index, calculate the right sum using:

   ```text
   rightSum = totalSum - leftSum - nums[i]
   ```

5. If `leftSum` equals `rightSum`, the current index is the pivot index, so return it.

6. Otherwise, update `leftSum` by adding the current element:

   ```text
   leftSum += nums[i]
   ```

7. If no pivot index is found after the traversal, return `-1`.

This approach computes the answer in a single traversal after finding the total sum, resulting in an efficient **O(n)** time solution with **O(1)** extra space.
