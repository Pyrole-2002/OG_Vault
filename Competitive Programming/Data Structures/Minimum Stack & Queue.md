## Stack Modification
We will modify the stack data structure in such a way, that it is possible to find the smallest element in the stack in $O(1)$ time, while maintaining the same asymptotic behavior for adding and removing elements from the stack.
To do this, we will store the elements in the stack in pairs, the element itself and the minimum in the stack starting from this element and below.