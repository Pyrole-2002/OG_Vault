- Disjoint Set Union is also known as DSU or Union Find.
- We are given several elements, each of which is a separate set. A DSU will have an operation to combine any two sets, and it will be able to tell in which set a specific element is.
- Thus, the basic interface of this data structure consists of three operations:
	- `make_set(v)` : creates a new set consisting of the new element $v$.
	- `union_sets(a, b)` : merges the set which contains element $a$ and the set which contains the element $b$.
	- `find_set(v)` : returns the representative (leader) of the set that contains the element $v$. This leader is an element of the corresponding set. It is selected in each set by the data structure itself and may change after `union_sets(a, b)` is called. This leader can be used to check if two elements are part of the same set or not. $a$ and $b$ are in the exact same set if `find_set(a) == find_set(b)`. Otherwise, they are in different sets.
- The DSU data structure allows us to do each of these operations in almost $O(1)$ time.
- There also exists an alternative structure of DSU which has a slower average complexity of $O(\log n)$, but can be more powerful than the regular DSU.
In the following image, you can see the representation of such trees:
<Graph indexType="custom" height="200" width="200" nodes={[{label:0,center:{x:214.3,y:147}},{label:1,center:{x:259.1,y:264.5}},{label:2,center:{x:147.6,y:177.6}},{label:3,center:{x:146.3,y:251.5}},{label:4,center:{x:206.1,y:218.5}},{label:5,center:{x:272.3,y:191.8}}]} edges={[{source:0,target:2},{source:0,target:4},{source:0,target:5},{source:1,target:4},{source:1,target:5},{source:2,target:3},{source:2,target:4},{source:4,target:5}]} />

![[temp.png]]