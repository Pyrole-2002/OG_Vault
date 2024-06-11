![[Pasted image 20240607182351.png]]
In the Pascal's Triangle, the $k^\text{th}$ entry in the $n^\text{th}$ row is denoted by $\binom{n}{k}$ ($1$ indexed).
We can see the downward construction of the Pascal's Triangle using the formula:
$$
\binom{n}{k} = \binom{n-1}{k-1} + \binom{n-1}{k}
$$
where $0\le k\le n$. This is known as **Pascal's Rule**.
Classic formula:
$$
\binom{n}{r} = \frac{n!}{r!\cdot (n-r)!}
$$
Optimized formula:
$$
\binom{n}{r} = \frac{n\cdot(n-1)\cdot(n-2)\dots(n-r+1)}{r\cdot(r-1)\cdot(r-2)\dots 1} = \frac{n}{1}\cdot\frac{n-1}{2}\cdot\frac{n-2}{3}\cdots\frac{n-r+1}{r}
$$
```cpp
int nCr(int n, int r)
{
	long long res = 1;
	for (int i = 0; i < r; i++)
	{
		res *= n - i;
		res /= i + 1;
	}
	return res;
}

int pascalTriangle(int r, int c)
{
	return nCr(r - 1, c - 1;)
}
```
Time Complexity: $O(c)$ where $c$ is column number.
Space Complexity: $O(1)$