#  Explain the functionality and characteristics of a hashing function, and how they are used (SHA-2, MD5)

## Hash function:
A function that can be used to map data of arbitrary size to data of fixed size.

The values returned by a hash function are called hash values, hash codes, digests, or simply hashes.

The exact requirements are dependent on the application, for example a hash function well suited to indexing data will probably be a poor choice for a cryptographic hash function.

- for given input, must always return the same hash output (deterministic)
- should not return the same output for different inputs - avoid collision (uniformity)



## MD5: message digest 5 1995
- Input (message) digital data, Output (digest) is always 128 bits (fixed length).
- Like most hash functions, MD5 is neither encryption nor encoding.
- It can be cracked by brute-force attack and suffers from extensive vulnerabilities.
  - It can still be used as a checksum to verify data integrity, but only against unintentional corruption.
- widely used in the software world to provide some assurance that a transferred file has arrived intact.
  - For example, file servers often provide a pre-computed MD5 (known as md5sum) checksum for the files, so that a user can compare the checksum of the downloaded file to it.

![checksum](https://upload.wikimedia.org/wikipedia/commons/thumb/c/c8/CPT-Hashing-File-Transmission.svg/281px-CPT-Hashing-File-Transmission.svg.png)



## SHA-2: secure hash algorithm 2 2001
- In 2017, an example of a SHA-1 (1995) collision was published.
- cryptographic hash functions designed by the NSA and patented and released under a royalty-free license
  - set of algorithms consisting of SHA-224, SHA-256, SHA-384 and SHA-512
- non invertible, one way function
- implemented in some widely used security applications and protocols, including TLS and SSL, PGP, SSH, S/MIME, and IPsec.
  - websites use TLS to secure all communications between their servers and web browsers
  






references:
- https://en.wikipedia.org/wiki/MD5
- https://www.gohacking.com/wp-content/uploads/2010/01/MD5-Hash-Function.jpg
- https://www.gohacking.com/what-is-md5-hash/
- https://en.wikipedia.org/wiki/SHA-2
