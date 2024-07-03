- Given a weighted undirected graph $G$ with $V$ vertices and $E$ edges, we will find a spanning tree of this graph which connects all vertices and has the least sum of weights of all edges. A spanning tree is a set of edges such that any vertex can reach any other by exactly one simple path. The spanning tree with the least weight is called a Minimum Spanning Tree.
![[Pasted image 20240703014427.png]]![[Pasted image 20240703014433.png]]
- Any spanning tree consists of $V-1$ edges.
- The MST is built gradually by adding edges one at a time. At first the tree consists only of a single arbitrary vertex.
- Then the minimum weight edge outgoing from this vertex is selected and added to the MST. This also adds the corresponding vertex to the tree.
- Now select and add the edge with the minimum weight that has one end in an already selected vertex and the other end in an unselected vertex.
- Every time we select and add the edge with minimal weight that connects one selected vertex with one unselected vertex. This is repeated until the MST contains all vertices and $V-1$ edges.
### Trivial Implementation
- If we search the edge by iterating over all possible edges, then it takes $O(E)$ time to find the edge with minimum weight. The total complexity becomes $O(VE)$, in the worst case this becomes $O(V^3)$.
- If we only look at one edge from each already selected vertex, we can sort the edges from each vertex in ascending order of their weights, and store a pointer to the first valid edge.
- Then after finding and selecting the minimal edge, we update the pointers. This gives a complexity of $O(V^2+E)$ and for sorting the edges an additional $O(E\log V)$ which gives the complexity $O(V^2\log V)$ in the worst case.
## Dense Graphs
