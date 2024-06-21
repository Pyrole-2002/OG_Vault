- We have a weighted graph with $n$ vertices and $m$ edges. The weights of all edges are non-negative. We are given a starting vertex $s$. We will then find the lengths of the shortest paths from a starting vertex $s$ to all other vertices. This problem is also called single-source shortest paths problem.
- Create an array $d$ where for each vertex $v$ we store the current length of the shortest path from $s$ to $v$ in `d[v]`.
- Initially, `d[s] = 0`, and for all other vertices this length equals infinity.
$$
d[v] = \infty\quad \forall\quad v\ne s
$$
- We also maintain a boolean array $u$ which stores for each vertex $v$ whether it's marked. Initially, all vertices are unmarked.
- Dijkstra's Algorithm runs for $n$ iterations. At each iteration, a vertex $v$ is chosen as unmarked vertex which has least value of $d$.