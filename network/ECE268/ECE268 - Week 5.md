gcd(84,30) = gcd(54,30) = gcd(24,30) = gcd(6,24) = 6

Fermat's little theorem $a^p = a(modp)$
Euler's Theorem $a^{\phi(m)}=1(modm)$

RSA Key Generation
1. Choose two large primes p, q
2. Compute n = p * q
3. Compute $\phi(n) = (p-1)*(q-1)$
4. Select the public exponent $e \in \{1,2,...,\phi(n)-1\}$ st $gcd(e,\phi(n)) = 1$
5. Compute the private key $d$ such that $d * e = 1mod\phi(n)$
6. Return $k_{pub} = (n,e),k_{pr} = d$

Square and multiply - even with this, RSA can still be slow due to computationally expensive modular exponentiation