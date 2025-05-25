#topic #unit1


### Diagram:
![[Diagram - Simplified Model of Symmetric Encryption.excalidraw]]
### Important Points:

#### **5 ingredients of symmetric encryption scheme:** 
1. **Plaintext**: This is the original intelligible message or data that is fed into the algorithm as input.
2. **Encryption algorithm**: The encryption algorithm performs various substitutions and transformations on the plaintext. 
3. **Secret key**: The secret key is also input to the encryption algorithm. The key is a value independent of the plaintext and of the algorithm. The algorithm will produce a different output depending on the specific key being used at the time. The exact substitutions and transformations performed by the algorithm depend on the key.
4. **Ciphertext**: This is the scrambled message produced as output. It depends on the plaintext and the secret key. For a given message, two different keys will produce two different ciphertexts. The ciphertext is an apparently random stream of data and, as it stands, is unintelligible. 
5. **Decryption algorithm**: This is essentially the encryption algorithm run in reverse. It takes the ciphertext and the secret key and produces the original plaintext.
#### **Cryptography**
- **Characterized by three independent dimensions:**
	- **Type of operations:**
		- **Substitution:** Each element (bit, letter, group) in the plaintext is mapped to another element.
		- **Transposition:** Elements in the plaintext are rearranged.
		- **Requirement:** All operations must be reversible, ensuring no information is lost.
		- **Product systems:** Most systems involve multiple stages of both substitutions and transpositions.
	- **Number of keys used:**
		- **Symmetric (single-key, secret-key, conventional encryption):** Both sender and receiver use the same key.
		- **Asymmetric (two-key, public-key encryption):** Sender and receiver use different keys.
	- **Plaintext processing method:**
		- **Block cipher:** Processes input one block at a time, producing an output block for each input block.
		- **Stream cipher:** Processes input elements continuously, producing output one element at a time.
#### **Cryptanalysis and Brute-Force Attack**
- **Objective:** To recover the key in use, rather than just the plaintext of a single ciphertext.
    - **Two general approaches to attacking conventional encryption:**
        - **Cryptanalysis:**
            - Relies on the algorithm's nature, potentially with knowledge of plaintext characteristics or sample plaintext-ciphertext pairs.
            - Exploits algorithm characteristics to deduce specific plaintext or the key.
        - **Brute-force attack:**
            - The attacker tries every possible key on a piece of ciphertext until an intelligible plaintext is obtained.
            - On average, half of all possible keys must be tried for success.
#### **Security of Encryption Schemes**
- **Unconditionally Secure:**
	- Ciphertext does not contain enough information to uniquely determine the plaintext, regardless of how much ciphertext is available or how much time an opponent has.
        - Impossible to decrypt simply because the required information isn't present.
        - **Exception:** The one-time pad is virtually the only unconditionally secure encryption algorithm.
        - Therefore, most encryption algorithms cannot achieve unconditional security.
- **Computationally Secure:** An encryption scheme is considered computationally secure if either of the following criteria are met:
	- The cost of breaking the cipher (cryptanalysis) exceeds the value of the encrypted information.
	- The time required to break the cipher exceeds the useful lifetime of the information.
	- **Challenge:** It is very difficult to accurately estimate the effort needed to successfully cryptanalyze ciphertext.
#### **Cryptanalysis for Different Encryption Schemes**
- **Symmetric Encryption Schemes:**
	- Cryptanalysis aims to exploit traces of structure or patterns in the plaintext that may survive encryption and be discernible in the ciphertext.
- **Public-Key Schemes (Asymmetric Encryption):**
	- Cryptanalysis proceeds from a fundamentally different premise.
	- It focuses on the mathematical properties of the key pair, potentially allowing one key to be deduced from the other.
#### **Brute-Force Attack**
- **Method:** Involves trying every possible key until an intelligible translation of the ciphertext into plaintext is obtained.
- **Average Attempts:** On average, half of all possible keys (X/2 tries for X different keys) must be tried to achieve success.
- **Beyond Key Trials:**
	- Requires the analyst to be able to recognize plaintext as plaintext.
	- **Ease of Recognition:**
		- **Plain English text:** Relatively easy to recognize, but requires automated recognition.
		- **Compressed text:** More difficult to recognize.
		- **General data (e.g., numerical files, especially if compressed):** Even more difficult to automate recognition.
	- **Supplementing Brute-Force:**
		- Some degree of knowledge about the expected plaintext is needed.
		- Some means of automatically distinguishing plaintext from garble (meaningless output) is also necessary.

| Type of Attack        | Information Known to Cryptanalyst                                                                                                                                                                                                                                                  | Description and Implications                                                                                                                                                                                                                                                                                                                                                                                                                 |
| :-------------------- | :--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Ciphertext Only**   | - Encryption algorithm<br>- Ciphertext                                                                                                                                                                                                                                             | This is the most difficult attack to defend against as the opponent has the least amount of information. The attacker must rely on statistical analysis of the ciphertext or a **brute-force attack** (trying all possible keys). Requires some general idea of the plaintext type (e.g., English text, EXE file) for successful analysis or recognition of decrypted output. Only relatively weak algorithms fail to withstand this attack. |
| **Known Plaintext**   | - Encryption algorithm<br>- Ciphertext<br>- One or more plaintext–ciphertext pairs formed with the secret key                                                                                                                                                                      | The analyst has access to some plaintext messages and their corresponding encrypted versions. This knowledge allows the analyst to deduce the key based on how the known plaintext is transformed. Examples include standard file headers, patterns, or probable words within the message. Encryption algorithms are generally designed to withstand this type of attack.                                                                    |
| **Chosen Plaintext**  | - Encryption algorithm<br>- Ciphertext<br>- Plaintext message chosen by cryptanalyst, along with its corresponding ciphertext generated with the secret key                                                                                                                        | The analyst can choose specific plaintext messages and obtain their corresponding ciphertexts. This allows the analyst to deliberately pick patterns that are expected to reveal the structure of the key, making it a powerful attack.                                                                                                                                                                                                      |
| **Chosen Ciphertext** | - Encryption algorithm<br>- Ciphertext<br>- Ciphertext chosen by cryptanalyst, along with its corresponding decrypted plaintext generated with the secret key                                                                                                                      | The analyst can choose specific ciphertexts and obtain their corresponding decrypted plaintexts. This type of attack is less commonly employed but can still be a possible avenue for cryptanalysis.                                                                                                                                                                                                                                         |
| **Chosen Text**       | - Encryption algorithm<br>- Ciphertext<br>- Plaintext message chosen by cryptanalyst, along with its corresponding ciphertext generated with the secret key<br>- Ciphertext chosen by cryptanalyst, along with its corresponding decrypted plaintext generated with the secret key | This is a combination of both chosen plaintext and chosen ciphertext attacks, where the analyst has control over both the input to be encrypted and the output to be decrypted. This provides the cryptanalyst with a significant amount of control and information.                                                                                                                                                                         |
### Formulas:

$Y = E(K, X)$
$X = D(K, Y)$

### Semester Questions:

___