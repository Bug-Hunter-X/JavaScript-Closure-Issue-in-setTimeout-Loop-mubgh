# JavaScript Closure Issue in setTimeout Loop

This repository demonstrates a common JavaScript closure issue that arises when using `setTimeout` within a loop.  The problem stems from how closures capture variables.

The `bug.js` file contains the buggy code, and `bugSolution.js` presents the corrected version.

**Problem:**
The expected output would be numbers 0 through 9 printed sequentially with a delay of 1 second between each. Instead, all 10 iterations print the final value of `i`, which is 10. This is because the callback functions within `setTimeout` only capture the variable `i` by reference, not by value. By the time the `setTimeout` callbacks execute, the loop has already completed, and `i` is 10.

**Solution:**
The solution uses an immediately invoked function expression (IIFE) to create a new scope for each iteration. This allows each callback to capture its own unique value of `i`.  Another approach involves using `let` in the loop as it correctly captures the value.