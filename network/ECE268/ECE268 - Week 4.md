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

