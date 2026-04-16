Introduction to Cryptography

Symmetric - all old schemes prior 1976
Asymmetric - public-key proposed by Diffie, Hellman, and Merkle in 1976

Symmetric (private-key, secret-key, single-key)
- $x$: plaintext, $y$: ciphertext, $K$: key, ${K_1,K_2,K_n}$: keyspace

$d_k (y) = d_k (e_k (x))$

$\rightarrow$ Problem is secure transmission and storage of key $K$

Kerchkhoff's Principle - cryptosystem should be secure if attacker know all details of system, except for the key

$\rightarrow$ Only use well known ciphers

Brute-Force Attack
- Check all possible keys until condition met $d_k (y_0) \stackrel{?}{=} x_0$

Substitution Cipher - encrypts at letter level
- Large keyspace, but vulnerable to analytical attacks

Modular Arithmetic
- Discrete and finite

a = r mod m

m is modulus
r is remainder

12 can be represented by 3  (mod 9)
12 can also be represented by 21 (mod 9)


---

Properties of Modular Arithmetic
1. Exponentiation followed by modular reduction
	$3^8 =6561 = 2mod7$
2. Exponentiation with intermediate modular reduction
	 $3^8 = 81 \times 81 = 4 \times 4 mod 7 = 2 mod 7$

The ring $Z_m$ - structure which we can always add, subtract and multiple but only divide by certain elements

$Z_g = \{0, 1,2,3,4,5,6,7,8 \}$
0,3,6 do not have inverses since not coprime to 9

Shift/Caesar Cipher - Ring of modulus 26
- Encrypt: $(x+k)mod26$
- Decrypt: $(y-k)mod26$

Affine Cipher - also multiply by key $k=(a,b)$
- Encrypt: $(ax+b)mod26$
- Decrypt: $a^{-1}(y-b)mod26$

Stream Ciphers
- Encrypt bits individually $\rightarrow$ small and fast (embedded)
- Encrypt: $(x_i + s_i )mod2$
- Decrypt: $(y_i + s_i)mod2$
- Key $s_i$ should be random, and reproducible by sender/receiver
- Usually has higher throughput than block ciphers

Random Number Generators
- True RNG: physical random process (coin flip, dice rolling, clock jitter of digital circuits)
- Pseudorandom NG: Generate sequences from initial seed value
	- Simple PRNG: Linear Congruential Generator
		- $S_0 = \text{seed}$
		- $S_{i+1} = AS_i + B\text{mod}m$
		- Unknown $A$, $B$ and $S_0$ as key
		- Solving - can easily solve for A and B from the linear system
		- $S_2 = AS_1 + B \text{mod}m$
		- $S_3 = AS_2 + B\text{mod}m$
- Cryptographically secure RNG: Output must be unpredictable

One-Time Pad (OTP) 
- Cryptosystem unconditionally secure (cannot be broken with infinite compute)
- Encrypt: $x_i \oplus k_i$
- Decrypt: $y_i \oplus k_i$
- Key must be as long as the message, almost all applications its impractical

