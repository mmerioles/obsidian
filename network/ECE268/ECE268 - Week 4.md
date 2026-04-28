Electronic Code Book mode (ECB)
- Each block is encrypted separately into b-bit blocks
- Adv: no block sync, bit errors only affect corresponding block, can operate in parallel
- Disadv: deterministic, same message sent twice is recognizable, substitution attack, can't obscure higher-order patterns

Cipher Block Chaining mode (CBC)
- Cipher text depends on all previous blocks
- Encryption is randomized by using an initialization vector (IV)

Output Feedback mode (OFB)
- Build synchronous stream cipher from block cipher

Cipher Feedback mode (CFB)
- Key stream generated in a block wise fashion for async stream cipher

Counter mode (CTR)
- Useful for high-speed implementations

Galois Counter Mode (GCM)
- Computes a message auth, and checksum for integrity

---


Meet in the middle attack
- Phase I: left encryption is brute-forced for all $k_{I,j}$ and stored $2^k$
- Phase II: right encryption is brute-forced and checked against the stored keys

Public Key Cryptography (Asymmetric)
- Symmetric algorithms are secure but hard to transport the secret key
- "Good old mailbox" idea - everyone can drop a message, only owner can open
- Bob has private key, Alice has public key (announced from Bob)
	- Alice encrypts with public key, drops it in "mailbox", only Bob can open and decrypt with private key
- Use the public key cryptography to move to a secure channel (private key) for less overhead

Basic Key Transport Protocol (Hybrid)
- Key exchange (for symmetric schemes) and digital signatures are performed with (slow) asymmetric algorithms
- Encryption of data is done using (fast) symmetric ciphers, block ciphers or stream ciphers

How to build Public-key algorithms (3 main families of one-way functions)
- Factoring integers - given composite integer, find prime factors
- Discrete Logarithm - given a, y, and m, find x st $a^x =ymodm$
- Elliptic Curves - generalization of discrete logarithm