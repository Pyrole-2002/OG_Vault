Depth First Search is a basic searching algorithm on [[Graphs Representation|Graphs]].
- DFS finds the lexicographical first path in the graph from a source vertex $s$ to each vertex.
- Time Complexity: $O(V+E)$
- The idea is to go as deep into the graph as possible and backtrack once we are at a vertex without any unvisited adjacent vertices.
### Classification of Edges
We classify the edges of a graph $G$, using the entry and exit time of the end nodes $u$ and $v$ of the edge $(u,v)$.
We perform DFS and classify the encountered edges using the following rules:
##### If $v$ is not visited
- **Tree Edge:** If $v$ is visited after $u$ then edge $(u, v)$ is called a tree edge.