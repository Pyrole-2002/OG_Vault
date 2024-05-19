The Fibonacci Sequence is defined as follows: $F_0 = 0, F_1 = 1, F_n = F_{n-1} + F_{n-2}$.
Fibonacci numbers have the following properties:
- **Cassini's Identity:** $F_{n-1} \cdot F_{n+1} - F_n^2 = (-1)^n$
- **Addition Rule:** $F_{n+k} = F_k \cdot F_{n+1} + F_{k-1} \cdot F_n$
- When $k=n$, $F_{2n} = F_n(F_{n+1} + F_{n-1})$. By induction, for any positive integer $k$, $F_{nk}$ is multiple of $F_n$. The inverse is also true: if $F_m$ is multiple of $F_n$, then $m$ is a multiple of $n$.
- **GCD Identity:** $\text{GCD}(F_m, F_n) = F_{\text{GCD}(m, n)}$
- Fibonacci numbers are the worst possible inputs for [[Euclidean Algorithm]] according to Lame's Theorem.
- **Binet's Formula:** $\Large{F_n = \frac{\left(\frac{1+\sqrt 5}{2}\right)^n - \left(\frac{1-\sqrt 5}{2}\right)^n}{\sqrt 5}}$, for $n > 1$, since the $2^{\text{nd}}$ term approaches $0$ exponentially: $\Large{F_n = \frac{\left(\frac{1+\sqrt 5}{2}\right)^n}{\sqrt 5}}$
### Matrix Form of Fibonacci Numbers
$$
\begin{pmatrix}
F_{n+1} & F_n\\
F_n & F_{n-1}
\end{pmatrix}
=
\begin{pmatrix}
1 & 1\\
1 & 0
\end{pmatrix} ^ n
$$
Using [[Binary Exponentiation]] in above, we can calculate $F_n$ in $O(\log n)$ time.
#### Fibonacci Coding
According to Zeckendorf's theorem, any natural number $n$ can be uniquely represented as a sum of Fibonacci Numbers:
$$N = F_{k_1} + F_{k_2} + \dots + F_{k_r}$$
such that $k_n \ge k_{n+1}+2, k_r \ge 2$, meaning that the representation cannot use two consecutive Fibonacci Numbers. 