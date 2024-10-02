# Step-by-Step Guide to Solving a DSA Problem

## Step 1: Understand the Problem

Before jumping into the code, you need to fully understand the problem.

### What is an Array?

An array is a collection of items stored in a contiguous block of memory. In this case, it holds integers.

### What is the Goal?

You need to go through the array and return the largest number present.

### Edge Cases

1. **Empty array**: What should happen if the array has no elements? This could result in an error or need a specific return value.
2. **Array with one element**: The maximum is the only element.
3. **Negative numbers**: The array may contain negative values, so ensure you're not assuming only positive numbers.
4. **All elements are the same**: Ensure the function works when all numbers are identical.

### Test Cases

1. `[3, 1, 5, 2, 4]`: Normal case with positive integers.
2. `[-3, -1, -5, -2, -4]`: All numbers are negative.
3. `[100]`: Single element.
4. `[]`: Empty array.
5. `[7, 7, 7]`: All elements are the same.

## Step 2: Plan the Solution

Now that you understand the problem, think of a logical plan or approach.

### Steps:

- **Initialize a variable to store the largest number**.
  Start with the first element of the array and assume it's the largest.
- **Loop through the array**.
  Compare each element with the "largest so far". If an element is larger than your current largest, update the "largest" variable.
- **Return the largest number** once you have looped through the array.

## Step 3: Write the Pseudocode

Pseudocode helps to break down your logic before you write actual code.

```plaintext
1. If the array is empty, return null or some message saying there are no numbers.
2. Assume the first element is the maximum (max = arr[0]).
3. Loop through the array starting from the second element.
4. For each element, if it is greater than the current max, set max to this element.
5. After the loop, the max will contain the largest number.
6. Return the maximum number.
```

## Step 4: Write the Actual Code

Now that you have a clear plan, it’s time to write the code in JavaScript.

### Code Example

```javascript
function findMaxNumber(arr) {
  // Step 1: Handle edge case (empty array)
  if (arr.length === 0) {
    return null; // Or return a message: "Array is empty"
  }

  // Step 2: Assume the first element is the largest
  let max = arr[0];

  // Step 3: Loop through the rest of the array
  for (let i = 1; i < arr.length; i++) {
    // Step 4: If current element is larger than max, update max
    if (arr[i] > max) {
      max = arr[i];
    }
  }

  // Step 5: Return the largest number found
  return max;
}

// Test cases
console.log(findMaxNumber([3, 1, 5, 2, 4])); // Output: 5
console.log(findMaxNumber([-3, -1, -5, -2, -4])); // Output: -1
console.log(findMaxNumber([100])); // Output: 100
console.log(findMaxNumber([])); // Output: null
console.log(findMaxNumber([7, 7, 7])); // Output: 7
```

## Step 5: Test the Solution

Test your code with different inputs to ensure it works for various cases:

1. Normal case with positive numbers: `[3, 1, 5, 2, 4]` should return `5`.
2. Negative numbers: `[-3, -1, -5, -2, -4]` should return `-1` (the largest negative number).
3. Single element: `[100]` should return `100`.
4. Empty array: `[]` should return `null`.
5. Same elements: `[7, 7, 7]` should return `7`.

## Step 6: Analyze Time and Space Complexity

### Time Complexity:

- **O(n)**: You loop through the array once, so the time complexity is O(n), where n is the number of elements in the array.

### Space Complexity:

- **O(1)**: You're using only one extra variable (max), so the space complexity is constant O(1).

## Step 7: Reflect and Improve

After solving the problem, reflect on your approach:

- Did you miss any edge cases? (For instance, when all numbers are the same.)
- Is the solution efficient for large inputs? (Yes, since it runs in linear time.)
