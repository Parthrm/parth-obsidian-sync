#it1 
1. Explain Round Function or F Function of DES algorithm with neat diagram. How to improve the performance of DES algorithm? Discuss. (5 marks)
	**Working of the F Function in DES**
	
	The **F Function** is applied in each round of DES and consists of the following steps:
	
	1. **Expansion (E-Box)**
	    
	    - The **32-bit right half** (R) is expanded to **48 bits** using an **Expansion Permutation Table**.
	    - This introduces **redundancy** and increases diffusion.
	2. **Key Mixing (XOR Operation)**
	    
	    - The expanded **48-bit right half** is **XORed** with a **48-bit round subkey** (generated from the 56-bit main key).
	3. **Substitution (S-Boxes)**
	    
	    - The **48-bit XOR result** is divided into **8 blocks of 6 bits each**.
	    - Each block is passed through an **S-Box (Substitution Box)**, reducing it to **4 bits**.
	    - S-Boxes introduce **non-linearity**, making DES harder to break.
	4. **Permutation (P-Box)**
	    
	    - The 32-bit output from the S-Boxes is permuted using a **P-Box (Permutation Table)**.
	    - This improves **diffusion**, ensuring small changes in input lead to large changes in output.
	5. **XOR with Left Half**
	    
	    - The **P-Box output** is **XORed with the left half (L)** of the data block.
	    - The result becomes the new **right half** for the next round.
	
	Despite being widely used, DES has weaknesses. The following improvements can enhance its performance:
	
	**A. Increasing Key Size**
	- **DES uses a 56-bit key**, which is vulnerable to **brute-force attacks**.
	- **Triple DES (3DES)** extends security by applying DES **three times** with **different keys**.
	
	**B. Using Advanced Encryption Algorithms**
	- **AES (Advanced Encryption Standard)** provides stronger security with **128-bit, 192-bit, or 256-bit keys**.
	- AES replaces DES for most modern applications.
	
	**C. Hardware Acceleration**
	- Implementing DES using **parallel processing** or **dedicated hardware (ASICs, FPGAs)** increases encryption speed.
	
	**D. Using Feistel Variants**
	- **Blowfish & Twofish** use modified **Feistel structures** with improved S-Boxes and diffusion techniques.
	
	**E. Hybrid Encryption Techniques**
	
	- Combining **DES with public-key encryption (RSA, ECC)** improves security without increasing computational load.
