Depth First Search is a basic searching algorithm on [[Graphs Representation|Graphs]].
- DFS finds the lexicographical first path in the graph from a source vertex $s$ to each vertex.
- Time Complexity: $O(V+E)$
- The idea is to go as deep into the graph as possible and backtrack once we are at a vertex without any unvisited adjacent vertices.
### Classification of Edges
We classify the edges of a graph $G$, using the entry and exit time of the end nodes $u$ and $v$ of the edge $(u,v)$.
We perform DFS and classify the encountered edges using the following rules:
##### If $v$ is not visited
- **Tree Edge:** If $v$ is visited after $u$ then edge $(u, v)$ is called a tree edge. In other words, if $v$ is visited for the first time and $u$ is currently being visited then $(u, v)$ is called tree edge. These edges form a DFS tree and hence the name tree edges.
##### If $v$ is visited before $u$
- **Back Edge:** If $v$ is an ancestor of $u$, then the edge $(u, v)$ is a back edge. $v$ is an ancestor exactly if we already entered $v$, but not exited it yet. Back edges complete a cycle as there is a path from ancestor $v$ to descendant $u$ (in the recursion of DFS)