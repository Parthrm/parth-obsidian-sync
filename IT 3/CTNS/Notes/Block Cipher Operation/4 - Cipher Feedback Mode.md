
### **Definition**
Cipher Feedback (CFB) mode is an encryption technique that transforms a block cipher into a self-synchronizing stream cipher. It allows data to be encrypted in smaller units (e.g., bytes or bits) and is ideal for encrypting real-time streams.

### **Example**
Assume:
- Block cipher = AES (block size b=128)
- Segment size s=8 (1 byte)
- Initialization Vector (IV) = 128-bit random value
- Plaintext: "HELLO" (each character = 8 bits)
**Steps**:
1. Encrypt IV: EK(IV)E_K(IV)EK​(IV)
2. Take MSB 8 bits of output and XOR with 'H' → $C_1$​
3. Shift IV left by 8 bits, append $C_1$​, and repeat

### **Diagram**

![[Pasted image 20250514225910.png]]

### **Explanation**
- CFB mode operates by dividing plaintext into segments of size s bits (often 8).
- The encryption function is applied to a shift register starting with an IV.
- The leftmost s bits of the output are XORed with plaintext to generate ciphertext.
- The shift register updates by shifting left s bits and appending the ciphertext segment.
- Only the **encryption algorithm** is used for both encryption and decryption.

### **Formulas**
**Encryption:**
- $I_1=IV$
- $I_j=LSB_{b−s}(I_j−1)∥Cj−1$
- $Oj=EK(Ij)$
- $C_j=P_j⊕MSB_s(O_j)$
**Decryption:**
- $I_1 = IV$
- $I_j = \text{LSB}_{b-s}(I_{j-1}) \| C_{j-1}$
- $O_j = E_K(I_j$
- $P_j = C_j \oplus \text{MSB}_s(O_j)$

Where:
- $P_j$​: Plaintext segment
- $C_j$​: Ciphertext segment
- $E_K$​: Encryption with key KKK
- $MSB_s$​: Most significant sss bits
- $LSB_{b-s}$​: Least significant b−sb-sb−s bits

### **Advantages**
- Converts block cipher into stream cipher.
- Ideal for encrypting small or real-time data streams (e.g., keystrokes).
- No padding required, unlike ECB or CBC.
- Can start encrypting without knowing the full message.

### **Disadvantages**
- Encryption is **not parallelizable** due to chaining.
- Transmission errors propagate (1-bit error in ciphertext affects two plaintext segments).
- Depends on a well-protected and unpredictable IV.

### **Works Best For**
- Real-time communication (e.g., chat, voice).
- Streaming data (e.g., over TCP/UDP).
- Environments where data arrives in small pieces.

### **Does Not Work Well When**
- High throughput with parallel processing is required (due to lack of parallelism in encryption).
- Error-sensitive data needs encryption (since errors affect multiple segments).
- Predictable or reused IVs are used (this weakens security).
