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
	if (n > 1) // prime numbers
		factorization.emplace_back(n);
	return factorization;
}
```
### Wheel Factorization
- Optimization of the trial division.
- One we know that the number is not divisible by 2, we don't check other even numbers. After factoring out 2 and getting an odd number, we simply start with 3 and only consider other odd divisors.
- When extended further, if the number is not divisible by 3, we can also ignore all other multiples of 3.
- Simply, we can also ignore all multiples of 5 once the number isn't divisible by 5.
- It is best to store the skipping strides.
```cpp

```