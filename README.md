# PHP Foreach Loop with Unset() Bug

This repository demonstrates a common, yet subtle bug in PHP related to using the `unset()` function within a `foreach` loop that iterates over an array.  When `unset()` is used to remove an element from the array during iteration, the loop's internal pointer can skip elements, resulting in unexpected behavior. 

The `bug.php` file contains the problematic code, while `bugSolution.php` offers a corrected and more robust solution.

## Bug Explanation
The core issue is that modifying the array within a `foreach` loop using `unset()` can alter the internal array pointer.  This leads to potentially skipping elements or producing inconsistent results.  The bug is most evident when the array has numeric keys.

## Solution
The solution is to iterate over the array using a `for` loop or using the `array_keys` function and manipulating the array using the keys.