2. Generate cipher text for the given message="Attack target at sharp One pm" using playfair technique. Use key as "Atom Bomb". (5 marks)
	Given Message: `"Attack target at sharp One pm"`  
	Key: `"Atom Bomb"
	
	**Step 1: Constructing the Playfair Cipher Key Square**
	- **Key Processing:** `"Atom Bomb"` (Remove duplicates) → **"ATOMB"**
	- **Fill the remaining letters of the alphabet** (excluding **J**, as J is merged with I).
	5×5 Key Square:
	```
	A T O M B
	C D E F G
	H I/J K L N
	P Q R S U
	V W X Y Z
	```
	
	**Step 2: Preparing the Plaintext**
	
	1. **Remove spaces:** `"AttacktargetatsharpOnepm"`
	2. **Break into digraphs (pairs of letters):**
	    ```
	    AT  TA  CK  TA  RG  ET  AT  SH  AR  PO  NE  PM
	    ```
	3. **Rules to handle repeated letters and odd-length plaintext:**
	    - No repeated letters in pairs → No modifications needed.
	    - The message is **even-length** → No need for an extra letter.

	**Step 3: Encrypt Using Playfair Rules**
	**Rules:**
	1. **Same row:** Replace each letter with the letter to its right (wrap to the left if at the end).
	2. **Same column:** Replace each letter with the letter below (wrap to the top if at the bottom).
	3. **Rectangle rule:** Swap the letters diagonally.
	
	**Encryption Process:**
	|AT| Same Row      (A → T, T → O)    | TO |
	|TA| Same Row      (T → O, A → T)    | OT |
	|CK| Rectangle      (C → E, K → H)    | EH |
	|TA| Same Row      (T → O, A → T)    | OT |
	|RG| Rectangle      (R → U, G → E)    | UE |
	|ET| Rectangle      (E → G, T → O)    | GO |
	|AT| Same Row      (A → T, T → O)    | TO |
	|SH| Rectangle      (S → U, H → P)    | UP |
	|AR| Rectangle      (A → B, R → T)    | BT |
	|PO| Rectangle      (P → R, O → M)    | RM |
	|NE| Rectangle      (N → G, E → K)    | GK |
	|PM| Rectangle      (P → S, M → B)    | SB |
	
	**Step 4: Ciphertext Output**
	**Ciphertext:**
	```
	TO OT EH OT UE GO TO UP BT RM GK SB
	```
3. Q.3)Why RSA algorithm is considered as strong algorithm? Discuss. Generate cipher text for the given message =" Transfer 10K" using RSA algorithm. Consider public key as (7,33) and private key as (3,33). (5 marks)
	
	The **RSA algorithm** is considered **strong** due to the following reasons:
	1. **Asymmetric Encryption**
	    - Uses **two keys**: a **public key (e, n)** for encryption and a **private key (d, n)** for decryption.
	    - Even if an attacker knows the **public key**, they cannot decrypt the message without the **private key**.
	2. **Based on Integer Factorization Problem**
	    - RSA security relies on the **difficulty of factoring large prime numbers**.
	    - Given n=p×qn = p \times q, where pp and qq are large primes, breaking RSA requires **factoring nn**, which is computationally infeasible for large values.
	3. **Mathematical One-Way Function**
	    - Encryption and decryption involve **modular exponentiation**, making it easy to compute but extremely hard to reverse without the private key.
	4. **Resistance to Brute-Force Attacks**
	    - Large key sizes (e.g., **2048-bit RSA**) make brute-force attacks impractical.
	    - **Quantum computing** poses a future threat, but currently, RSA with a sufficiently large key is secure.
	5. **Widespread Use**
	    - Used in **SSL/TLS encryption, digital signatures, and secure communication** worldwide.
	    - No known practical attack can break RSA encryption when **proper key sizes** are used.

	**RSA Ciphertext Generation for "Transfer 10K"**
	**Given:**
	- **Public Key**: (e,n)=(7,33)(e, n) = (7, 33)
	- **Private Key**: (d,n)=(3,33)(d, n) = (3, 33)
	- **Message**: `"Transfer 10K"`
	
	**Step 1: Convert Message to Numerical Form**
	Each character is converted to ASCII values:
	
	|Character|ASCII Value|
	|---|---|
	|T|84|
	|r|114|
	|a|97|
	|n|110|
	|s|115|
	|f|102|
	|e|101|
	|r|114|
	|**Space**|32|
	|1|49|
	|0|48|
	|K|75|
	
	---
	
	**Step 2: Encrypt Each Character Using RSA Formula**
	
	**Encryption Formula:**
	
	C = (M^e) \mod n
	where:
	
	- M is the ASCII value of the character.
	- e=7, n=33
	
	Let's compute ciphertext for each character:
	
	|Character|ASCII (M)|Ciphertext (C = M7mod  33M^7 \mod 33)|
	|---|---|---|
	|T|84|847mod  33=2184^7 \mod 33 = 21|
	|r|114|1147mod  33=24114^7 \mod 33 = 24|
	|a|97|977mod  33=3197^7 \mod 33 = 31|
	|n|110|1107mod  33=4110^7 \mod 33 = 4|
	|s|115|1157mod  33=13115^7 \mod 33 = 13|
	|f|102|1027mod  33=30102^7 \mod 33 = 30|
	|e|101|1017mod  33=29101^7 \mod 33 = 29|
	|r|114|1147mod  33=24114^7 \mod 33 = 24|
	|**Space**|32|327mod  33=3232^7 \mod 33 = 32|
	|1|49|497mod  33=1649^7 \mod 33 = 16|
	|0|48|487mod  33=2748^7 \mod 33 = 27|
	|K|75|757mod  33=1875^7 \mod 33 = 18|
	
	---
	
	**Step 3: Final Encrypted Ciphertext**
	
	The ciphertext for `"Transfer 10K"` using RSA with public key (7,33)(7,33) is:
	
	👉 **"21 24 31 4 13 30 29 24 32 16 27 18"**

