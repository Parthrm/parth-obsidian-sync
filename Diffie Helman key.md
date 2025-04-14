### 🔹 **Definition**

Diffie–Hellman Key Exchange is a cryptographic algorithm that allows two parties to establish a shared secret key over an insecure communication channel. It was the first publicly known method for securely exchanging cryptographic keys.

### 🔹 **Explanation**

The main purpose of Diffie–Hellman is to enable two users (say, Alice and Bob) to agree on a secret key that they can later use for symmetric encryption. Although the communication of some values occurs over a public channel, the final shared key remains secret due to the mathematical difficulty of the **Discrete Logarithm Problem (DLP)**.

It relies on the fact that, while exponentiation modulo a large prime is computationally easy, finding the exponent (discrete logarithm) is hard.

>[!note|right-medium]
>![[Pasted image 20250414233726.png]]
### 🔹 **Algorithm**

Let:
- `q` = a large prime number
- `α` = a primitive root modulo `q`
- `XA` = Alice’s private key (randomly chosen, < q)
- `YA` = Alice’s public key = α^XA mod q
- `XB` = Bob’s private key (randomly chosen, < q)
- `YB` = Bob’s public key = α^XB mod q

#### 🔁 **Steps**
1. **Public Setup**:
    - Choose prime `q` and primitive root `α`.
    - Both values are publicly known.
2. **Key Generation**:
    - Alice picks private key `XA`, computes `YA = α^XA mod q`, and sends `YA` to Bob.
    - Bob picks private key `XB`, computes `YB = α^XB mod q`, and sends `YB` to Alice.
3. **Key Computation**:
    - Alice computes `K = YB^XA mod q`.
    - Bob computes `K = YA^XB mod q`.
    Since:
    ```
    K = α^(XB * XA) mod q = α^(XA * XB) mod q
    ```
    Both parties now share the same secret key `K`.

### 🔹 **Example**
Let:
- `q = 353`, `α = 3`
- Alice chooses `XA = 97` → `YA = 3^97 mod 353 = 40`
- Bob chooses `XB = 233` → `YB = 3^233 mod 353 = 248`
- Shared key:
    - Alice: `K = 248^97 mod 353 = 160`
    - Bob: `K = 40^233 mod 353 = 160`

So, shared key `K = 160`.

### 🔹 **Advantages**

1. ✅ **Secure Key Exchange**: Secret key is never transmitted.
2. ✅ **Public Channel Use**: Works over insecure communication.
3. ✅ **Foundation of Public Key Cryptography**: Introduced core concepts.
4. ✅ **No Prior Contact Needed**: Users can establish a key even if they haven’t met before.
5. ✅ **Simple Mathematical Operation**: Based on modular arithmetic.

### 🔹 **Disadvantages**

1. ❌ **No Authentication**: Vulnerable to **Man-in-the-Middle (MITM)** attacks unless combined with digital signatures.
2. ❌ **Requires Large Numbers**: Security depends on large prime numbers and long keys.
3. ❌ **Computation Heavy**: Especially with very large primes.
4. ❌ **Only for Key Exchange**: Can’t be used directly for encryption/decryption.

### 🔹 **Points of Failure**

1. ⚠️ **Small Prime or Weak Generator**: Makes it easier to break via brute-force.
2. ⚠️ **MITM Attack**: Without authentication, an attacker can intercept and replace public keys.
3. ⚠️ **Reused Keys**: Using the same private keys repeatedly reduces security.
4. ⚠️ **Improper Implementation**: Can lead to side-channel attacks or key leakage.
5. ⚠️ **Lack of Forward Secrecy**: If private key is leaked later, past keys may be compromised (unless ephemeral keys are used).
