# Hash Algorithms

Hash algorithms are cryptographic functions that take an input (or 'message') and return a fixed-size string of bytes. These algorithms are designed to be fast to compute and irreversible. Hash functions are widely used in various fields, including cryptography, data integrity verification, and data structures.

## Properties of Hash Algorithms

1. **Deterministic**: Given the same input, a hash algorithm will always produce the same output.
2. **Irreversible**: Given the output (hash value) of a hash function, it should be computationally infeasible to determine the original input data. This property ensures the security of various cryptographic applications by preventing attackers from recovering sensitive information from hashed representations.
3. **Fixed Output Size**: Regardless of the size of the input, the output hash has a fixed size.
4. **Efficient Computation**: Hash algorithms are designed to be computationally efficient.
5. **Pre-image Resistance**: It should be computationally infeasible to determine the input from its hash value.
6. **Collision Resistance**: It should be computationally infeasible to find two different inputs that produce the same hash value.
7. **Avalanche Effect**: A small change in the input should produce a significantly different hash value.

## Common Hash Algorithms

### MD5 (Message Digest Algorithm 5)
### SHA-1 (Secure Hash Algorithm 1)
### SHA-256 (Secure Hash Algorithm 256-bit)
### SHA-3 (Secure Hash Algorithm 3)
## Applications

- **Data Integrity**: Hash algorithms are used to ensure data integrity by generating hash values for data and comparing them to verify if the data has been tampered with.
- **Digital Signatures**: Hash functions are used in digital signatures to ensure the authenticity and integrity of digital documents.
- **Password Storage**: Hash algorithms are used to store passwords securely. Instead of storing plaintext passwords, systems store hashed passwords, making it difficult for attackers to reverse-engineer the original passwords.
