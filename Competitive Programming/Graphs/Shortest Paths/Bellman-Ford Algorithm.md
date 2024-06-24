- Given a weighted directed graph $G$ with $V$ vertices and $E$ edges, and some vertex $v$, we will find the length of shortest paths from vertex $v$ to every other vertex.
- Unlike [[Dijkstra's Algorithm]], this can also be applied to graphs containing negative weight edges. However, if the graph contains a negative cycle, then the shortest path to some vertices may not exist. This algorithms can also detect the presence of a cycle of negative weight and deduce this cycle.
- First assume that the graph contains no negative weight cycle. We create a distance array $d$ of size $V-1$, which after completion of the algorithm will contain the answer to the problem. Initialize `d[v] = 0`, and all other elements of $d$ to $\infty$.
- The algorithm consists of phases, each phase scans through all edges of the graph, and the algorithm tries to produce relaxation along each edge $(a, b)$ having weight $c$. Relaxation attempts to improve the value of $d[b]$ using value of $d[a]+c$.
- $n-1$ phases of relaxation are sufficient to correctly calculate the lengths of all shortest paths in the graph. For unreachable vertices, $d$ remains $\infty$.
- We check if $a$ is less than $\infty$ to skip the edges where path to $a$ has not yet been found.
## Proof
- Note that for all unreachable vertices $u$, the algorithm works correctly as the $d[u]$ remains $\infty$.
- To Prove: After the execution of $i_{\text{th}}$ phase, the algorithm correctly finds all shortest paths whose number of edges doesn't exceed $i$.
- Consider an arbitrary vertex $a$ to which there is a path from the starting vertex $v$, and consider a shortest path to it $(p_{0}=v, \dots, p_{k}=a)$.
- Before the first phase, the shortest path to $p_{0}$ was found correctly. During first phase, the edge $(p_{0}, p_{1})$ has been checked and the distance to the vertex $p_{1}$ was found correctly. Repeating this $k$ times will find the distance to the vertex $p_{k}$ correctly.
- Any shortest path can't have more than $n-1$ edges..
##### Simplest Implementation
```cpp
int n;
vector<Edge> edges;
vector<int> d;

void bellmanFord(int v)
{
	d.resize(n, INF);
	d[v] = 0;
	for (int i = 0; i < n - 1; i++)
		for (auto e : edges)
			if (d[e.a] < INF)
				d[e.b] = min(d[e.b], d[e.a] + e.cost);
}
```
##### Better Implementation
- To speed up this algorithm, we keep a flag to tell whether relaxation happened in the current phase or not, if in any phase relaxation had no change, the algorithm can be stopped.
- We can modify the algorithm so it allows to reconstruct the shortest paths.
```cpp
int n;
vector<Edge> edges;
vector<int> d, p;

void bellmanFord(int v)
{
	d.resize(n, INF);
	p.resize(n, -1);
	d[v] = 0;
	bool flag = false;
	for (int i = 0; i < n - 1; i++)
	{
		for (auto e : edges)
			if (d[e.a] < INF && d[e.a] + e.cost < d[e.b])
			{
				d[e.b] = d[e.a] + e.cost;
				p[e.b] = e.a;
				flag = true;
			}
		if (!flag)
			break;
	}
}
```
### Negative Cycles