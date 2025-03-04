Source: [GPT](https://chatgpt.com/c/67c585b6-e260-8009-bae0-30b0ea684d33)

---

The **Rivest-Shamir-Adleman (RSA) algorithm** is a **public-key cryptosystem** used for **secure data transmission**. It was invented in **1977** by **Ron Rivest, Adi Shamir, and Leonard Adleman**. Unlike symmetric encryption algorithms (such as DES and AES), RSA is an **asymmetric encryption algorithm**, meaning it uses **two different keys**:

- **Public Key** (used for encryption)
- **Private Key** (used for decryption)

RSA is widely used in **digital signatures, secure email communication, online banking, and SSL/TLS encryption**.

---

### **Step 1: Key Generation**

To generate the public and private keys, follow these steps:

1. **Select two large prime numbers**:
    
    - Choose two distinct large prime numbers **p** and **q**.
    - Example: p=61p = 61, q=53q = 53.
2. **Compute n (modulus)**:
    
    - Multiply the two prime numbers: `n=p×q`
    - Example: `n=61×53=3233`
3. **Compute Euler’s Totient Function (φ(n))**:
    
    - Formula: `φ(n)=(p−1)×(q−1)`
    - Example: `φ(3233)=(61−1)×(53−1)=3120`
4. **Choose a public exponent (e)**:
    
    - Select an integer **e** such that: 1<e<φ(n)
    - **e should be coprime to φ(n)** (i.e., gcd(e, φ(n)) = 1).
    - Common choice: **e = 65537** (often used in practice).
5. **Compute the private exponent (d)**:
    
	- Compute **d** such that: `d×e≡1 (mod φ(n))`
    - Find **d** using the **Extended Euclidean Algorithm**.
    - Example: `d = 2753 (since (2753×17)mod  3120=1`

### **Step 2: Encryption**

To encrypt a message **M**, use the public key (e, n):

- `C = M^e mod n`
- Example: If **M = 65**, then `C=65^(17)mod  3233=2790`

### **Step 3: Decryption**

To decrypt the ciphertext **C**, use the private key (d, n):

- `M = C^d mod n`
- Example: `M=2790^(2753)mod  3233=65`

---

## **Advantages of RSA**

✅ **High Security**: RSA is secure due to the difficulty of **factoring large prime numbers**.

✅ **Public Key Encryption**: No need to share a secret key before communication.

✅ **Digital Signatures**: RSA allows **authentication** through digital signatures.

✅ **Scalability**: Can be used for secure communications across networks, including SSL/TLS.

---

## **Disadvantages of RSA**

❌ **Slow for Large Data**: RSA is computationally expensive, making it slower than symmetric encryption (AES).

❌ **Key Length**: To remain secure, RSA requires large key sizes (2048-bit or more), increasing computational overhead.

❌ **Vulnerable to Quantum Computing**: **Shor’s Algorithm** (for quantum computers) could break RSA encryption in the future.

---

## **Conclusion**

RSA is one of the most widely used **public-key cryptographic algorithms**. It provides **secure encryption and authentication**, making it essential for **internet security**. However, due to its computational intensity, it is often used in combination with **symmetric encryption algorithms** for efficiency (e.g., RSA for key exchange and AES for data encryption). 🚀

---
[[DES Algorithm]] :luc_arrow_left:
[[Digital Signature]] :luc_arrow_right: