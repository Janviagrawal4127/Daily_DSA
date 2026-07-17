# Letter Combinations of a Phone Number

## Description

Given a string containing digits from **2 to 9**, generate all possible letter combinations that the number could represent based on the standard telephone keypad mapping.

Each digit maps to a set of characters:

* 2 → abc
* 3 → def
* 4 → ghi
* 5 → jkl
* 6 → mno
* 7 → pqrs
* 8 → tuv
* 9 → wxyz

The goal is to return every possible combination of letters formed by choosing one letter for each digit.

---

## Approach

This problem is solved using the **Backtracking** technique.

1. Create a mapping of digits (`2-9`) to their corresponding letters.
2. Start from the first digit and recursively explore every possible letter.
3. Append a letter to the current combination and move to the next digit.
4. When the current combination's length becomes equal to the number of input digits, add it to the result list.
5. Backtrack by removing the last added letter and continue exploring the remaining possibilities.
6. Repeat this process until all possible combinations have been generated.

Backtracking efficiently explores every valid combination while avoiding unnecessary extra space for intermediate strings.
