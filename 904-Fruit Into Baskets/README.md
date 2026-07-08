# 904. Fruit Into Baskets

## Problem Overview

You are visiting a farm with a single row of fruit trees. Each tree produces one type of fruit.

You have **two baskets**, and each basket can hold **only one type of fruit**. There is no limit to how many fruits of that type a basket can hold.

You can start collecting fruits from **any tree**, but once you start:

* You must move **only to the right**.
* You must pick **one fruit from every tree** you pass.
* You **cannot skip** any tree.
* If you reach a tree whose fruit type does not fit into either of your two baskets, you must stop collecting.

Your goal is to collect the **maximum number of fruits** possible.

---

## Examples

### Example 1

**Input**

```text
fruits = [1,2,1]
```

**Output**

```text
3
```

**Explanation**

There are only two types of fruits (`1` and `2`), so both baskets can hold them. You can collect fruits from all three trees.

---

### Example 2

**Input**

```text
fruits = [0,1,2,2]
```

**Output**

```text
3
```

**Explanation**

If you start from the second tree, you collect:

```text
[1,2,2]
```

This sequence contains only two fruit types (`1` and `2`), allowing you to collect **3 fruits**.

---

### Example 3

**Input**

```text
fruits = [1,2,3,2,2]
```

**Output**

```text
4
```

**Explanation**

The best starting point is the second tree. The collected fruits are:

```text
[2,3,2,2]
```

Since there are only two fruit types (`2` and `3`), you can collect **4 fruits** before encountering a different fruit type.

---

## Constraints

* The number of trees ranges from **1 to 100,000**.
* Each tree contains exactly one type of fruit.
* Fruit types are represented by integers.

---

## Key Idea

The problem is asking for the **longest continuous sequence of trees that contains no more than two different types of fruits**.

Because you only have **two baskets**, you can carry at most **two distinct fruit types** while moving continuously to the right.

The answer is the maximum number of consecutive trees that satisfy this condition.
