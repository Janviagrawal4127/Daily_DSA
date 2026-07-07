# Maximum Points You Can Obtain from Cards

## Problem Statement

You are given an integer array `cardPoints` and an integer `k`.

In one move, you can pick **one card** either from the **beginning** or the **end** of the array.

You must pick **exactly `k` cards**.

Return the **maximum score** that can be obtained.

---

## Examples

### Example 1

**Input**

```text
cardPoints = [1,2,3,4,5,6,1]
k = 3
```

**Output**

```text
12
```

**Explanation**

Take the cards `1`, `6`, and `5`.

Score = **1 + 6 + 5 = 12**

---

### Example 2

**Input**

```text
cardPoints = [2,2,2]
k = 2
```

**Output**

```text
4
```

---

### Example 3

**Input**

```text
cardPoints = [9,7,7,9,7,7,9]
k = 7
```

**Output**

```text
55
```

---

## Approach

Instead of checking every possible combination, use a **Sliding Window** approach.

### Key Observation

Initially, take all `k` cards from the **left**.

Then repeatedly:

- Remove one card from the **left**
- Add one card from the **right**
- Update the maximum score

This checks every possible way of choosing `k` cards from both ends.

---

## Algorithm

1. Compute the sum of the first `k` cards.
2. Store it as the current maximum.
3. Start taking cards from the right:
   - Remove one card from the left sum.
   - Add one card from the right sum.
   - Update the maximum score.
4. Return the maximum score.

---

## Java Solution

```java
class Solution {
    public int maxScore(int[] cardPoints, int k) {

        int n = cardPoints.length;

        int leftSum = 0;
        int rightSum = 0;

        // Take first k cards
        for (int i = 0; i < k; i++) {
            leftSum += cardPoints[i];
        }

        int maxSum = leftSum;

        int rightIndex = n - 1;

        // Replace left cards with right cards
        for (int i = k - 1; i >= 0; i--) {

            leftSum -= cardPoints[i];
            rightSum += cardPoints[rightIndex];

            rightIndex--;

            maxSum = Math.max(maxSum, leftSum + rightSum);
        }

        return maxSum;
    }
}
```

---

## Dry Run

### Input

```text
cardPoints = [1,2,3,4,5,6,1]
k = 3
```

### Initial

Take first 3 cards

```text
1 + 2 + 3 = 6
```

```
leftSum = 6
rightSum = 0
maxSum = 6
```

---

### Iteration 1

Remove `3`

Add `1`

```
leftSum = 3
rightSum = 1
Total = 4
```

```
maxSum = 6
```

---

### Iteration 2

Remove `2`

Add `6`

```
leftSum = 1
rightSum = 7
Total = 8
```

```
maxSum = 8
```

---

### Iteration 3

Remove `1`

Add `5`

```
leftSum = 0
rightSum = 12
Total = 12
```

```
maxSum = 12
```

---

## Complexity Analysis

### Time Complexity

```
O(k)
```

- First loop → `O(k)`
- Second loop → `O(k)`

Overall:

```
O(2k) = O(k)
```

### Space Complexity

```
O(1)
```

No extra data structures are used.

---

## Key Learning

- Sliding Window
- Two Pointer Technique
- Prefix & Suffix Sum
- Array Optimization

---

## Tags

- Arrays
- Sliding Window
- Two Pointers
- Prefix Sum
- Greedy
- LeetCode 1423
