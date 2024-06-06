> [!tip] Given an array consisting of only $0$'s, $1$'s, and $2$'s. Write an algorithm to **in-place sort** the array in single pass $O(N)$ time and constant space.
- This algorithm contains 3 pointers: low, mid, and high, and 3 main rules. The rules are the following:
	- $\text{arr}[0\dots \text{low}-1]$ contains $0$
	- $\text{arr}[\text{low}\dots \text{mid}-1]$ contains 1
	- $\text{arr}[\text{high}+1\dots n-1]$ contains 2