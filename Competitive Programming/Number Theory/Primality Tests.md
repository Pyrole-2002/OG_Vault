Primality test algorithms determine if a number $n$ is prime or not.
## Trial Division
- A composite number has at least one additional divisor other than $1$ and $n$ (the number itself), let's call this this divisor $d$.
- This means that $\frac{n}{d}$ is also a divisor of $n$.
- Either $d$ or $\frac{n}{d}$ is $\le \sqrt n$.
- We find a non-trivial divisor by checking if any of the numbers between $2$ and $\sqrt n$ is a divisor of $n$.
- Time complexity is $O(\sqrt n)$.
```cpp
bool isPrimeTrial(int n)
{
	for (int d = 2; d*d <= n; d++)
	{
		if (n % d == 0)
			return false;
	}
	return x >= 2;
}
```