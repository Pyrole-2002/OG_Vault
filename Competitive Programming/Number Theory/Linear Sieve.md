- Linear Sieve deals with finding all prime numbers in a segment $[2; n]$.
- The standard way of solving this is to use the [[Sieve of Eratosthenes]], but that has runtime $O(n\log\log n)$.
- This algorithm also calculates factorizations of all numbers in the segment $[2; n]$ as a side effect that can be helpful.
- The weakness of linear sieve is using more memory. It makes sense to use this algorithm only for numbers up to order $10^7$.
#### Algorithm
Goal is to calculate Minimum Prime Factor $\text{lp}[i]$ for every $i$ in the segment $[2; n]$. Also store the list of all the found prime numbers in $\text{pr}[]$.
1. Initialize the values of $\text{lp}[i]$ with zeros, assuming all numbers are prime.
2. Iterate $i$ through numbers $2$ to $n$:
	- If $\text{lp}[i] = 0$, $i$ is prime, meaning we haven't found any smaller factors for it. Assign $\text{lp}[i] = i$ and append $i$ to the end of list $\text{pr}[]$.
	- If $\text{lp}[i] \ne 0$, $i$ is composite and its minimum prime factor is $\text{lp}[i]$.
3. Update values of $\text{lp}[]$ for the indexes divisible by $i$.
	1. 