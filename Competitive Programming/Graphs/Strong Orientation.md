- A strong orientation of an undirected graph is an assignment of a direction to each edge that makes it a [[Connected Components#Kosaraju Algorithm|Strongly Connected Component]].
- This cannot be done to every graph. For example, a graph containing a [[Bridges & Articulation Points|Bridge]] can't be strongly oriented as it will become crossable in only one direction.
- Consider a [[DFS]] through a bridgeless connected graph. Clearly, we will each vertex. Since there are no bridges, we can remove any DFS tree edge and still be able to go from below the edge to above the edge by using a path that contains at least one back edge. Therefore, from any vertex, we can go to the root of the DFS tree. Also, from the root of the DFS tree, we can visit any vertex.
- To strongly orient a bridgeless connected graph, run a DFS on it and let the DFS tree edges point away from the DFS root and all other edges from the descendant to the ancestor in the DFS tree.
- The result that bridgeless connected graphs are exactly the graphs that have strong orientations is called **Robbins' Theorem**.
### Extension
- Consider an extension of the orientation problem, where we need to find a graph orientation so that the number of SCC's is minimal.
- Each graph component will be considered separately. Since only bridgeless graphs are strongly orientable, let's remove all bridges temporarily. We end up with some number of bridgeless components (components at beginning + number of bridges) and each can be strongly oriented.
- Since we were only allowed to orient edges and not remove them, we can orient the bridges arbitrarily.
#### Implementation
```cpp

```