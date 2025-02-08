# Closure Issue in setTimeout Loop

This repository demonstrates a common closure-related issue in JavaScript when using `setTimeout` within a loop.  The expected behavior is to log numbers 0 through 9 with a one-second delay between each. However, due to how closures work, the code produces an unexpected result.

## Problem
The problem stems from the fact that the `setTimeout` callback function doesn't immediately capture the value of `i`. Instead, it captures a reference to the variable `i`. By the time the `setTimeout` callbacks finally execute, the loop has already completed, and `i` holds its final value of 10.  Therefore, all the `console.log` statements output 10.

## Solution
The solution involves creating a new function scope for each iteration using an immediately invoked function expression (IIFE). This ensures that each callback function captures its own copy of the `i` value.

## How to Run
1. Clone the repository.
2. Open `bug.js` and `bugSolution.js`.
3. Run `bug.js` to see the buggy output.
4. Run `bugSolution.js` to observe the fixed behavior.