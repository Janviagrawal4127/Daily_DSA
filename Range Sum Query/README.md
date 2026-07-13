# 303. Range Sum Query - Immutable

## Description

Given an integer array `nums`, efficiently answer multiple range sum queries.

Each query asks for the sum of the elements between two indices `left` and `right` (inclusive).

Implement the `NumArray` class with the following methods:

- **`NumArray(int[] nums)`**  
  Initializes the object with the integer array `nums`.

- **`int sumRange(int left, int right)`**  
  Returns the sum of the elements from index `left` to index `right` (inclusive).

The goal is to preprocess the array once so that each range sum query can be answered efficiently.

### Constraints

- `1 <= nums.length <= 10^4`
- `-10^5 <= nums[i] <= 10^5`
- `0 <= left <= right < nums.length`
- At most `10^4` calls will be made to `sumRange`.
```
