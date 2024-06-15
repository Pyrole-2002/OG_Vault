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