## Enumerating All Submasks of a Given Mask
Given a bitmask $m$, you want to efficiently iterate through all of its submasks, that is, masks $s$ in which only bits that were included in mask $m$ are set. A submask $s$ is any mask that can be formed by clearing some (or none) of the set bits of $m$ to $0$.
We can iterate through the submasks using below implementations:
```cpp
int s = m;
```