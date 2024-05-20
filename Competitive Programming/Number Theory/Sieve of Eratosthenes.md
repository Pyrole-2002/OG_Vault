Sieve of Eratosthenes is an algorithm for finding all the prime numbers in a segment $[1;n]$ using $O(n\log\log n)$ time complexity.
#### Steps:
1. At the beginning, we write down all numbers between $2$ and $n$.
2. Mark $2$ as prime. Mark all proper multiples of $2$ as composite.
3. Find the next number that hasn't been marked composite and mark it as prime. Then mark all proper multiples of this new prime number as composite.
4. Repeat the step $3$ until we have processed all numbers in the row.
```cpp
vector<bool> sieveOfEratosthenes(int n)
{
	vector<bool> is_prime(n + 1, true);
	is_prime[0] = is_prime[1] = false; // 0 and 1 are not prime numbers
	for (int i = 2; i <= n; i++)
	{
		if (is_prime[i] && (long long)i*i <= n)
		{
			for (int j = i * i; j <= n; j += i)
			{
				is_prime[j] = false;
				cout << "j: " << j << endl;
			}
		}
	}
	return is_prime;
}
```
