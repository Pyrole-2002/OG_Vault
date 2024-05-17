Iterators are used to point at the memory addresses of STL containers. They are primarily used in sequences. They reduce the complexity and execution time of the program.
## Syntax
```cpp
vector<int> v = { 1, 2, 3, 4, 5 };
vector<int>::iterator ptr; // iterator to a vector<int>
ptr = v.begin(); // returns the beginning position of vector
ptr = v.end(); // returns the after end position of the container

```