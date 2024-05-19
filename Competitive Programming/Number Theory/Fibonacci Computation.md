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
### Fibonacci Coding
According to Zeckendorf's theorem, any natural number $n$ can be uniquely represented as a sum of Fibonacci Numbers:
$$N = F_{k_1} + F_{k_2} + \dots + F_{k_r}$$
such that $k_n \ge k_{n+1}+2, k_r \ge 2$, meaning that the representation cannot use two consecutive Fibonacci Numbers.
Any number can be uniquely encoded in the Fibonacci Encoding, we describe this representation with binary codes $d_0d_1d_2\dots d_s1$, where $d_i$ is $1$ if $F_{i+2}$ is used in the representation. The code is appended by a $1$ to indicate the end of the code word. This is the only occurrence where two consecutive $1$-bits appear.
$$
\begin{align*}
1 &= 1 &&= F_2 &&= (11)_F\\
2 &= 2 &&= F_3 &&= (011)_F\\
3 &= 3 &&= F_4 &&= (0011)_F\\
4 &= 3+1 &&= F_4+F_2 &&= (1011)_F\\
\end{align*}
$$