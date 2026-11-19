# Cryptography simulators

Interactive pages that show how cryptographic algorithms work, from the outside in.

**Live site:** https://ksawerym.github.io/Cryptography-simulators/

## Ready

- **ChaCha20** (`chacha20/`): black box, inside, one round, one operation, and the comparison with RC4 (the two key
  tests of Lecture 2 over 10 000 or 100 000 keys; the fixed seed 2026 gives the numbers on the slides).

## In progress

- **Mathematics for cryptography** (`math/`): 9 chapters and 60 sections; two sections are done: the extended Euclidean
  algorithm (`math/extended-euclid/`) and fast modular exponentiation (`math/fast-exponentiation/`).
- **AES and its modes** (`aes/`): black box, inside, one round, the modes ECB, CTR, GCM and XTS, comparison.
- **RC4** (`rc4/`): black box, key scheduling (KSA), producing bytes (PRGA), the weaknesses (with WEP: the IV repeats, the FMS attack step by step).
- **RSA** (`rsa/`): black box (a story in 9 steps), making the keys, why decryption works, Eve tries to break it, why textbook RSA is not enough. The algorithms behind
  d and the power are in the mathematics section.
- **Diffie-Hellman and ElGamal** (`diffie-hellman/`): black box, the powers of g, Mallory in the middle, ElGamal, one power.
- **Elliptic curves** (`elliptic-curves/`): black box, adding points, from real numbers to modulo 17, the curve modulo 17, one addition.
- **Hash functions** (`hash/`): black box, the avalanche, padding and the chain of blocks, `update()` in pieces, one bit through the rounds, guessing a short hash.
- **Collisions and passwords** (`passwords/`): the birthday paradox, one MD5 collision gives many, four ways to store a password, a rainbow table, the cost of bcrypt.
- **Certificates and PKI** (`pki/`): black box (Mallory swaps a key, a CA signature stops her), inside a certificate (X.509 fields, DER
  bytes, fingerprint), chain of trust, validation checks, revocation (CRL, OCSP, stapling), certificates in TLS 1.3 and mTLS, pinning.

## Coming soon

- Classical ciphers and the one-time pad
- Randomness
- Authenticated encryption (AEAD)
- Message authentication codes (MAC)
- Passwords and key derivation
- Digital signatures
- TLS 1.3
- Secure messaging (Signal)
- Post-quantum cryptography (PQC)
- Side-channel attacks
- Secret sharing
- Zero-knowledge proofs and commitments
- Homomorphic encryption and secure computation

## License

Creative Commons Attribution 4.0 International (CC BY 4.0), see [LICENSE](LICENSE).
