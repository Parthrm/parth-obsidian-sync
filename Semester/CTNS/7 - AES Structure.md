### 🔐 **Advanced Encryption Standard (AES)**
- **Standardized by NIST** in **2001** as the successor to DES.
- Based on the **Rijndael algorithm** developed by **Joan Daemen and Vincent Rijmen**.
- **Symmetric block cipher**: uses the **same key** for encryption and decryption.

### 📦 **Block and Key Sizes**
- Operates on **128-bit blocks** of plaintext and ciphertext.
- Supports **key sizes** of:
    - **128 bits** (AES-128) → **10 rounds**
    - **192 bits** (AES-192) → **12 rounds**
    - **256 bits** (AES-256) → **14 rounds**

### 🔁 **AES Structure**
- Based on a **Substitution–Permutation Network (SPN)**, not a Feistel structure.
- Each round (except the last) includes 4 main transformations:
    1. **SubBytes** – Non-linear substitution using a **S-box** (byte-wise).
    2. **ShiftRows** – **Row-wise permutation** (circular shift of rows).
    3. **MixColumns** – **Column-wise mixing** using matrix multiplication in **GF(2⁸)**.
    4. **AddRoundKey** – **XOR** state with round key.
- **Initial Round**: Only **AddRoundKey**.
- **Final Round**: No **MixColumns** step.

### 🔑 **Key Expansion**
- AES uses a **key schedule** to derive **round keys** from the cipher key.
- Employs **Rcon constants** and **rotword**/**subword** operations.

### ✅ **Security Strength**
- Strong against known attacks:
    - **Brute-force**
    - **Differential and linear cryptanalysis**
- No practical attacks known against full AES (as of today).
- **Widely adopted** in government, financial, and enterprise systems.

### ⚙️ **Performance**
- **Efficient in both hardware and software**.
- Faster and more secure than DES and 3DES.
- Built-in support in **modern CPUs** (e.g., **AES-NI** instructions).
