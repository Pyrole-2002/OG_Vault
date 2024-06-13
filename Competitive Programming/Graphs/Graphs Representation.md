- A graph is a non-linear data structure consisting of nodes that have data and are connected to other nodes through edges.
![[Pasted image 20240613032827.png|left|400]]          ![[Pasted image 20240613032852.png|right|300]]          ![[Pasted image 20240613132654.png]]
- Nodes (vertices) are circles represented by numbers. The numbering can be done in any order, no specific order needs to be followed.
- An undirected graph is a graph where edges are bidirectional, with no direction associated with them. Pair of vertices to represent any edge is unordered.
- A directed graph is a graph where all the edges are directed from one node to another. Pair of vertices to represent an edge is ordered.
- A graph is called cyclic if we can start traversal from a node and end at the same node.
###### Degree of Graph
- It is the number of edges that go inside or outside that node.
- For undirected graphs, the degree of a node is the number of edges attached to that node.
- For directed graphs, indegree is the number of incoming edges and outdegree is the number of outgoing edges.
- Total degree of a graph is twice to number of edges.
### Representation
The two most commonly used representations for graphs are:
- Adjacency Matrix
- Adjacency List
#### Adjacency Matrix
An adjacency matrix of a graph is a 2-D array of size $n\times n$, where $n$ is the number of nodes in the graph. Here `adj[i][j] = 1` if the edge $(v_{i},v_{j})$ is in the set of edge and `adj[i][j] = 0` if there is no such edge.
```cpp

```