- Given a weighted directed graph $G$ with $V$ vertices and $E$ edges, and some vertex $v$, we will find the length of shortest paths from vertex $v$ to every other vertex.
- Unlike [[Dijkstra's Algorithm]], this can also be applied to graphs containing negative weight edges. However, if the graph contains a negative cycle, then the shortest path to some vertices may not exist. This algorithms can also detect the presence of a cycle of negative weight and deduce this cycle.
- First assume that the graph contains no negative weight cycle. We create a distance array $d$ of size $V-1$, which after completion of the algorithm will contain the answer to the problem. Initialize `d[v] = 0`, and all other elements of $d$ to $\infty$.
- The algorithm consists of phases, each phase scans through all edges of the graph, and the algorithm tries to produce relaxation along each edge $(a, b)$ having weight $c$. Relaxation attempts to improve the value of $d[b]$ using value of $d[a]+c$.
- $n-1$ phases of relaxation are sufficient to correctly calculate the lengths of all shortest paths in the graph. For unreachable vertices, $d$ remains $\infty$.
- We check if $a$ is less than $\infty$ because the graph contains negative weights.
##### Simplest Implementation
```cpp
int n;
vector<Edge> edges;
vector<int> d;

void bellmanFord(int v)
{
	d[v] = 0;
	for (int i = 0; i < n - 1; i++)
		for (auto e : edges)
			if (d[e.a] < INF)
				d[e.b] = min(d[e.b], d[e.a] + e.cost);
}
```
