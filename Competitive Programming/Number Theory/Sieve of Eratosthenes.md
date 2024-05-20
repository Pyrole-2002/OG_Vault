Sieve of Eratosthenes is an algorithm for finding all the prime numbers in a segment $[1;n]$ using $O(n\log\log n)$ time complexity.
#### Steps:
1. At the beginning, we write down all numbers between $2$ and $n$.
2. Mark $2$ as prime. Mark all proper multiples of $2$ as composite.
3. Find the next number that hasn't been marked composite and mark it as prime. Then mark all proper multiples of this new prime number as composite.
4. Repeat the step $3$ until we have processed all numbers in the row.
```cpp
void sieveOfEratosthenes(int n, vector<bool>& is_prime)
{
	
}
```