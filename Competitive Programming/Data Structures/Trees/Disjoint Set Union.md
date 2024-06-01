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