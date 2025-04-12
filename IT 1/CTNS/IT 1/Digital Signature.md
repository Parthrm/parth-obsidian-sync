#it1 
Source: [GPT](https://chatgpt.com/c/67c585b6-e260-8009-bae0-30b0ea684d33)

---
**Important Terms and Definitions in Digital Signatures (Cryptography)**

Digital signatures are cryptographic techniques used to **ensure authenticity, integrity, and non-repudiation** of electronic messages or documents. Below are the key terms you need to know:

1. Digital Signature
	A cryptographic mechanism that allows a sender to **sign** a message or document to prove its authenticity and integrity. It is based on **public-key cryptography**.
2. Public Key Cryptography (Asymmetric Cryptography)
	A cryptographic system that uses **two keys**:
	- **Public Key** – Shared with everyone for verification.
	- **Private Key** – Kept secret and used for signing.
3. Hash Function
	A mathematical function that converts an input (message) into a **fixed-length hash value** (digest). The output is unique to the input, ensuring integrity.
	Examples: **SHA-256, SHA-512, MD5**.
4. Message Digest
	The output of a **hash function** that uniquely represents the original message. Even a small change in the message results in a completely different digest.
5. Signing Process
	The process of creating a **digital signature** by hashing a message and encrypting the hash with the **private key** of the sender.
	**Steps:**
	1. Hash the message using a **hash function**.
	2. Encrypt the hash using the **private key** to create a **digital signature**.
	3. Attach the signature to the message and send it.
6. Verification Process
	The process of confirming the authenticity of a digital signature using the sender’s **public key**.
	**Steps:**
	1. Decrypt the signature using the sender’s **public key** to get the hash.
	2. Hash the received message independently.
	3. Compare both hash values. If they match, the signature is **valid**.
7. Certificate Authority (CA)
	A trusted third party that issues **digital certificates** to verify the authenticity of an entity’s **public key**.
8. Digital Certificate
	An electronic document issued by a **Certificate Authority (CA)** that links a person’s **identity** with their **public key**.
	**Contains:**
	- Public key
	- Owner’s identity
	- CA’s signature
	- Expiry date
9. Private Key
	A **secret key** used by the sender to sign a digital document. It must be kept confidential.
10. Public Key
	A key that is **shared publicly** and used for **verifying** the digital signature.
11. Non-Repudiation
	A property of digital signatures ensuring that the **sender cannot deny** sending the message, as it is linked to their private key.
12. Key Pair
	A combination of a **public key** and a **private key** used in asymmetric encryption systems like RSA and ECDSA.
13. RSA Digital Signature Algorithm
	A widely used **asymmetric cryptographic algorithm** for creating digital signatures. Uses **modular exponentiation** and **factorization of large primes**.
14. ECDSA (Elliptic Curve Digital Signature Algorithm)
	A modern, efficient alternative to RSA that provides the same security with smaller key sizes, making it **faster and more scalable**.
15. Timestamping
	A mechanism that provides **proof of time** when a digital signature was created, ensuring documents remain valid over time.
16. Digital Signature Standard (DSS)
	A standard set by **NIST** defining algorithms like **DSA, RSA, and ECDSA** for generating digital signatures.
17. Man-in-the-Middle Attack (MITM)
	A security threat where an attacker intercepts and modifies messages. Digital signatures help prevent such attacks by ensuring message authenticity.
18. Hash Collision
	When two different inputs produce the **same hash value**. A secure hash function like **SHA-256** reduces collision risks.
19. Revocation
	The process of **invalidating a digital certificate** before its expiry if it is compromised or no longer trustworthy. Managed via a **Certificate Revocation List (CRL)**.
20. Blockchain and Digital Signatures
	Digital signatures are widely used in **blockchain** technology to verify transactions in cryptocurrencies like **Bitcoin** and **Ethereum**.

**Conclusion**
Digital signatures are an essential cryptographic tool that provides **authentication, integrity, and non-repudiation** for electronic communication.

---
[[RSA algorithm]] :luc_arrow_left:
[[Random Generator]] :luc_arrow_right: