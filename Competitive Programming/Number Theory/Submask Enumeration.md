## Enumerating All Submasks of a Given Mask
Given a bitmask $m$, you want to efficiently iterate through all of its submasks, that is, masks $s$ in which only bits that were included in mask $m$ are set. A submask $s$ is any mask that can be formed by clearing some (or none) of the set bits of $m$ to $0$.
We can iterate through the submasks using below implementations:
```cpp
for (int s = m; s; s = (s-1)&m)
{
	// code here
}
```
The above loop iterates all submasks of $m$ without repetition and in descending order.
Suppose we have a current bitmask $s$, and we want to move on to the next bitmask, by subtracting $1$ from the mask $s$, we clear the rightmost set bit and set all bits to the right of it. Then we remove all the "extra" $1$ bits that are not included in $m$ and therefore shouldn't be part of submask by taking bitwise AND.