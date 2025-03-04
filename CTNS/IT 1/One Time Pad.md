Source: [GPT](https://chatgpt.com/c/67c585b6-e260-8009-bae0-30b0ea684d33) [GFG](https://www.geeksforgeeks.org/implementation-of-vernam-cipher-or-one-time-pad-algorithm/) 

___

The One-Time Pad (OTP) is a symmetric encryption algorithm that achieves perfect secrecy by combining plaintext with a randomly generated key of equal or greater length, where each key is used only once, through a modular addition operation, resulting in ciphertext that bears no statistical relationship to the original plaintext.

#### **Working Mechanism**

- Each character of the **plaintext** is assigned a numerical value (A = 0, B = 1, ..., Z = 25).
- A **random key** of the same length as the plaintext is generated.
- Each character of the plaintext is encrypted using the key with a mathematical operation: 
	- `C=(P+K)mod  26` 
	where **P** is the plaintext, **K** is the key, and **C** is the ciphertext.
- The same key is used for decryption: `P=(C−K)mod  26`

#### **Requirements for Security**

1. **Key must be completely random** and as long as the message.
2. **Each key is used only once** and must be discarded after encryption.

| Advantages                                                                                    | Disadvantages                                                                                                                   |
| --------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------- |
| **Perfect Security** – It is mathematically proven to be unbreakable.                         | **Key Management** – Requires a truly random key as long as the message, making storage and distribution difficult.             |
| **No Pattern or Statistical Relation** – The ciphertext appears completely random.            | **One-Time Use** – Reusing a key compromises security.                                                                          |
| **Protection Against Frequency Analysis** – Unlike other ciphers, it provides no useful clues | **Not Practical for Large Messages** – Since the key size must match the message length, it is inefficient for large-scale use. |

#### **Example**

- **Plaintext:** **HELLO**
- **Random Key:** **XMCKL**
- **Encryption:**
    - H (7) + X (23) = (30) mod 26 = **D**
    - E (4) + M (12) = (16) mod 26 = **Q**
    - L (11) + C (2) = (13) mod 26 = **N**
    - L (11) + K (10) = (21) mod 26 = **V**
    - O (14) + L (11) = (25) mod 26 = **Z**
- **Ciphertext:** **DQNVZ**

Since the key is random and used only once, **decryption is impossible without the key**.

Thus, **One-Time Pad remains the most secure encryption method** but is impractical for everyday use due to its key management challenges.

___

[[Vignere Cipher]] :luc_arrow_left:
[[Playfair Cipher]] :luc_arrow_right: