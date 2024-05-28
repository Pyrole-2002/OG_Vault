## Stack Modification
- We will modify the stack data structure in such a way, that it is possible to find the smallest element in the stack in $O(1)$ time, while maintaining the same asymptotic behavior for adding and removing elements from the stack.
- To do this, we will store the elements in the stack in pairs, the element itself and the minimum in the stack starting from this element and below.
- To find the minimum in the whole stack, we just look at the value `stack.top().second`.
```cpp
// Declaration
stack<pair<int, int>> s;

// Adding an element
int new_min = s.empty() ? new_elem : min(new_elem, s.top().second);
s.emplace({new_elem, new_min});

// Removing an element
int rem_elem = s.top().first;
s.pop();

// Find the minimum
int min = s.top().second;
```
## Queue Modification
### Method 1
- We want to add elements at the end and remove them from the front.
- The disadvantage is that the modified queue will actually not store all the elements.
- The idea is to only store the elements in the queue that are needed to determine the minimum.
- The queue is kept in non-decreasing order (head/front is smallest).
- While adding a new element, we remove all elements from the back of the queue that are larger than the new element.
- While removing elements, we only remove the front element if it matches the value we want to remove. If it doesn't match, we do nothing.
```cpp
// Declaration
deque<int> q;

// Find the minimum
int min = q.front();

// Add an element
while (!q.empty() && q.back() > new_elem)
	q.pop_back();
q.emplace_back(new_elem);

// Remove an element
if (!q.empty() && q.front() == rem_elem)
	q.pop_front();
```
### Method 2
- Modification of method 1.
- We want to remove elements without knowing which element we have to remove.
- We do this by storing the index for each element in the queue, and remember how many elements we already have added and removed.
```cpp
// Declaration
deque<pair<int, int>> q;
int cnt_added = 0, cnt_removed = 0;

// Find the minimum
int min = q.front().first;

// 
```