Calculates $A^B$ in $O(\log B)$ instead of usual $O(B)$
- **Case 1:** If $B = 0$, result will always be $1$.
- **Case 2:** If $B$ is even, then we calculate $((A^2)^{\frac{B}{2}})$.
- **Case 3:** If $B$ is odd, then we calculate $(A \times (A^{\frac{B-1}{2}}) ^ 2)$.

```cpp
long long binpow(long long A, long long B) // recursive
{
    if (B == 0)
        return 1;
    long long res = binpow(A, B / 2);
    if (B & 1) // Odd
        return res * res * A;
    else
        return res * res;
}
```

```cpp
long long power(long long a, long long b) // iterative (faster)
{
    long long result = 1;
    while(b)
		{
        if (b & 1) 
			result = result * a;
        a = a * a;
        b >>= 1;
    }
    return result;
}
```

> [!tip] When multiplying two big numbers, $a$ and $b$ modulo $m$, the product may be too big to fit in the data-type. So we use a variation of binary exponentiation to compute $a \cdot b \mod m$.
