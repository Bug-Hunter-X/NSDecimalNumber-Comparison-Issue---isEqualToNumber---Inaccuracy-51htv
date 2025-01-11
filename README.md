# NSDecimalNumber Comparison Issue in Objective-C

This repository demonstrates a subtle bug in Objective-C when comparing `NSDecimalNumber` objects using `isEqualToNumber:`. The issue arises when comparing numbers with the same numerical value but different scales (number of decimal places).  `isEqualToNumber:` returns `NO` in such cases, even though the numbers are numerically equivalent.

The `bug.m` file shows the problematic code, while `bugSolution.m` offers a corrected approach using `compare:` for robust numerical comparison.

## How to Reproduce

1. Clone the repository.
2. Open the project in Xcode.
3. Run the `bug.m` file. Observe the incorrect comparison result.
4. Run the `bugSolution.m` file. Observe the correct comparison result.

## Solution

Instead of `isEqualToNumber:`, use the `compare:` method, which compares the numerical values irrespective of the scale.  This ensures accurate comparisons of `NSDecimalNumber` objects.