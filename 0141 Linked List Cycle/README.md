# 141. Linked List Cycle

## Description

Given the `head` of a linked list, determine whether the linked list contains a **cycle**.

A cycle exists if a node in the list can be reached again by continuously following the `next` pointers.

Return `true` if there is a cycle; otherwise, return `false`.

---

## Example

**Input:**

```
3 → 2 → 0 → -4
    ↑       ↓
    └───────┘
```

**Output:**

```
true
```

**Explanation:**

The last node points back to the second node, forming a cycle.

---

## Approach (Floyd's Cycle Detection Algorithm)

- Use two pointers:
  - **Slow Pointer** moves one step at a time.
  - **Fast Pointer** moves two steps at a time.
- Initialize both pointers at the head of the linked list.
- Traverse the list while the fast pointer and its next node are not `null`.
- If the slow and fast pointers meet at any point, a cycle exists.
- If the fast pointer reaches the end (`null`), there is no cycle.

This approach is also known as the **Tortoise and Hare Algorithm**.

---

## Complexity Analysis

- **Time Complexity:** `O(n)`
  - Each node is visited at most once by the pointers.

- **Space Complexity:** `O(1)`
  - Only two pointers are used, making it an optimal constant-space solution.
