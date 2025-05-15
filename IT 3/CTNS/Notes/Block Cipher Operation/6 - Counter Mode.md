
### **Definition:**
Counter Mode (CTR) is a block cipher mode of operation that converts a block cipher into a stream cipher. It uses a counter value for each block encryption, which is then XORed with the plaintext block to produce ciphertext. The counter must be unique for each block to maintain security.
### **Explanation:**
In CTR mode, instead of chaining like CBC or CFB, each plaintext block is XORed with the encryption of a unique counter value. This makes encryption and decryption parallelizable and highly efficient for both hardware and software implementations.
The counter starts from a nonce value and is incremented for each block.
Encryption: Cj = Pj ⊕ E(K, Tj)
Decryption: Pj = Cj ⊕ E(K, Tj)
For the last partial block of u bits, only the most significant u bits of E(K, Tj) are used.
There’s no need for padding in CTR mode because the XOR operation can handle partial blocks.

### **Example:**
Suppose we want to encrypt the plaintext blocks P1, P2, P3 using key K and initial counter T1:
T1 = Nonce
T2 = T1 + 1, T3 = T2 + 1, ...
Encrypt each counter: E(K, T1), E(K, T2), E(K, T3)
Compute ciphertexts:
$C_1 = P_1 ⊕ E(K, T_1)$
$C_2 = P_2 ⊕ E(K, T_2)$
$C_3 = P_3 ⊕ E(K, T_3)$
To decrypt, the same counters and key are used to get back the plaintexts.

### **Diagram:**

![[Pasted image 20250515014446.png]]
### **Formulas:**
**Encryption:**
	$Cj = Pj ⊕ E(K, Tj) for j = 1, ..., N-1$
	$C*_N = P*_N ⊕ MSB_u[E(K, TN)]$ (for last partial block)
**Decryption:**
	$P_j = C_j ⊕ E(K, T_j) for j = 1, ..., N-1$
	$P^*_N = C^*_N ⊕ MSB_u[E(K, T_N)]$
Where:
	$T_j$ = Counter value for block j
	$E(K, T_j)$ = Encryption of the counter using key K
	$MSB_u$ = Most significant u bits

### **Advantages:**
- Parallelism: Encryption/decryption can be done in parallel for all blocks.
- Hardware & Software Efficiency: Exploits modern CPU features like pipelining, SIMD.
- No Padding Needed: Works even if the last block is not full.
- Random Access: Any block can be independently encrypted/decrypted.
- Preprocessing: Counter encryption can be done ahead of time.
- Security: Provable security if counters are unique.
- Simplicity: Only encryption function is needed (even for decryption).
### **Disadvantages:**
- Counter Uniqueness is Critical: Reusing counter values with the same key leads to serious security vulnerabilities.
- Nonce Management: Requires careful tracking and unique initialization for each message.
- Does Not Detect Modifications: Like most modes, CTR does not provide integrity.
### **Works Best For:**
- High-performance encryption (parallel execution)
- Applications needing random-access to encrypted data
- Environments with strong nonce/counter management
- Real-time systems and IPsec, SSL/TLS
### **Does Not Work When:**
- The same counter value is reused with the same key (leads to key stream reuse and plaintext recovery)
- Nonce or counter values are not managed properly
- Environments where data integrity is required (needs additional authentication like HMAC)