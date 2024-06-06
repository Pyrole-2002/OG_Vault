> [!tip] Given an integer array, find the contiguous subarray (containing at least one number) which has the largest sum. Return the sum and print the subarray.
- We iterate the given array and while iterating, we add the elements in a `sum` variable.
- After each update of `sum`, we compare it to the maximum value of `sum` encountered till now and update this maximum value.
- If at any point, `sum` becomes negative, we reset `sum` to $0$ and continue adding it.
```cpp
long long 
```