# 876. Middle of the Linked List

## Description

Given the `head` of a singly linked list, return the **middle node** of the linked list.

- If the linked list has an **odd number** of nodes, return the middle node.
- If the linked list has an **even number** of nodes, there will be two middle nodes. Return the **second middle node**.

---

## Example 1

**Input:**

```
head = [1,2,3,4,5]
```

**Output:**

```
[3,4,5]
```

**Explanation:**

The linked list has 5 nodes, so the middle node is `3`. The returned list starts from node `3`.

---

## Example 2

**Input:**

```
head = [1,2,3,4,5,6]
```

**Output:**

```
[4,5,6]
```

**Explanation:**

The linked list has 6 nodes. The two middle nodes are `3` and `4`, so we return the **second middle node**, which is `4`.

---

## Approach (Fast & Slow Pointer)

- Initialize two pointers:
  - **Slow Pointer** moves one node at a time.
  - **Fast Pointer** moves two nodes at a time.
- Start both pointers from the head of the linked list.
- Traverse the list while the fast pointer and its next node are not `null`.
- Move:
  - `slow = slow.next`
  - `fast = fast.next.next`
- When the fast pointer reaches the end of the list, the slow pointer will be at the middle node.
- Return the slow pointer.

This approach naturally returns the **second middle node** when the list contains an even number of nodes.

---

## Complexity Analysis

- **Time Complexity:** `O(n)`
  - The linked list is traversed only once.

- **Space Complexity:** `O(1)`
  - Only two pointers are used, making it an optimal constant-space solution.
