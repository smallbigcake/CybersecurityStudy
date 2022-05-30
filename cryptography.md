

# Cryptography


## Elliptic-curve cryptography

Elliptic-curve cryptography (ECC) is an approach to public-key cryptography based on the algebraic structure of elliptic curves over finite fields. ECC allows smaller keys compared to non-EC cryptography (based on plain Galois fields) to provide equivalent security.  
https://en.wikipedia.org/wiki/Elliptic-curve_cryptography


### Curve25519

In cryptography, Curve25519 is an elliptic curve offering 128 bits of security (256 bits key size) and designed for use with the elliptic curve Diffie–Hellman (ECDH) key agreement scheme. It is one of the fastest ECC curves and is not covered by any known patents. The reference implementation is public domain software.  
The original Curve25519 paper defined it as a Diffie–Hellman (DH) function. Daniel J. Bernstein has since proposed that the name Curve25519 be used for the underlying curve, and the name X25519 for the DH function.  
https://en.wikipedia.org/wiki/Curve25519


### X25519

X25519 is a key agreement algorithm based on the Montgomery curve "curve25519" [[CURVE25519](http://cr.yp.to/ecdh.html)]. The use of X25519 for Elliptic Curve Diffie-Hellman key exchange (ECDH) is described in [[RFC7748](https://datatracker.ietf.org/doc/html/rfc7748)].


### EdDSA

In public-key cryptography, Edwards-curve Digital Signature Algorithm (EdDSA) is a digital signature scheme using a variant of Schnorr signature based on twisted Edwards curves.


### Ed25519

Ed25519 is the EdDSA signature scheme using SHA-512 (SHA-2) and Curve25519.


### Features of X25519 and Ed25519

- The private and public keys for both X25519 and Ed25519 are all represented by a 32-byte string.
- X25519 allows all 32-byte strings as public keys.
- There are masking requirements for X25519 private keys but this Toolkit will accept any 32-byte string as an X25519 private key. The masking will be applied before the key is used or saved.
- Ed25519 allows all 32-byte strings as private keys.
- Ed25519 signatures are always 64 bytes long, with the three most significant bits of the final byte always zero.
- The public keys for X25519 and Ed25519 are derived from the secret key in different ways and cannot be interchanged.


### Some differences from the NIST/SEC curves

- The NIST/SEC elliptic curves can be used for both ECDH key exchange and ECDSA signatures, but Ed25519 cannot be used for key exchange and X25519 cannot be used for signatures.
- For NIST/SEC curves, the difference between a private key and public key is obvious from its structure. This is not the case for safe curves where the private and public keys are the same length.
- When using the [ECC_ReadKeyByCurve](https://www.cryptosys.net/pki/manpki/pki_ECC_ReadKeyByCurve.html) function with safe curves, the user must explicitly specify whether the key is a private key or public key.
- The hexadecimal encoding of safe curve keys is different from that used for NIST/SEC keys. Safe curve keys are encoded using the little-endian convention, whereas NIST/SEC curves are encoded using the big-endian convention as per [[RFC5915](https://datatracker.ietf.org/doc/html/rfc5915)] using the I2OSP primitive defined in [[RFC3447](https://datatracker.ietf.org/doc/html/rfc3447)]. The encoding for safe curves used in this Toolkit is consistent with that used in the reference documents (other implementations may differ).
- When using the ECDSA signature algorithm with the NIST/SEC curves, you can pass the hash digest of the message to the signature function to create the signature as an alternative to passing the entire message. However, Ed25519 cannot create or verify a signature using the hash of the message. The full message must be passed to the sign or verify function. To sign or verify a file with Ed25519, you must read in all the data first and pass that directly to the [SIG_SignData](https://www.cryptosys.net/pki/manpki/pki_SIG_SignData.html) function.


https://www.cryptosys.net/pki/manpki/pki_eccsafecurves.html