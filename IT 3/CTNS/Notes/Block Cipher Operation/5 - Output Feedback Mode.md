### **Definition**
**OFB (Output Feedback) Mode** is a block cipher mode of operation that turns a block cipher into a synchronous stream cipher. Instead of feeding the ciphertext back into the encryption process (like CFB), OFB feeds the output of the encryption function back into itself to generate a keystream, which is then XORed with plaintext blocks.

### **Example**
Let’s assume:
- Block size (b) = 128 bits
- Encryption algorithm: AES
- Initialization vector (IV/Nonce): `IV`
- Key: `K`

**Encryption process:**
```
O1 = E(K, IV) 
C1 = P1 ⊕ O1  

O2 = E(K, O1) 
C2 = P2 ⊕ O2  

O3 = E(K, O2) 
C3 = P3 ⊕ O3 

...
```
**Decryption process:**
```
P1 = C1 ⊕ O1 
P2 = C2 ⊕ O2 
P3 = C3 ⊕ O3 
...
```

### **Diagram**

![[Pasted image 20250515000811.png]]

### **Explanation**
- OFB generates a stream of pseudo-random bits (keystream) independent of the plaintext.
- These keystream blocks are XORed with the plaintext to produce ciphertext.
- The keystream is produced by repeatedly encrypting the previous output (starting from IV).
- Since the keystream does not depend on the ciphertext, **errors in transmission do not propagate**.

### **Formulas**
**Encryption:**
```
I1 = Nonce (IV) Ij = Oj-1                for j = 2 to N Oj = E(K, Ij)            for j = 1 to N Cj = Pj ⊕ Oj             for j = 1 to N-1 C*_N = P*_N ⊕ MSB_u(O_N)  (for partial last block)
```
**Decryption:**
```
I1 = Nonce (IV) Ij = Oj-1                for j = 2 to N Oj = E(K, Ij)            for j = 1 to N Pj = Cj ⊕ Oj             for j = 1 to N-1 P*_N = C*_N ⊕ MSB_u(O_N)  (for partial last block)
```

### ✅ **Advantages**
- **Error Containment**: A bit error in ciphertext only affects corresponding bit in plaintext (no propagation).
- **Preprocessing**: Keystream can be precomputed since it's independent of plaintext (useful for speed).
- **Stream cipher compatibility**: Makes block ciphers behave like stream ciphers.
- **No padding needed** for non-block-sized data (like real-time streams).
# ❌ **Disadvantages**
- **IV (Nonce) reuse is dangerous**: Reusing the same IV with the same key results in repeated keystream, which can be exploited.
- **No parallel encryption**: Each block depends on the previous output.
- **Message modification risk**: An attacker can flip bits in ciphertext to flip specific bits in plaintext (no diffusion).

### 🎯 **Works Best For**
- **Real-time communication systems** like secure voice or video streams.
- Applications where **error propagation must be avoided** (e.g., noisy channels).
- When **precomputing keystream** is useful (e.g., low-latency systems).

### 🚫 **Does Not Work When**
- The same IV is reused across messages — leads to **keystream reuse**, a critical vulnerability.
- Strong resistance to tampering is required — since **bit-flipping attacks are possible**.
- **Parallel processing of encryption** is needed — OFB is inherently sequential.