> [!tip] Given an array of $N$ integers, write an algorithm to return the element that occurs more than $\frac{N}{2}$ times in the given array.
- We keep a note of two variables `count` and `element`.
- `element` is the value that we are expecting to be the answer.
- `count` is for tracking the count of `element`.
- We start iterating through the array:
	- If `count` is $0$, store the current element of the array as `element`.
	- If the current element is same as `element`, increase `count` by $1$, else decrease `count` by $1$.
- At the end, the element present in `element` should be the answer, if there exists an element which occurs more than $\frac{N}{2}$ times.