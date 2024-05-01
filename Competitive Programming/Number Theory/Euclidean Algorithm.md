Given two non-negative integers $a$ and $b$, Euclidean Algorithm helps find the GCD for both.
$$
\gcd(a, b) =
\begin{cases}
a, & \text{if } b = 0\\
\gcd(b, a\bmod{b}), & \text{otherwise}
\end{cases}
$$
#### Implementation
```cpp
// recursive (slower)
int gcdRecursive1(int a, int b)
{
	if (b == 0)
	{
		return a;
	}
	else
	{
		return gcd(b, a % b);
	}
}

int gcdRecursive2(int a, int b)
{
	return b ? gcd(b, a % b) : a;
}

// iterative (faster)
int gcdIterative(int a, int b)
{
	while (b)
	{
		a %= b;
		swap(a, b);
	}
	return a;
}
```

> [!tip] Always use C++ inbuilt [[Tricks#Inbuilt GCD|GCD]] function.

## Time Complexity
- The time complexity of Euclidean Algorithm is estimated by Lame's Theorem, which establishes a connection between the Euclidean Algorithm and the [[Fibonacci Computation]].
- Consecutive Fibonacci Numbers are the worst case input for Euclidean Algorithm.
- Given that the Fibonacci Numbers grow exponentially, the Euclidean Algorithm works in $O\Big(\log\big(\min(a, b)\big)\Big)$.