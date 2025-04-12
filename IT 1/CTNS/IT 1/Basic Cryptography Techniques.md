#it1 
Features of Cryptography
- **Confidentiality:** Ensures data secrecy.
- **Integrity:** Protects data from unauthorized modification.
- **Non-repudiation:** Prevents denial of message origin.
- **Authentication:** Verifies sender and receiver identities.
- **Interoperability:** Enables secure communication across systems.
- **Adaptability:** Evolves to counter new threats.

Source: [GFG](https://www.geeksforgeeks.org/cryptography-and-its-types/)
## ***Types Of Cryptography***
### ***1. Symmetric Key Cryptography***

It is an encryption system where the sender and receiver of a message use a single common key to encrypt and decrypt messages. [Symmetric Key cryptography](https://www.geeksforgeeks.org/what-is-a-symmetric-encryption/) is faster and simpler but the problem is that the sender and receiver have to somehow exchange keys securely. The most popular symmetric key cryptography systems are [Data Encryption Systems (DES)](https://www.geeksforgeeks.org/data-encryption-standard-des-set-1/) and [Advanced Encryption Systems (AES)](https://www.geeksforgeeks.org/advanced-encryption-standard-aes/) .
### ***2. Hash Functions***

There is no usage of any key in this algorithm. A hash value with a fixed length is calculated as per the plain text which makes it impossible for the contents of plain text to be recovered. Many operating systems use hash functions to encrypt passwords.

### ***3. Asymmetric Key Cryptography***

In [Asymmetric Key Cryptography,](https://www.geeksforgeeks.org/asymmetric-key-cryptography/) a pair of keys is used to encrypt and decrypt information. A sender’s public key is used for encryption and a receiver’s private key is used for decryption. Public keys and Private keys are different. Even if the public key is known by everyone the intended receiver can only decode it because he alone knows his private key. The most popular asymmetric key cryptography algorithm is the RSA algorithm.

[[Caesar Cipher]] :luc_arrow_right: