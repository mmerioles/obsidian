Linear feedback shift registers (LFSRs)
- $2^m - 1$ where $m$ is a prime number
- Typically described by polynomial
$$P(x) = x^m + p_{l-1}x^{m-1} + ... + p_1x + p_0$$
- Single LFSRs produce highly reproducible output

Modern Stream Cipher - Trivium
- Three nonlinear LFSRs, XOR-Sum of all three outputs

Two primitive operations
- Confusion - relationship between key and ciphertext is obscured (substitution)
- Diffusion - influence of one plaintext symbol is spread over many ciphertext symbols (bit permutation)

Overview of DES - Data Encryption Standard
- Encrypts blocks of size 64 bits
- Key size 56 bits, 8 bit parity
- Symmetric
- 16 rounds to perform identical operation
- Structure is a Feistel network
- Initial permutation from LUT - diffusion
- f-Function
	- Expand 32 bit to 48 bits - increase diffusion
	- XOR with round key
	- S-box substitution
	- Permutation - for diffusion (via LUTs)
Two Major criticisms - Key space too small, S-box design criteria

---

DES Decyption
- Can be done using same structure, just need to modify key schedule

Triple DES (3DES)
- To extend effective key length to 112
- Useful for legacy systems

AES Overview
- 128 bit block symmetric block cipher
- Key sizes of 128, 192, or 256 bits
- Byte Substitution Layer
	- Identical, nonlinear, bijective
- ShiftRows Sublayer
	- Permutates rows for diffusion
- MixColumn Sublayer
	- Linear transformation which mixes each column of state matrix
- Key Addition Layer
	- Subkeys derived recursively from original key
	- Each round is 1 subkey, plus 1 subkey at beginning of AES
	- Key whitening $subkeys = rounds + 1$
- Efficient in computation in software
- Security
	- Brute force and analytical attacks not really possible
	- Side-channel attack - several published, requires additional information 