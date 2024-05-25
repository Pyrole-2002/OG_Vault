# Modular Inverse
- A modular multiplicative inverse of an integer $a$ is an integer $x$ such that $a\cdot x$ is congruent to $1$ modular some modulus $m$.
$$a\cdot x\equiv 1\mod m$$
- We can denote $x$ simply with $a^{-1}$.
- Modular inverse does not always exist. Modular inverse exists if and only if $a$ and $m$ are coprime.
### Modular Inverse using [[Euclidean Algorithm#Extended Euclidean Algorithm|Extended Euclidean Algorithm]]
Consider the following equation with unknown $x$ and $y$:
$$ax+my=1$$
This is a [[Linear Diophantine Equation]] in two variables.
Since $a$ and $m$ are coprime, $\gcd(a, m) = 1$ fits the equation in [[Euclidean Algorithm#Extended Euclidean Algorithm|Extended Euclidean Algorithm]].
Taking modulo $m$ on both sides, we get rid of the term $my$:
$$ax\equiv 1\mod m$$
Therefore, the modular inverse of $a$ is $x$.
```cpp
int modInverseExtendedEuclidean(int a, int m)
{
	int x, y;
	int g = gcdExtendedEuclidean(a, m, x, y);
	if (g != 1) // No Solution
		return 0;
	return (x % m + m) % m;
}
```
### Modular Inverse using [[Binary Exponentiation]]
