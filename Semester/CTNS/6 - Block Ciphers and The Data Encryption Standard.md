### 1️⃣ **Traditional Block Cipher Structure**
- Operates on **fixed-size blocks** of plaintext (e.g., 64 bits).
- Uses **symmetric key** (same key for encryption and decryption).
- Involves **substitution and permutation** steps to create confusion and diffusion.
- Employs a series of **rounds** (e.g., 16 rounds) for multiple transformations.
- Common structure: **Feistel Network**, where:
    - Block is split into **two halves (L and R)**.
    - One half is transformed using a function and key, then **XORed** with the other half.
    - Halves are swapped and the process repeats.

### 2️⃣ **Data Encryption Standard (DES)**
- A **symmetric block cipher** developed by IBM and standardized by NIST in 1977.
- Operates on **64-bit blocks** of plaintext.
- Uses a **56-bit key** (plus 8 parity bits, totaling 64 bits).
- Consists of **16 Feistel rounds**.
- Each round uses a **different 48-bit subkey** derived from the main key.
- Employs **initial and final permutation** and a complex **round function (f)**.

### 3️⃣ **A DES Example**
- **Plaintext** (64-bit) is input.
- Apply **Initial Permutation (IP)**.
- Split into **L0 and R0** (32 bits each).
- For each round (1 to 16):
    - Li = Ri-1
    - Ri = Li-1 ⊕ f(Ri-1, Ki)
- After 16 rounds, combine and apply **Inverse Initial Permutation (IP⁻¹)**.
- **Ciphertext** (64-bit) is the final output.
- f-function includes:
    - Expansion (E), Key Mixing, S-box Substitution, and Permutation (P).

### 4️⃣ **The Strength of DES**
- **Strengths**:
    - Strong **confusion and diffusion**.
    - Resistant to many known cryptanalytic attacks (for its time).
    - Simple and fast in hardware.
- **Weaknesses**:
    - **56-bit key** is too short — vulnerable to **brute-force attacks**.
    - Susceptible to **differential and linear cryptanalysis** with enough plaintext-ciphertext pairs.
    - **Outdated** for modern security needs — replaced by AES.
