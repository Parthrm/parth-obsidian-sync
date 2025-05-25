### **Transposition Ciphers**

- Rearrange the **positions of characters** in the plaintext.
- Characters remain **unchanged**, only their order is shuffled.
- Involves a **key** that determines the pattern of rearrangement.
- Unlike substitution ciphers, **no character substitution** occurs.
- Used for achieving **confusion** in cryptography.

### **Rail Fence Cipher**
- A **simple transposition cipher**.
- Write plaintext in a **zigzag pattern** across multiple "rails" (rows).
- Example (3-rail cipher):
    ```
    P . . . A . . . H . . . N . . .  
    . L . S . I . G . P . I . 
    . . A . . . Y . . . R . . .
    ```
- Read row-wise to get ciphertext.
- **Key** = number of rails.

### **Row Transposition Cipher**
- Write plaintext into a **matrix (row-wise)**.
- Rearrange **columns** based on a **numeric key**.
- Example:
    - Key: 3 1 4 2
    - Rearranged columns: 2nd, 4th, 1st, 3rd
- Read **column-wise** using key order to get ciphertext.
- More secure than Rail Fence.
