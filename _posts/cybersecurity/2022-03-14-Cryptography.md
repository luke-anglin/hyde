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

* Designed by Ron Rivest for RSA security 
* Used in SSL/TLS, WEP and WPA 

### Asymmetric

- Two different keys (public-private key pair)
- Can do everything in-band

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
