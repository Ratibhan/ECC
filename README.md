The Elliptic Curve Cryptography (ECC) is modern family of public-key cryptosystems, which is based on the algebraic structures of the elliptic curves over finite fields and on the difficulty of the Elliptic Curve Discrete Logarithm Problem (ECDLP).

ECC implements all major capabilities of the asymmetric cryptosystems: encryption, signatures and key exchange.
The ECC cryptography is considered a natural modern successor of the RSA cryptosystem, because ECC uses smaller keys and signatures than RSA for the same level of security and provides very fast key generation, fast key agreement and fast signatures.

ECC Keys
The private keys in the ECC are integers (in the range of the curve's field size, typically 256-bit integers). Example of 256-bit ECC private key (hex encoded, 32 bytes, 64 hex digits) is: 0x51897b64e85c3f714bba707e867914295a1377a7463a9dae8ea6a8b914246319.
The key generation in the ECC cryptography is as simple as securely generating a random integer in certain range, so it is extremely fast. Any number within the range is valid ECC private key.
The public keys in the ECC are EC points - pairs of integer coordinates {x, y}, laying on the curve. Due to their special properties, EC points can be compressed to just one coordinate + 1 bit (odd or even). Thus the compressed public key, corresponding to a 256-bit ECC private key, is a 257-bit integer. Example of ECC public key (corresponding to the above private key, encoded in the Ethereum format, as hex with prefix 02 or 03) is: 0x02f54ba86dc1ccb5bed0224d23f01ed87e4a443c47fc690d7797a13d41d2340e1a. In this format the public key actually takes 33 bytes (66 hex digits), which can be optimized to exactly 257 bits.

Curves and Key Length
ECC crypto algorithms can use different underlying elliptic curves. Different curves provide different level of security (cryptographic strength), different performance (speed) and different key length, and also may involve different algorithms.
ECC curves, adopted in the popular cryptographic libraries and security standards, have name (named curves, e.g. secp256k1 or Curve25519), field size (which defines the key length, e.g. 256-bit), security strength (usually the field size / 2 or less), performance (operations/sec) and many other parameters.
ECC keys have length, which directly depends on the underlying curve. In most applications (like OpenSSL, OpenSSH and Bitcoin) the default key length for the ECC private keys is 256 bits, but depending on the curve many different ECC key sizes are possible: 192-bit (curve secp192r1), 233-bit (curve sect233k1), 224-bit (curve secp224k1), 256-bit (curves secp256k1 and Curve25519), 283-bit (curve sect283k1), 384-bit (curves p384 and secp384r1), 409-bit (curve sect409r1), 414-bit (curve Curve41417), 448-bit (curve Curve448-Goldilocks), 511-bit (curve M-511), 521-bit (curve P-521), 571-bit (curve sect571k1) and many others.


ECC Algorithms
Elliptic-curve cryptography (ECC) provides several groups of algorithms, based on the math of the elliptic curves over finite fields:
ECC digital signature algorithms like ECDSA (for classical curves) and EdDSA (for twisted Edwards curves).ECC encryption algorithms and hybrid encryption schemes like the ECIES integrated encryption scheme and EEECC (EC-based ElGamal).ECC key agreement algorithms like ECDH, X25519 and FHMQV.
All these algorithms use a curve behind (like secp256k1, curve25519 or p521) for the calculations and rely of the difficulty of the ECDLP (elliptic curve discrete logarithm problem). All these algorithms use public / private key pairs, where the private key is an integer and the public key is a point on the elliptic curve (EC point). Let's get into details about the elliptic curves over finite fields.


The ECC cryptography is considered a natural modern successor of the RSA cryptosystem, because ECC uses smaller keys and signatures than RSA for the same level of security and provides very fast key generation, fast key agreement and fast signatures.
