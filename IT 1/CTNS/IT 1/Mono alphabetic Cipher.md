Source: [GFG](https://www.geeksforgeeks.org/what-is-monoalphabetic-cipher/)

---

Monoalphabetic Cipher is a type of **substitution cipher** in which each letter of the plaintext is mapped to a unique letter of the ciphertext using a single fixed substitution rule throughout the message. Unlike **Caesar Cipher**, where shifting is done by a fixed key, Monoalphabetic Cipher allows random mappings of letters, making it more complex.

#### **Types of Monoalphabetic Ciphers:**

1. **Additive Cipher** – Also known as **Shift Cipher**, shifts the plaintext letters by a fixed key.
    
    - Encryption: `C=(P+K)mod  26`
    - Example: **GEEKS** (Key = 4) → **KIIOW**
2. **Caesar Cipher** – A special case of Additive Cipher with a fixed key of **3**.
    
    - Example: **GEEKS** → **JHHNV**
3. **Multiplicative Cipher** – Uses multiplication instead of addition for encryption.
    
    - Example: **VMH** (Key = 3) → **HEL**
4. **Affine Cipher** – Combines both multiplicative and additive transformations.
    
    - Example: **ARM** (Key1 = 3, Key2 = 5) → **HEL**

#### **Working of Monoalphabetic Cipher**

- Each letter in the plaintext is replaced based on a predefined substitution.
- Example:
    - Plaintext: **GFG**
    - Ciphertext: **SRS** (Mapping: G → S, F → R)


| Advantages                                   | Disadvantages                                                            |
| -------------------------------------------- | ------------------------------------------------------------------------ |
| More secure than **Caesar Cipher**           | Easy to break using **frequency analysis**                               |
| Maintains frequency of letters in text  <br> | Prone to guessing attacks based on common **English letter occurrences** |
| Provides both **encryption and decryption**  | Less secure than **polyalphabetic ciphers**                              |

Monoalphabetic Cipher provides better security than basic shift ciphers but is still vulnerable to decryption techniques like frequency analysis.

---

[[Caesar Cipher]] :luc_arrow_left: 
[[Poly alpha Cipher]] :luc_arrow_right: