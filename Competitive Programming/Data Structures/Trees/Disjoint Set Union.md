- Disjoint Set Union is also known as DSU or Union Find.
- We are given several elements, each of which is a separate set. A DSU will have an operation to combine any two sets, and it will be able to tell in which set a specific element is.
- Thus, the basic interface of this data structure consists of three operations:
	- `make_set(v)` : creates a new set consisting of the new element $v$.
	- `union_sets(a, b)` : merges the set which contains element $a$ and the set which contains the element $b$.
	- `find_set(v)` : returns the representative (leader) of the set that contains the element $v$. This leader is an element of the corresponding set. It is selected in each set by the data structure itself and may change after `union_sets(a, b)` is called. This leader can be used to check if two elements are part of the same set or not. $a$ and $b$ are in the exact same set if `find_set(a) == find_set(b)`. Otherwise, they are in different sets.
- The DSU data structure allows us to do each of these operations in almost $O(1)$ time.
- There also exists an alternative structure of DSU which has a slower average complexity of $O(\log n)$, but can be more powerful than the regular DSU.
In the following image, you can see the representation of such trees:
![[Pasted image 20240601234100.png|300]]![[Pasted image 20240601234232.png|300]]![[Pasted image 20240601235429.png|200]]
In the beginning, every element starts as a singleton set, each vertex is its own tree. Then we combine the set containing element $0$ and the set containing element $1$. Similarly, we combine sets containing elements $2$ and element $3$. Lastly, we combine the set containing element $0$ and element $2$.
- For the implementation, we will have to maintain an array `parent` that stores a reference to its immediate ancestor in the tree.
# Naive Implementation
- To create a new set `make_set(v)`, we simply create a tree with root as the vertex $v$, which becomes it's own ancestor.
- To combine two sets `union_sets(a, b)`, we first find the representative of the set in which $a$ is located, and the representative of the set in which $b$ is located. If the representatives are identical, we have nothing to do and the sets are already merged. Otherwise, we simply specify that one of the representatives is the parent of the other representative, combining the two trees.
- For finding the representative `find_set(v)`, we simply climb the ancestors of the vertex $v$ until we reach the root (reference to the ancestor leads to itself) using recursion.
```cpp
vector<int> parent;

void make_set(int v)
{
	parent[v] = v;
}

int find_set(int v)
{
	if (v == parent[v])
		return v;
	return find_set(parent[v]);
}

void union_sets(int a, int b)
{
	a = find_set(a);
	b = find_set(b);
	if (a != b)
		parent[b] = a;
}

int main()
{
	ios::sync_with_stdio(false);
	cin.tie(NULL);

	int n = 5; // number of vertices
	parent.resize(n);
	for (int i = 0; i < n; i++)
		make_set(i);

	union_sets(0, 1);
	union_sets(2, 3);
	union_sets(0, 4);
	cout << find_set(0) << endl;
	cout << find_set(1) << endl;
	cout << find_set(2) << endl;
	cout << find_set(3) << endl;
	cout << find_set(4) << endl;

	return 0;
}
```
- However, this implementation is inefficient because the operations may take $O(n)$ time.
## Path Compression
- This optimization speeds up `find_set`.
- If we call `find_set(v)` for some vertex $v$, we actually find the leader $p$ for all vertices that we visit on the path between $v$ and the leader $p$.
- We will therefore make the paths for all nodes shorter, by setting the parent of each visited vertex directly to $p$.
In the below image, on the left is a tree, and on the right is the compressed tree after calling `find_set(7)` which shortens the path for all visited nodes $7\to{5}\to{3}\to{2}\to{1}$.
![[Pasted image 20240602193845.png|400]]![[Pasted image 20240602194242.png]]
```cpp
int find_set(int v)
{
	if (v == parent[v])
		return v;
	return parent[v] = find_set(parent[v]);
}
```
- This modification achieves the time complexity $O(\log n)$ per call on average.
## Union by rank
- In this optimization, we change the `union_set` operation.
- We change which tree gets attaches to the other one. In the naive implementation, the second tree always got attached to the first one. This can lead to trees containing chains of length $O(n)$.
- We popularly use two heuristics:
	1. Using the size of the trees as rank.
	2. Using the depth of the tree as rank.
- We attach the tree with the lower rank to the one with the higher rank.
###### Union By Size
```cpp
void make_set(int v)
{
	parent[v] = v;
	size[v] = 1;
}

void union_sets(int a, int b)
{
	a = find_set(a);
	b = find_set(b);
	if (a != b)
	{
		if (size[a] < size[b])
			swap(a, b);
		parent[b] = a;
		size[a] += size[b]; // update only for leader
	}
}
```
###### Union by Depth of Tree
```cpp
void make_set(int v)
{
	parent[v] = v;
	rank[v] = 0;
}

void union_sets(int a, int b)
{
	a = find_set(a);
	b = find_set(b);
	if (a != b)
	{
		if (rank[a] < rank[b])
			swap(a, b);
		parent[b] = a;
		if (rank[a] == rank[b])
			rank[a]++; // update only for leader
	}
}
```