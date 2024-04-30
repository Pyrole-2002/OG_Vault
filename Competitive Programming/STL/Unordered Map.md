- Unordered Map is a container that stores key-value and mapped-value pairs, like [[Map]].
- Internally, unordered map is implemented using [[Hash Table]], the key provided is hashed into indices of a hash table which is why performance depends on the hash function.
- On average, the cost of search, insert and delete is $O(1)$.
## Syntax
```cpp
unordered_map<object_type1, object_type2> variable_name;
```