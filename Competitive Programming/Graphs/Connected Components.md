> [!tip] Given an undirected graph $G$ with $V$ nodes and $E$ edges, find in it all the connected components, i.e. several groups of vertices such that within a group each vertex can be reached from another and no path exists between different groups.
- We can use [[DFS]] or [[BFS]]. We will do a series of rounds of DFS.
- The first round will start from first node and all nodes in the first connected component will be traversed. Then we traverse the first unvisited node of the remaining nodes and run DFS on it thus finding the second connected component. Repeat the process until all nodes are visited.
- Time Complexity: $O(V+E)$
```cpp
vector<bool> visited;
vector<int> component;

void DFS(vector<vector<int>> adj, int vertex)
{
	visited[vertex] = true;
	component.emplace_back(vertex);
	for (int i : adj[vertex])
		if (!visited[i])
			DFS(adj, i);
}

vector<vector<int>> connectedComponents(vector<vector<int>> adj)
{
	vector<vector<int>> components;
	for (int i = 0; i < adj.size(); i++)
	{
		if (!visited[i])
		{
			component.clear();
			DFS(adj, i);
			components.emplace_back(component);
		}
	}
	return components;
}
```
## Condensation Graph\
Given a directed graph $G$ with vertices $V$ and edges $E$:
**Strongly Connected Component:** is a maximal subset of vertices $C$ such that any two vertices of this subset are reachable from each other. For any $u, v\in C$:
$$
u\mapsto v,  v\mapsto u
$$
where $\mapsto$ means existence of the path from first vertex to the second.
- Strongly connected components do not intersect each other and it is a partition of all graph vertices.
- Thus we can give a definition of condensation graph $G^\text{SCC}$ as a graph containing every strongly connected component as one vertex.
- Each vertex of the condensation graph corresponds to the SCC of graph $G$. There is an oriented edge between two vertices $C_{i}$ and $C_{j}$ of the condensation graph iff there are two vertices $u\in C_{i},\ v\in C_{j}$ such that there is an edge in initial graph $(u, v)$.
- Condensation graph is acyclic. Suppose there is an edge between $C$ and $C'$, then there can't be an edge from $C'$ to $C$.
### Kosaraju Algorithm
- Based on [[DFS]] with time complexity $O(V+E)$.
- We start at each vertex of the graph and run a DFS from every non-visited vertex. For each vertex we keep track of exit time `tout[v]`.
- The exit time `tout[C]` from the SCC $C$ is the maximum of values `tout[v]` for all $v\in C$. Similarly, the entry time `tin[C]` from SCC $C$ is the minimum of values `tin[v]` for all $v\in C$.
- Let $C$ and $C'$ be two different SCC and there be an edge $(C, C')$ in the condensation graph between these two nodes. Then `tout[C] > tout[C']`. Depending on difference between `tin[C]` and `tin[C']`:
	- If the component $C$ was reached first, it means that DFS comes at some vertex $v\in C$ at some moment, but all other vertices of components $C$ and $C'$ were not visited yet. By condition there is an edge $(C, C')$ in a condensation graph, so not only the entire component $C$ is reachable from $v$ but the whole component $C'$ is reachable as well. It means that DFS that is running from vertex $v$ will visit all vertices of components $C$ and $C'$, so they will be descendants for $v$ in a DFS tree. For each vertex $u\in C\cup C',\ u\ne v$ we have `tout[v] > tout[u]`.
	- If the component $C'$ was visited first, it means that DFS comes at some vertex $v\in C'$ at some moment, but all other vertices of components $C$ and $C'$ were not visited yet. By condition there is an edge $(C, C')$ in the condensation graph, so because of acyclic property, there is no back path from $C'$ to $C$, thus DFS from $v$ will not reach vertices of $C$. It means that vertices of $C$ will be visited by DFS later so `tout[C] > tout[C']`.
- If we sort all vertices $v\in V$ in decreasing order of their exit time `tout[v]` then the first vertex $u$ is going to belong to the **root** SCC and will have no incoming edges in the condensation graph.