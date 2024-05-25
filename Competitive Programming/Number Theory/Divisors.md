## Number of Divisors
If the prime factorization of $n = p_1^{e_1}\cdot p_2^{e_2}\dots p_k^{e_k}$, where $p_i$ are distinct prime numbers, then the number of divisors is:
$$d(n) = (e_1+1)(e_2+1)\dots(e_k+1)$$
```cpp
long long numDivisors(long long num)
{
	long long total = 1;
	for (int i = 2; (long long)i*i <= num; i++)
	{
		if (num % i == 0)
		{
			int e = 0;
			do
			{
				num /= i;
				e++;
			} while (num % i == 0);
			total *= e + 1;
		}
	}
	if (num > 1)
		total *= 2;
	return total;
}
```