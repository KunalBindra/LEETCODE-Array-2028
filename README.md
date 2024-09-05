# LEETCODE-Array-2028
This Java class `Solution` implements a method `missingRolls` that calculates an array of missing dice rolls, given an array of known rolls, a target mean, and the number of missing rolls. Here's how it works:

1. **Parameters:**
   - `rolls`: an integer array representing known dice rolls.
   - `mean`: an integer representing the target mean value of all rolls.
   - `n`: the number of missing rolls you need to fill in.

2. **Steps:**
   - The target sum is calculated based on the total number of dice (known and missing) multiplied by the mean.
   - The missing sum is the difference between the target sum and the sum of the known rolls.
   - If the missing sum cannot be distributed among the missing dice (i.e., it’s too large or too small to fit within the bounds of dice values from 1 to 6), the method returns an empty array.
   - Otherwise, it fills the result array with the quotient of the missing sum divided by `n`.
   - Any remainder (`missingSum % n`) is distributed among the first elements of the result array by incrementing them by 1.
   
3. **Edge Cases:**
   - If the `missingSum` is larger than `n * 6` or smaller than `n`, it’s impossible to achieve the desired mean with valid dice values, and an empty array is returned.

### Dry Run Example:
Suppose `rolls = [3, 2, 4]`, `mean = 5`, and `n = 2`.

1. Calculate the target sum:
   - Total rolls: `3 (length of rolls) + 2 (n) = 5`
   - Target sum = `5 * 5 = 25`

2. Calculate the missing sum:
   - Known sum = `3 + 2 + 4 = 9`
   - Missing sum = `25 - 9 = 16`

3. Check if the missing sum is valid:
   - `n = 2`, so the range for valid missing rolls is between `2` and `12`. Since `16` is too large, return `[]`.
