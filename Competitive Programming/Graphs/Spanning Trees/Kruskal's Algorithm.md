- Given a weighted undirected [[Graphs Representation|graph]] $G$ with $V$ vertices and $E$ edges, we will find a spanning tree of this graph which connects all vertices and has the least sum of weights of all edges. A spanning tree is a set of edges such that any vertex can reach any other by exactly one simple path. The spanning tree with the least weight is called a Minimum Spanning Tree.
![[Pasted image 20240703014427.png]]![[Pasted image 20240703014433.png]]
- Kruskal's Algorithm initially places all the nodes of the original graph isolated from each other to form a forest of single node trees and then gradually merges these trees combining at each iteration any two of all the trees with some edge of the original graph.
- Before the execution of the algorithm, all edges are sorted by weight (non-decreasing).
- During unification, pick all edges from the first to the last (in sorted order), and if the ends of the currently picked edge belong to different subtrees, combine the subtrees using the edge.
- After iterating through all edges, all vertices will belong to the same sub-tree and we will get the answer.
### Simplest Implementation
Directly implementing the algorithm results in $O(E\log E+V^2)$ time complexity.
```cpp

```