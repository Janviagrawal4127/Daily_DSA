# Find Peak Element

## Description

Given a 0-indexed integer array `nums`, find the index of any **peak element**.

A peak element is an element that is **strictly greater than its adjacent neighbors**. For boundary elements, assume:

* `nums[-1] = -∞`
* `nums[n] = -∞`

This guarantees that at least one peak always exists in the array. If multiple peak elements are present, returning the index of any one of them is valid.

The solution must run in **O(log n)** time.

---

## Approach

This problem is solved using **Binary Search** by observing the direction of the slope instead of searching for a specific value.

1. Initialize two pointers:

   * `low = 0`
   * `high = n - 1`

2. While `low < high`:

   * Calculate the middle index `mid`.
   * Compare `nums[mid]` with `nums[mid + 1]`.

3. If `nums[mid] < nums[mid + 1]`, the array is increasing at `mid`, so a peak must exist on the **right half**. Move `low` to `mid + 1`.

4. Otherwise, the array is decreasing at `mid`, meaning a peak exists on the **left half**, including `mid`. Move `high` to `mid`.

5. Continue until `low == high`. At this point, both pointers indicate the index of a peak element.

This approach works because each comparison allows half of the search space to be eliminated while guaranteeing that the remaining half still contains at least one peak.
