
Digital Signature Algorithm (DSA)
- based on elgamal
- 320 bits
- verification slower than rsa

DSA Key Generation
- generate big prime $p$
- find prime divisor of $p-1$
- find integer with $ord(\alpha)=q$
- choose rand int $d$
- compute $\beta \equiv a^d \mod p$

DSA Signature gen
1. compute integer as random ephemeral key
2. compute r
3. compute s

DSA signature verification
1. compute aux values w, u1, u2
2. compute v

Hash function
- iteratively chain hashes for all blocks
