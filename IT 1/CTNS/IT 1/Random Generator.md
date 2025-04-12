#it1 
Source: [GPT](https://chatgpt.com/c/67c585b6-e260-8009-bae0-30b0ea684d33)

---
## **1. Introduction to Random Number Generation**

- Random numbers are essential in cryptographic applications, simulations, and statistical sampling.
- True randomness is hard to achieve computationally, leading to the use of **pseudorandom number generators (PRNGs)**.
- A sequence is considered **random** if:
    - Each element is chosen independently from a probability distribution.
    - The Kolmogorov complexity (size of the smallest Turing machine that generates the sequence) is large.

---

## **2. Environmental Sources of Randomness (True Random Number Generators - TRNGs)**

- True random number generators (TRNGs) rely on unpredictable physical processes, including:
    - **Radioactive decay** (e.g., HotBits - [http://www.fourmilab.ch/hotbits/](http://www.fourmilab.ch/hotbits/))
    - **Radio frequency noise** (e.g., [http://www.random.org/](http://www.random.org/))
    - **Thermal noise from resistors/diodes**
    - **Keyboard timings and mouse movements**
    - **Interrupt timing in CPUs**
- These sources are **highly unpredictable** but require specialized hardware.

---

## **3. Combining Sources of Randomness**

- When multiple random sources exist, their outputs can be combined using:
    - XOR operation:  
        b=r1⊕r2⊕...⊕rkb = r_1 \oplus r_2 \oplus ... \oplus r_k
    - If **at least one** of the sources is truly random, the output remains random.
- Example sources:
    - JPEG file entropy
    - Audio signal noise
    - System clock values

---

## **4. Skew Correction (Von Neumann’s Algorithm)**

- Raw random numbers can be **biased**, leading to non-uniform distributions.
- **Von Neumann’s Algorithm:**
    1. Collect two consecutive random bits.
    2. If they are **identical**, discard them.
    3. If they are **different**, use the first bit.
- This method ensures an unbiased output but reduces efficiency.

---

## **5. Chi-Square Test for Randomness**

- Used to measure how close a sequence of numbers is to a truly random distribution.
- Given:
    - kk possible outcomes
    - p1,p2,...,pkp_1, p_2, ..., p_k probabilities for each outcome
    - Y1,Y2,...,YkY_1, Y_2, ..., Y_k observed occurrences
- The **Chi-square statistic** is calculated: X2=∑(Yi−npi)2npiX^2 = \sum \frac{(Y_i - np_i)^2}{np_i}
- Large X2X^2 values indicate deviation from randomness.

---

## **6. Analysis of Randomness**

- **random.org entropy test:**
    - Entropy: **7.9998 bits per character** (ideal: 8.0)
    - Arithmetic mean: **127.46 (expected 127.5)**
    - Monte Carlo estimation of π: **3.13896 (error 0.08%)**
    - Serial correlation coefficient: **0.000417** (ideal: 0.0)
- **JPEG entropy analysis:**
    - Entropy: **7.98 bits per character**
    - Monte Carlo π estimation: **3.1698 (error 0.90%)**
    - Higher correlation than ideal randomness.

---

## **7. Pseudorandom Number Generators (PRNGs)**

- PRNGs generate **deterministic sequences** that approximate randomness.
- **Properties:**
    - Fast and efficient.
    - Reproducible given the same seed.
    - **Not truly random**, but sufficient for many applications.
- **Cryptographic PRNGs** must ensure unpredictability and **next-bit resistance**.

---

## **8. Linear Congruential Generator (LCG)**

- A common PRNG defined by: Xn+1=(P1Xn+P2)mod  NX_{n+1} = (P_1 X_n + P_2) \mod N
- Example:
    - Parameters: P1=263,P2=71,N=100,X0=79P_1 = 263, P_2 = 71, N = 100, X_0 = 79
    - Generated sequence: **79, 48, 95, 56, 99, 8, ...**
- **Variants:**
    - **Park and Miller:** P1=16807,P2=0,N=231−1P_1 = 16807, P_2 = 0, N = 2^{31} - 1
    - **ANSI C rand():** P1=1103515245,P2=12345,N=231P_1 = 1103515245, P_2 = 12345, N = 2^{31}

---

## **9. Cryptographically Secure PRNGs (CSPRNGs)**

- Must pass the **next-bit test**, meaning that the next output bit **cannot be predicted**.
- **Yao’s Theorem (1982):** A PRNG that passes the next-bit test **passes all polynomial-time randomness tests**.
- Examples:
    - **SHA-1 and MD5 hash functions**
    - **AES-based PRNGs**
    - **Blum Blum Shub (BBS) Generator**

---

## **10. Blum Blum Shub (BBS) Secure PRNG**

- Based on the difficulty of **integer factorization**.
- Uses a **Blum integer** n=pqn = pq, where p,qp, q are primes such that: p≡q≡3mod  4p \equiv q \equiv 3 \mod 4
- **Generation Steps:**
    1. Choose a **random seed** X0X_0 coprime to nn.
    2. Compute **next state**: Xi=Xi−12mod  nX_i = X_{i-1}^2 \mod n.
    3. Output **least significant bit** of XiX_i as the next random bit.
- **Security:** If p,qp, q are unknown, recovering X0X_0 is infeasible.

---

## **11. Comparison of Random Number Generators**

|Method|Type|Strength|Weakness|
|---|---|---|---|
|**TRNGs**|True Random|Highly unpredictable|Requires specialized hardware|
|**LCG**|PRNG|Fast, simple|Predictable, short cycles|
|**Park-Miller**|PRNG|Better than LCG|Still predictable|
|**CSPRNGs**|Secure PRNG|Unpredictable, cryptographically secure|Slower than basic PRNGs|
|**BBS**|Secure PRNG|Based on number theory, very secure|Computationally expensive|

---

## **12. Conclusion**

- **True randomness** is ideal but impractical for many applications.
- **Pseudorandom generators** like **LCG and Park-Miller** are useful but predictable.
- **Cryptographically secure PRNGs** (CSPRNGs) like **BBS and AES-based PRNGs** ensure **strong security**.
- **Choosing the right method depends on the application (e.g., simulations, cryptography, gaming, etc.).**

---
[[Digital Signature]] :luc_arrow_left:
[[Steganography and it's application]] :luc_arrow_right: