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
## Fermat Primality Test
- This is a probabilistic test based on [[Fermat's Little Theorem]].
- We pick an integer $a$ such that $2\le a\le p-2$, and check if the equation holds or not. If it doesn't hold, we know that $p$ cannot be a prime number. Here, the base $a$ will be called a **Fermat Witness** for the compositeness of $p$.
- However, it is possible that the equation holds for a composite number. So if the equation holds, we don't have proof for primality. We only can say that $p$ is **probably** a prime. If it turns out that $p$ was composite, we call the base $a$ a **Fermat Liar**.
- The test will be repeated several times with random choices for $a$, if we find no Fermat Witness, it is very likely that the number is in fact prime.
- There exist some composite numbers $p$, where $a^{p-1}\equiv 1 \pmod p$ holds for all $a$ coprime to $p$. Such numbers are called **Carmichael Numbers**. The Fermat Primality test can identify these numbers only if we choose a base $a$ with $\gcd(a, p) \ne 1$.
- There are very few Carmichael numbers, only 646 exist below $10^9$.
```cpp
bool isPrimeFermat(int n, int iter=10)
{
	
}
```