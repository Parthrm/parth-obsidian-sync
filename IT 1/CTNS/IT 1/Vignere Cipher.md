Source: [GFG](https://www.geeksforgeeks.org/vigenere-cipher/)

---

Vigenere Cipher is a method of encrypting alphabetic text. It uses a simple form of [polyalphabetic substitution](https://en.wikipedia.org/wiki/Polyalphabetic_cipher). A polyalphabetic cipher is any cipher based on substitution, using multiple substitution alphabets. The encryption of the original text is done using the [__Vigenère square or Vigenère table__](https://en.wikipedia.org/wiki/Vigen%C3%A8re_cipher#/media/File:Vigen%C3%A8re_square_shading.svg).

- The table consists of the alphabets written out 26 times in different rows, each alphabet shifted cyclically to the left compared to the previous alphabet, corresponding to the 26 possible [Caesar Ciphers](https://www.geeksforgeeks.org/caesar-cipher/).
- At different points in the encryption process, the cipher uses a different alphabet from one of the rows.
- The alphabet used at each point depends on a repeating keyword.

## **Formulas**
```
Encryption
	Ei = (Pi + Ki) mod 26

Decryption
	Di = (Ei - Ki) mod 26

Where
	Ei -> Encrypted Text at index i
	Di -> Plain text at index i
	Ki -> key letter at index i
```

#### **Example**

Plaintext: **HELLO**
Key: **KEY** (repeated to match text length → **KEYKE**)
Encryption (A=0, B=1, ..., Z=25):
    - H (7) + K (10) = **R** (17)
    - E (4) + E (4) = **I** (8)
    - L (11) + Y (24) = **J** (9)
    - L (11) + K (10) = **V** (21)
    - O (14) + E (4) = **S** (18)
- **Ciphertext:** **RIJVS**

---
[[Poly alpha Cipher]] :luc_arrow_left:
[[One Time Pad]] :luc_arrow_right: