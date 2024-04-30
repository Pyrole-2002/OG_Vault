- Unordered Map is a container that stores key-value and mapped-value pairs, like [[Map]].
- Internally, unordered map is implemented using [[Hash Table]], the key provided is hashed into indices of a hash table which is why performance depends on the hash function.
- On average, the cost of search, insert and delete is $O(1)$.
## Syntax
```cpp
unordered_map<object_type1, object_type2> variable_name;
```

### Functions
```cpp
unordered_map<string, int> m;

// insert(), emplace() and [] can be used to insert elements
m.insert("a", 1);
m.emplace("b", 2);
m["c"] = 3;

// begin() returns an iterator to the first element in the container
```

#### Unordered Map vs [[Unordered Set]]
|                           Unordered Map                           |                           Unordered Set                            |
| :---------------------------------------------------------------: | :----------------------------------------------------------------: |
|         Contains elements in the form of key-value pairs          | Contains independent values, used to see presence/absence of a set |
| Operator `[]` can be used to extract corresponding value to a key |    Searching for an element is done using the `find()` function    |

#### Unordered Map vs [[Map]]
|                            Unordered Map                            |                             Map                              |
| :-----------------------------------------------------------------: | :----------------------------------------------------------: |
|                   Key can be stored in any order                    |               Ordered sequence of unique keys                |
| Implements an unbalanced tree structure, so order is not maintained | Implements a balanced tree structure, so order is maintained |
|          Time complexity of operations is generally $O(1)$          |    Time complexity of operations is generally $O(\log N)$    |
