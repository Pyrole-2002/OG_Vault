- Euler's Totient Function aka **Phi-Function $\phi(n)$**, counts the number of integers between $1$ and $n$ inclusive, which are coprime to $n$. $1$ is coprime to every number.
#### Properties:
- If $p$ is a prime number, then $\gcd(p, q) = 1$ for all $1\le q < p$. Therefore:
$$\phi(p) = p-1$$
- If $p$ is a prime number and $k \ge 1$, then there are exactly $\large\frac{p^k}{p}$ numbers between $1$ and $p^k$ that are divisible by $p$. Therefore:
$$\phi(p^k) = p^k - p^{k-1}$$
- If $a$ and $b$ are coprime, then:
$$\phi(ab) = \phi(a)\cdot\phi(b)$$
This relation follows from the [[Modular Arithmetic#Chinese Remainder Theorem|Chinese Remainder Theorem]]. It guarantees that for each $0\le x<a$ and each $0\le y<b$, there exists a unique $0\le z<ab$ with $z \equiv x\pmod a$ and $z\equiv y\pmod b$.
It can be shown that $z$ is coprime to $ab$ if and only if $x$ is coprime to $a$ and $y$ is coprime to $b$.
Therefore the amount of integers coprime to $ab$ is equal to the product of amounts of $a$ and $b$.
- In general, for not coprime $a$ and $b$, the equation is:
$$\phi(ab) = \phi(a)\cdot\phi(b)\cdot\frac{d}{\phi(d)}$$
where $d=\gcd(a, b)$
- Thus using the above properties, we can compute $\phi(n)$ through the factorization of $n$.
If $n = p_1^{a_1}\cdot p_2^{a_2}\dots p_k^{a_k}$ where $p_i$ are prime factors of $n$:
$$
\begin{align}
\phi(n) &= \phi(p_1^{a_1})\cdot \phi(p_2^{a_2})\dots \phi(p_k^{a_k})\\
&= (p_1^{a_1} - p_1^{a_1-1})\cdot (p_2^{a_2} - p_2^{a_2-1})\dots (p_k^{a_k} - p_k^{a_k-1})\\
&= p_1^{a_1}\left(1-\frac{1}{p_1}\right)\cdot p_2^{a_2}\left(1-\frac{1}{p_2}\right)\dots p_k^{a_k}\left(1-\frac{1}{p_k}\right)\\
&= n\cdot \left(1-\frac{1}{p_1}\right)\cdot \left(1-\frac{1}{p_2}\right)\dots \left(1-\frac{1}{p_k}\right)
\end{align}
$$
```cpp
int phi(int n)
{
	int result = n;
	for (int i = 2; i*i <= n; i++)
	{
		if (n % i == 0)
		{
			while (n % i == 0)
				n /= i;
			result -= result / i;
		}
	}
	if (n > 1)
		result -= result / n;
	return result;
}
```

---
https://cp-algorithms.com/algebra/phi-function.html