## Trial Division
- Divide by each possible divisor $d$.
- Test divisors $2\le d \le \sqrt n$, with a time complexity $O(\sqrt n)$.
- The smallest divisor must be prime, we remove the factored number and continue the process.
- If no divisor found in the range $[2; \sqrt n]$, then the number has to be prime.