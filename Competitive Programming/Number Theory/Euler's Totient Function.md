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
