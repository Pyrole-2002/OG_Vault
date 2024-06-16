- We are given an undirected graph. A bridge is defined as an edge which, when removed, makes the graph disconnected (increases the number of [[Connected Components]]). We will find all bridges in a given graph.
- The algorithm is based on [[DFS]] and has time complexity $O(V+E)$.
- Pick an arbitrary vertex of graph `root` and run DFS from it.
- At any point in DFS, the edge from $(v, to)$ is a bridge iff none of the vertices $to$ and its descendants in the DFS has a back-edge to vertex $v$ or any of its ancestors. This means that there is no other way from $v$ to $to$ except for edge $(v, to)$.
- Let `tin[v]` denote entry time for node $v$. The array `low[]` will let us check the condition for each vertex. `low[v]` is the minimum of `tin[v]`, the entry times `tin[p]` for each node $p$ that is connected to node $v$ via a back-edge $(v, p)$ and the values of `low[to]` for each vertex $to$ which is a direct descendant of $v$ in the DFS tree:
$$
low[v] = \min
$$