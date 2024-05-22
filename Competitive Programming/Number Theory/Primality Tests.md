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
	if (n < 4)
		return n == 2 || n == 3;
	for (int i = 0; i < iter; i++)
	{
		int a = 2 + rand() % (n - 3); // a in [2, n-2]
		if (binpow(a, n-1, n) != 1)
			return false;
	}
	return true;
}
```
Use [[Binary Exponentiation]] to efficiently compute  $a^{n-1}\bmod n$.
## Miller-Rabin Primality Test
Extends the ideas from Fermat Primality Test.
For an odd number $n$, $n-1$ is even, so we factor out all powers of $2$:
$$n-1 = 2^s\cdot d$$
where $d$ is odd.
This allows us to factorize the equation of Fermat's little theorem:
$$
\large{
\begin{align}
a^{n-1}&\equiv 1 \bmod n \iff a^{2^sd} - 1\equiv 0 \bmod n\\
&\iff \left(a^{2^{s-1}d}+1\right)\left(a^{2^{s-1}d}-1\right)\equiv 0 \bmod n\\
&\iff \left(a^{2^{s-1}d}+1\right)\left(a^{2^{s-2}d}+1\right)\left(a^{2^{s-2}d}-1\right)\equiv 0 \bmod n\\
&\vdots\\
&\iff \left(a^{2^{s-1}d}+1\right)\left(a^{2^{s-2}d}+1\right)\cdots\left(a^{2^{0}d}+1\right)\left(a^{2^{0}d}-1\right)\equiv 0 \bmod n
\end{align}
}
$$
If $n$ is prime, then $n$ has to divide one of these factors.
For a base $2\le a\le n-2$ we check if either:
$$\Large a^d\equiv 1\mod n$$
holds or
$$\Large a^{2^rd}\equiv -1\mod n$$
holds for some $0\le r\le s-1$
