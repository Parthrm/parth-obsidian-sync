### 🔹 **Definition:**
**Cipher Block Chaining (CBC)** is a block cipher mode of operation where each plaintext block is **XORed with the previous ciphertext block** before encryption, ensuring that **identical plaintext blocks result in different ciphertexts** if the preceding blocks differ.

### 🔹 **Example:**
Assume a message `"HELLOWORLD"` is split into two blocks:
- P1 = "HELLO"
- P2 = "WORLD"
Assume:
- IV = `00000` (Initialization Vector)
- Key = `K`
- Encryption function = `E(K, X)`, XOR denoted by ⊕
Encryption:
- C1 = E(K, P1 ⊕ IV)
- C2 = E(K, P2 ⊕ C1)
So even if P1 = P2, **C1 ≠ C2**, thanks to chaining via C1.

### 🔹 **Diagram:**

![[Pasted image 20250514194046.png]]
### 🔹 **Explanation:**
CBC overcomes ECB’s flaw where identical plaintext blocks yield identical ciphertexts. It introduces **randomness** through:
1. **Initialization Vector (IV):** XORed with the first block of plaintext.
2. **Chaining:** Each ciphertext block influences the encryption of the next block.
**Decryption works as:**
- P1 = D(K, C1) ⊕ IV
- Pj = D(K, Cj) ⊕ Cj−1 for j > 1
Thus, both sender and receiver must share the IV securely.

### 🔹 **Formulas:**
- **Encryption:**
    - C1=EK(P1⊕IV)
    - Cj=EK(Pj⊕Cj−1)
	for j=2,…,N
- **Decryption:**
    - P1=DK(C1)⊕IV
    - Pj=DK(Cj)⊕Cj−1​ 
    for j=2,…,N
Where:
- EKE_KEK​: Encryption with key KKK
- DKD_KDK​: Decryption with key KKK
- ⊕: Bitwise XOR

### 🔹 **Advantages:**
- 🔹 Conceals plaintext patterns (unlike ECB).
- 🔹 Provides semantic security under chosen-plaintext attacks.
- 🔹 Allows use for both **confidentiality** and **authentication** (with MAC).

### 🔹 **Disadvantages:**
- 🔻 **Cannot parallelize encryption** (due to chaining).
- 🔻 **Error propagation:** one bit error in a ciphertext block affects two plaintext blocks.
- 🔻 Requires **secure handling of IV**:
    - Must be unique and unpredictable.
    - Must be known to both sender and receiver.

### 🔹 **Works Best For:**
- ✅ Encrypting **long messages** or files where security against pattern leakage is important.
- ✅ Secure transmission of structured or repeated plaintext blocks.

### 🔹 **Does Not Work When:**
- 🚫 The IV is reused or predictable.
- 🚫 High performance parallel encryption is needed.
- 🚫 The system cannot securely distribute or protect the IV.