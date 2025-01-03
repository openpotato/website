---
title: Public-key Cryptography
date: 2025-01-03
authors: [fstueber, chatgtp]
slug: public-key-cryptography
description: >
  A short Introduction to Public-Key Cryptography
categories:
  - Infosec
---

# Public-Key Cryptography

Imagine you want to share a secret message with a friend without anyone else being able to read it. The problem is, you are on opposite sides of the world, and you don’t trust the postman. This is where public-key cryptography steps in—a method that allows secrets to be shared securely, even if the whole world is watching.

<!-- more -->

## A Look Back in Time

In the past, **symmetric encryption** was commonly used, where a single key was shared. For example, you would put your message in a box and lock it. Your friend would need the same key to unlock it. However, the problem was: how do you share the key securely? If someone intercepts the key, the message is no longer secure.

In the 1970s, a group of mathematicians—*Whitfield Diffie, Martin Hellman*, and later *Rivest, Shamir, and Adleman (RSA)*—revolutionised cryptography. They introduced the concept of using *two* keys: one public and one private. This innovation made secure communication possible, even if the key exchange happens publicly.

## How Does It Work?

Public-key cryptography relies on two keys:

+ **The public key**: Shared with everyone, like a mailbox outside your house where people can drop letters.
+ **The private key**: Kept secret, like the key that unlocks the mailbox.

Here’s how Alice and Bob can communicate securely:

1. Bob generates a key pair—a public and a private key—and shares the public key with Alice.
2. Alice encrypts her message to Bob using his public key.
3. Alice sends the encrypted message to Bob.
4. Bob decrypts the message using his private key and reads it.

[![Infographic - Public-Key Cryptography][1]][1]

## The Mathematical Foundations

At the heart of public-key cryptography are **one-way functions**—mathematical operations that are easy to compute in one direction but extremely difficult to reverse. For example, breaking a vase is simple, but piecing it back together is nearly impossible.

Public-key cryptography uses these one-way functions to:

+ Encrypt data with the public key.
+ Decrypt data with the private key by solving the “hard part” of the math.

### RSA Encryption

The most well-known public-key cryptography algorithm, **RSA**, is based on **prime factorisation** and **modular arithmetic**. Prime factorisation makes it easy to multiply two large primes but extremely difficult to reverse the process. Modular arithmetic ensures computations are not easily undone.

**How RSA Works**:

1. Choose two large prime numbers \( p \) and \( q \), and calculate \( n = p \times q \).
2. Compute \( \phi(n) = (p - 1)(q - 1) \), used for generating the private key.
3. Select \( e \), a number coprime with \( \phi(n) \), to create the public key.
4. Calculate \( d \), the private key, such that:
   $$
   (e \cdot d) \mod \phi(n) = 1
   $$

To encrypt a message \( M \):
$$
C = M^e \mod n
$$

To decrypt the message:
$$
M = C^d \mod n
$$

**Example** (with small numbers):

+ Choose \( p = 7 \), \( q = 11 \). Then \( n = 77 \) and \( \phi(n) = 60 \).
+ Choose \( e = 17 \) (coprime to 60). Calculate \( d = 53 \).
+ Public key: \( (77, 17) \), Private key: \( 53 \).

Encrypt with \( M = 10 \):  
$$
C = 10^{17} \mod 77 = 17
$$

Decrypt with \( C = 17 \):  
$$
M = 17^{53} \mod 77 = 10
$$

If you want to experiment a bit with RSA, you can try it out using this [interactive playground](https://www.ntietz.com/demos/bleichenbacher/).


### Elliptic Curve Cryptography (ECC)

While RSA is powerful, **elliptic curve cryptography (ECC)** offers an efficient alternative. Instead of relying on prime factorisation, ECC uses the properties of points on a curve to achieve the same security with smaller keys and less computational effort.

## Applications of Public-Key Cryptography

### Transport Layer Security (TLS)

TLS ensures secure communication between web browsers and servers. Public-key cryptography is used to:

+ Safely exchange a **symmetric key**, which is then used for encrypting the session.
+ Verify the server’s identity using its digital certificate and public key.

### Digital Signatures

Digital signatures are like handwritten signatures but far more secure. They guarantee:

+ **Authenticity**: The message truly comes from the sender.
+ **Integrity**: The message hasn’t been tampered with.
+ **Non-repudiation**: The sender cannot deny having sent the message.

How it works:

+ The sender signs the message or document using their private key.
+ The recipient verifies the signature using the sender’s public key.

Examples:

+ Signing contracts or PDFs.
+ Verifying the integrity of software updates.

### Encrypting and Signing Emails

Email encryption ensures:

+ **Confidentiality**: Only the intended recipient can read the email.
+ **Authenticity**: The email truly originates from the claimed sender.

How it works:

+ **Encryption**: The sender encrypts the message using the recipient’s public key, and the recipient decrypts it with their private key.
+ **Signing**: The sender signs the email with their private key, and the recipient verifies the signature with the sender’s public key.

Examples:

+ PGP (Pretty Good Privacy).
+ S/MIME (Secure/Multipurpose Internet Mail Extensions).

### Authenticating SSH Connections

SSH (Secure Shell) is a protocol for secure access to remote servers. Public-key cryptography ensures:

+ Only the owner of the private key can access the server.
+ No passwords are transmitted over the network.

How it works:

+ The user generates a key pair (public and private).
+ The public key is stored on the server.
+ During login, the client proves possession of the private key without transmitting it.

### Blockchain Platforms

Blockchain platforms like **Bitcoin** and **Ethereum** rely heavily on public-key cryptography to ensure security and trust.

+ **Wallets and Identity**: Users have a key pair. The public key serves as the wallet address, while the private key is used to sign transactions.
+ **Digital Signatures**: Transactions are signed with private keys, ensuring authenticity and preventing tampering.
+ **Verification**: Other network nodes verify the transaction using the public key.

Examples:

+ **Bitcoin**: Transactions are signed with private keys and verified by the blockchain.
+ **Ethereum**: Smart contracts and transactions are secured using public-key cryptography.

## Epilogue: Alice and Bob

In the world of cryptography, **Alice** and **Bob** are fictional characters used to explain secure communication.

Typically:

+ **Alice** is the sender (**A**). She wants to send a message to Bob that remains private.  
+ **Bob** is the recipient (**B**). He should receive the message, regardless of who else might be listening or trying to intercept it.  

Alice and Bob were first mentioned in the groundbreaking paper [A Method for Obtaining Digital Signatures and Public-Key Cryptosystems](https://people.csail.mit.edu/rivest/Rsapaper.pdf) by Ronald Rivest, Adi Shamir, and Leonard Adleman (the inventors of RSA). Since then, they’ve become iconic figures in cryptography.

[1]: /en/assets/img/public-key-encryption.png "Infographic - Public-Key Cryptography"
