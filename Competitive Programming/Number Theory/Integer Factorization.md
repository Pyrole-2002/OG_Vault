## Trial Division
- Divide by each possible divisor $d$.
- Test divisors $2\le d \le \sqrt n$, with a time complexity $O(\sqrt n)$.
- The smallest divisor must be prime, we remove the factored number and continue the process.
- If no divisor found in the range $[2; \sqrt n]$, then the number has to be prime.
```cpp
vector<long long> factorTrialDivision(long long n)
{
	vector<long long> factorization;
	for (long long d = 2; d*d <= n; d++)
	{
		while (n % d == 0)
		{
			factorization.emplace_back(d);
			n /= d;
		}
	}
	if (n > 1)
		factorization.emplace_back(n);
}
```