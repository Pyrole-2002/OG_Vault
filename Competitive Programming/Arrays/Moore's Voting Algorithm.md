> [!tip] Given an array of $N$ integers, write an algorithm to return the element that occurs more than $\frac{N}{2}$ times in the given array.
- We keep a note of two variables `count` and `element`.
- `element` is the value that we are expecting to be the answer.
- `count` is for tracking the count of `element`.
- We start iterating through the array:
	- If `count` is $0$, store the current element of the array as `element`.
	- If the current element is same as `element`, increase `count` by $1$, else decrease `count` by $1$.
- At the end, the element present in `element` should be the answer, if there exists an element which occurs more than $\frac{N}{2}$ times.
- However, if `element` is not in majority, then there exist no other answer. To confirm this, we can traverse the array once more.
```cpp
int majorityElement(vector<int> v)
{
	int n = v.size();
	int count = 0;
	int element;
	for (int i = 0; i < n; i++)
	{
		if (count == 0)
		{
			element = v[i];
			count++;
		}
		else if (element == v[i])
			count++;
		else
			count--;
	}
	// Optional: Check if stored element is majority
	int freq = 0;
	for (int i = 0; i < n; i++)
		if (element == v[i])
			freq++;
	if (freq > (n / 2))
		return element;
	else
		return -1;
}
```
- Time Complexity: $O(2\times N)$
- Space Complexity: $O(1)$
## Extended Voting Algorithm
> [!tip] Given an array of $N$ integers, write an algorithm to return the elements that occurs more than $\frac{N}{3}$ times in the given array.
- Keep a note of 4 variable `cnt1`, `cnt2`, `el1` and `el2`.