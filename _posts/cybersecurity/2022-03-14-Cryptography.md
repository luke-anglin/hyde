---
layout: post
title: Cryptography
categories: cybersecurity
link: https://collab.its.virginia.edu/access/content/group/e7990662-1551-41b1-99bd-0539849f7d83/CS3710_Week9.pdf
---

# Language and Cryptanalysis

- **Frequency Analysis** - most common English letter is E
- Create tables of double (digram) and triple (trigram)

# Cryptography Terms

- Encrypted information - ciphertext
- Key - a string of numbers or characters used to encrypt or decrypt information
- **Key size very important!** - 128 bit keys is enough for today

## Cipher Categories

- **Private, symmetric** - same key to encrypt/decrypt
- **Public, assymetric** - different keys to encrypt/decrypt

### Symmetric

- Both parties use the same key (private)
- Key needs to be exchanged out-of-band
- Fast, good for securing a lot of data
- Scalability issues

![Sym Crypt](https://i.imgur.com/GNdg4ky.png)

#### Block cipher

- Processes the plaintext input in fixed-size blocks and produces blocks of ciphertext for each block
- Most common for symmetric encryption

#### DES

- Data Encryption Standard
- 56-bit key, 64-bit block, 16 iterations of substitutions and transformation
- Because of improving computers, 3DES is now the standard ~ 3 unique keys

#### AES

- New best symmetric - based no Rijndael
- 128, 192, and 256-bit key
- 128-bit blocks

#### Symmetric Stream Encryption Algorithm - RC4

- Designed by Ron Rivest for RSA security
- Used in SSL/TLS, WEP and WPA

### Asymmetric

- Two different keys (public-private key pair)
- Can do everything in-band

#### Asymmetric Public Key

![Asym Pub Key](https://i.imgur.com/ctFCwv9.png)

#### Asymmetric Public Key Algorithms

![Asymmetric process](https://i.imgur.com/O5uOyWf.png)

#### Diffie-Hellman Key Exchange

![DHKE](https://i.imgur.com/qMeBa8G.png)

#### RSA

![RSA](https://i.imgur.com/ykUVMzv.png)

![RSA Example](https://i.imgur.com/1j4xraC.png)

- Euler's phi function is the $\phi$, also called the **coprime** of $n$
- $e$ is the GCD of $\phi(n)$
- $d$ is kept secret because it is used in generating the private key
- Ciphertext encryption: $C = M^e \text{ mod } n$
- Decryption: $M = C^d \text{ mod } n$

## Cryptography's Role in Information Security

Remember **CIAN** like the color

- Confidentiality - secret from unauthorized users
- Integrity - ensures that no one, even the sender, changes data after transmission - go ahead and hash too, so that if someone changes something you'll know
- Authentication
- Nonrepudiation - prevents a party from denying a previous statement or action

## Transposition Ciphers

- Encrypt in a table and permute columns based on keyword/key set

![TC](https://i.ytimg.com/vi/sHsnH1u03e4/maxresdefault.jpg)

## Substitution Ciphers

### Keyword mixed alphabet cipher

Remove a few letters from a word, throw in the rest of the letters, substitution cipher after that

![](https://i.imgur.com/wPj23iJ.png)

### Vigenére

- Encrypts every letter with its own substition scheme
- Matrix table that shifts alphabet each row
- Uses a keyword that matches the length of the message
- Breaks frequency analysis

![Vigenére](https://i.imgur.com/Pq3KCii.png)

### Simple Substitution Cipher

Allows any letter to uniquely map to any other letter (vigenére included)

### Rot13

Modification of Caesar cipher, shifts by 13 rather than 3

# Hash functions and signatures

- **Checksum** - message metadata to ensure the integrity of the **data values** (that it hasn't changed since it was sent), not as secure as hashes (replay attacks will beat this)
- **Hash** - Similar to a checksum, but prevents **forged messages**, which wouldn't create a same hash (MD5, 128-bit hash)
- **Digital Signatures**
  - Binds some identity to some piece of data/message
  - Ensures data integrity of the message and author
  - Requires ASYM key cryptography

## Digital Signature Process

![Digital Signature Process](https://i.imgur.com/GVkrnHU.png)

# SSL/TLS

- Secure Sockets Layer / Transport Layer Security - we don't use SSL anymore, but we still call it SSL sometimes
- HTTPS and FTPS use it
- Asymmetric
- Current browsers moving from TLS 1.2 to TLS 1.3
- Encryption while data is in transit, NOT while at rest
- Some VPNS are built on TLS

## TLS Handshake

1. Agree on suite (Diffie-hellman? RSA? AES? SHA for hashing?)
2. Server authenticates with a digital certificate (Amazon is _really_ Amazon, the certificate proves it)
3. Key/color exchange, mixing them, getting that final symmetric key (Diffie-Hellman or some other cipher suite)
4. Use that 'brown' key and use symmetric encryption

# Cryptanalysis

Cryptanalysis objectives:

- Figure out the plaintext from a target message
- Figure out the key used to encrypt some message
- Figure out the algorithm some cipher uses
- Figure out the math underlying some cryptographic process

Forms of cryptographic attack:

- Ciphertext-only attack (COA)
- Known-plaintext attack (KPA)
- Chosen-plaintext attack
- Chosen-ciphertext attack

Computationally secure encryption schemes rely on **cost and time**.
