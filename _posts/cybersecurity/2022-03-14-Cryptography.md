---
layout: post
title: Cryptography
categories: cybersecurity
---

# Language and Cryptanalysis

- **Frequency Analysis** - most common English letter is E
- Create tables of double (digram) and triple (trigram)

# Cryptography Terms

- Encrypted information - ciphertext
- Key - a string of numbers or characters used to encrypt or decrypt information

## Cipher Categories

- **Private, symmetric** - same key to encrypt/decrypt
- **Public, assymetric** - different keys to encrypt/decrypt

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
