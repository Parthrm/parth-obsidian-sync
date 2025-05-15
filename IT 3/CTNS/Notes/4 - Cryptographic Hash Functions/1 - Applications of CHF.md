### Message Authentication – Technical Summary
#### ✅ **Definition**
**Message Authentication** ensures that the data received is **exactly** what was sent—unaltered, untampered, and from a legitimate sender. When **cryptographic hash functions** are used for this purpose, the resulting output is called a **message digest**.
#### ⚙️ **Mechanism of Hash-Based Message Authentication**
1. **Sender Side**:
    - Compute the hash (digest) of the message: `H(M)`
	    
    - Send both message `M` and its hash value `H(M)` to the receiver.
        
2. **Receiver Side**:
    
    - Compute the hash on the received message `M'` as `H(M')`
        
    - Compare it with the received hash `H(M)`.
        
    - If `H(M) ≠ H(M')`, the message has been tampered with.
        
#### ❗ **Vulnerability**
If the hash is sent **unencrypted**, an attacker (e.g., Darth) could:
- Intercept the message.
    
- Modify it to `M'`.
    
- Recalculate `H(M')`.
    
- Replace the original hash.
    
**Result**: Receiver (Bob) accepts `M'` as authentic.
#### 🔐 **Secure Hash Usage Techniques (Figure 11.3)**
**(a) Encrypt Message + Hash (using symmetric key)**
- `E(K, M || H(M))`
    
- Ensures both **confidentiality** and **authentication**.
    
**(b) Encrypt Only Hash**
- `E(K, H(M))`, with message sent in plaintext.
    
- Lower overhead, still authenticates the message.
    
**(c) Hash with Shared Secret**
- `H(M || S)` where `S` is a secret shared between sender and receiver.
    
- No encryption needed, but only works if `S` is known and secret.
    
**(d) Combine (c) with Encryption**
- Encrypt entire `(M || H(M || S))` for both **confidentiality** and **authentication**.
    
#### ⚠️ **Why Avoid Full Encryption for Authentication**
- Encryption is **computationally intensive** for small messages.
    
- **Hardware cost** is non-trivial in large networks.
    
- Some encryption algorithms (e.g., DES) are **patent protected**.
    
- Encryption hardware/software is optimized for large blocks, not small ones.
    
### 🧾 **MAC (Message Authentication Code) – Preferred Approach**
- **MAC = H(K, M)** → Hash with a secret key.
    
- Ensures **integrity** and **authenticity** without encrypting the full message.
    
- Sender and receiver share a **secret key K**.
    
- Attacker cannot compute a valid MAC without `K`.
    
- Common in secure protocols like **HMAC**, **IPSec**, **TLS**, etc.
    

---
### 🖋️ **Digital Signatures** 

#### ✅ **Definition**

A **digital signature** is a cryptographic technique that ensures **authentication**, **integrity**, and **non-repudiation** of a message. It works by **encrypting the hash (digest)** of a message using the **sender’s private key**, allowing any verifier with the **corresponding public key** to validate that the message originated from the claimed sender and has not been modified.
#### 🔐 **Mechanism of Digital Signature Using Hash Functions**
1. **Sender Side (Signing)**:
    - Compute hash of the message: `H(M)`
    - Encrypt the hash using sender’s **private key**: `DS = E_private(H(M))`
    - Send message `M` and digital signature `DS`
2. **Receiver Side (Verification)**:
    - Compute hash of received message: `H(M')`
    - Decrypt the received signature using sender’s **public key**: `H'(M) = D_public(DS)`
    - Compare `H(M')` with `H'(M)`. If they match, the message is:
        - Authentic (from sender)
        - Untampered (integrity maintained)
        - Signed and verifiable
#### 📌 **Properties Ensured by Digital Signatures**
- **Authentication**: Signature proves the identity of the sender.
- **Integrity**: Any change in message causes a hash mismatch.
- **Non-repudiation**: The sender **cannot deny** signing the message since only they hold the private key.
#### 🔁 **Techniques Illustrated (Figure 11.4)**
**(a) Basic Digital Signature:**
- `DS = E_private(H(M))`
- Signature is computed by encrypting hash with the sender’s private key.   
- Public key of sender is used by receiver to decrypt and verify.
**(b) Digital Signature + Confidentiality:**
- Message `M` and signature `DS` are **both encrypted** using a **symmetric key**.
- Ensures:
    - Message confidentiality (only the intended recipient can read it)
    - Signature verification (recipient decrypts, then verifies using public key)
#### ⚠️ **Security Considerations**
- An attacker **cannot forge** a digital signature without access to the **private key**.
- If the **private key is compromised**, signatures can be forged.
- Requires a **trusted public key infrastructure (PKI)** to associate public keys with identities (discussed in digital certificates/X.509).
#### 🔄 **Comparison with MAC**

| Feature                   | **MAC**                         | **Digital Signature**                     |
| ------------------------- | ------------------------------- | ----------------------------------------- |
| Key type                  | **Symmetric (shared key)**      | **Asymmetric (private/public key pair)**  |
| Provides non-repudiation? | ❌ No                            | ✅ Yes                                     |
| Verifiable by public?     | ❌ No (only by parties with key) | ✅ Yes (anyone with public key)            |
| Efficiency                | High                            | Relatively lower due to public-key crypto |
