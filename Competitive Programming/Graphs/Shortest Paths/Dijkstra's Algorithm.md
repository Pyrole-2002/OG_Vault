- We have a weighted graph with $n$ vertices and $m$ edges. The weights of all edges are non-negative. We are given a starting vertex $s$. We will then find the lengths of the shortest paths from a starting vertex $s$ to all other vertices. This problem is also called single-source shortest paths problem.
- Create an array $d$ where for each vertex $v$ we store the current length of the shortest path from $s$ to $v$ in `d[v]`.
- Initially, `d[s] = 0`, and for all other vertices this length equals infinity.
$$
d[v] = \infty\quad \forall\quad v\ne s
$$
- We also maintain a boolean array $u$ which stores for each vertex $v$ whether it's marked. Initially, all vertices are unmarked.
- Dijkstra's Algorithm runs for $n$ iterations. At each iteration, a vertex $v$ is chosen as unmarked vertex which has least value of $d$.
- The selected vertex $v$ is marked, from $v$ relaxations are performed where all edges of the form $(v, to)$ are considered and for each vertex $to$, the algorithm tries to improve the value $d[to]$. If the length of the current edge is $len$, then relaxation is:
$$
d[to] = \min(d[to,\ d[v]+len])
$$
- After all the edges are considered, the current iteration ends. After $n$ iterations, all vertices will be marked, and the algorithm terminates.
- The found values of $d[v]$ are the lengths of shortest paths from $s$ to all vertices $v$.
### Restoring Shortest Paths
- If we want to know not only the lengths of the shortest paths but the paths themselves, we will maintain an array of predecessors $p$ in which for each vertex $v \ne s$, $p[v]$ is the penultimate vertex in the shortest path from $s$ to $v$.
- We use the fact that if we take the shortest path to some vertex $v$ and remove $v$ from this path, we'll get a path ending in at vertex $p[v]$, and this path will be the shortest for the vertex $p[v]$.
- For each successful relaxation, when for some selected vertex $v$, there is an improvement in the distance to some vertex $to$, we update the predecessor vertex for $to$ with the vertex $v$.
$$
p[to] = v
$$
#### Implementation
- For the simplest implementation, on each iteration vertex search requires $O(n)$ time and each relaxation can be performed in $O(1)$. Asymptotic time complexity becomes $O(V^2 + E)$.
- This complexity is optimal for dense graphs where $E\approx V^2$. However, in sparse graphs where $E$ is much smaller than maximum number of edges $V^2$, the problem can be solved in $O(n\log n+m)$. This will be discussed in future section.