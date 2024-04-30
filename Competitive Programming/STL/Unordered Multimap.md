- The limitation with [[Unordered Map]] is that we cannot store duplicates in it.
- The internal implementation is the same as unordered map but for duplicate keys, another count value is maintained with each key-value pair.
- Pairs with the same keys come together in the data structure but pairs with the same values aren't guaranteed to come together.
## Syntax
```cpp
unordered_multimap<object_type1, object_type2> variable_name;
```

### Functions
```cpp
unordered_multimap<string, int> m;


```