- Sparse table is a data structure that allows answering range queries.
- It can answer most range queries in $O(\log n)$, but its true power is answering range minimum queries (or equivalent range maximum queries) in $O(1)$ time.
- Only drawback is that it can be used only on immutable arrays. The array cannot be changed between two queries. If any element in the array changes, the complete data structure has to be recomputed.
- Just like binary numbers, any non-negative number can be represented uniquely as a sum of decreasing powers of $2$ (these powers are called summands). For a number $x$, there can be at most $\lceil\log_{2}x\rceil$.
- By the same logic, any interval can be uniquely represented as a union of intervals with lengths that are decreasing powers of $2$. The union consists of at most $\lceil\log_{2}(\text{len})\rceil$ intervals, where $\text{len}$ is the length of the original interval.
### Precomputation
- We use a 2-dimensional array for storing the answers to the precomputed queries.
- `st[i][j]` will store the answer for the range $[j, j+2^i-1]$ of length $2^i$.
- The size of the 2-dimensional array will be $(K+1)\times\text{MAXN}$, where $\text{MAXN}$ is the biggest possible array length we want to handle.