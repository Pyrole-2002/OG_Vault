A Linear Diophantine Equation (in two variables) is an equation of the general form:
$$ax+by=c$$
where $a, b, c$ are given integers and $x, y$ are unknown integers.
### Degenerate Case
A degenerate case is when $a=b=0$. Either we have no solutions or infinitely many solutions, depending on whether $c=0$ or not.
### Analytic Solution
When $a\ne 0$ and $b\ne 0$, the equation can be equivalently treated as either of the following:
$$
\begin{align}
ax\equiv c\pmod b\\
by\equiv c\pmod a
\end{align}
$$
Without loss of generality, assume that $b\ne 0$ and consider the first equation. When $a$ and $b$ are co-prime, the solution to it is given as:
$$x\equiv ca^{-1}\pmod b$$
where $a^{-1}$ is the [[Modular Arithmetic#Modular Inverse|Modular Inverse]] of $a$ modulo $b$.
When $a$ and $b$ are not co-prime, values of $ax$ modulo $b$ for all integer $x$ are divisible by $g=gcd(a, b)$, so the solution only exists when $c$ is divisible by $g$. In such a case, one of the solutions can be found by reducing the equation by $g$:
$$\left(\frac{a}{g}\right)x\equiv \left(\frac{c}{g}\right) \pmod{b/g}$$
By the definition of $g$, the numbers $\frac{a}{g}$ and $\frac{b}{g}$ are co-prime, so the solution is given explicitly as:
$$
\begin{align}
x &\equiv \left(\frac{c}{g}\right)\left(\frac{a}{g}\right)^{-1}\pmod{b/g}\\
y &= \frac{c-ax}{b}
\end{align}
$$
### Algorithmic Solution
To find one solution of the Diophantine Equation with 2 unknowns, we use the [[Euclidean Algorithm#Extended Euclidean Algorithm|Extended Euclidean Algorithm]].
First, assume that $a$ and $b$ are non-negative:
$$ax_g+by_g=g$$
If $c$ is divisible by $g=\gcd(a, b)$, then the diophantine equation has a solution, otherwise it does not have any solution.
Assuming $c$ is divisible by $g$:
$$ax_g\cdot\frac{c}{g}+by_g\cdot\frac{c}{g} = c$$
Therefore, **one of the solutions** of the diophantine equation is:
$$
\begin{align}
x_0 &= x_g\cdot{c}{g}\\
y_0 &= y_g\cdot{c}{g}
\end{align}
$$