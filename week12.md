#  Explain the functionality and characteristics of a hashing function, and how they are used (SHA-2, MD5)

## Hash function:
A function that can be used to map data of arbitrary size to data of fixed size.

The values returned by a hash function are called hash values, hash codes, digests, or simply hashes.



## MD5: message digest 5
- Output hash is always 128 bits (fixed length).
- Like most hash functions, MD5 is neither encryption nor encoding.
- It can be cracked by brute-force attack and suffers from extensive vulnerabilities.
-  It can still be used as a checksum to verify data integrity, but only against unintentional corruption.
- widely used in the software world to provide some assurance that a transferred file has arrived intact.
-  For example, file servers often provide a pre-computed MD5 (known as md5sum) checksum for the files, so that a user can compare the checksum of the downloaded file to it.

[checksum]: https://upload.wikimedia.org/wikipedia/commons/thumb/c/c8/CPT-Hashing-File-Transmission.svg/281px-CPT-Hashing-File-Transmission.svg.png


https://en.wikipedia.org/wiki/MD5

https://www.gohacking.com/wp-content/uploads/2010/01/MD5-Hash-Function.jpg

https://www.gohacking.com/what-is-md5-hash/


## SHA-2
