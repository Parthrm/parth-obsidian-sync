#it1 
Source: [GFG](https://www.geeksforgeeks.org/difference-between-monoalphabetic-cipher-and-polyalphabetic-cipher/)

___

A polyalphabetic cipher is any cipher based on substitution, using multiple substitution alphabets. The [Vigenère cipher](https://www.geeksforgeeks.org/vigenere-cipher/) is probably the best-known example of a polyalphabetic cipher, though it is a simplified special case. 

## **Applications of Polyalphabetic Cipher**

- Military and Diplomatic Use
- Modern [Cryptography](https://www.geeksforgeeks.org/cryptography-and-its-types/)
- Algorithm Development
- Research and Development
- Steganography and [Digital Watermarking](https://www.geeksforgeeks.org/digital-watermarking-and-its-types/)

## **Difference Between Monoalphabetic Cipher and Polyalphabetic Cipher**

| Monoalphabetic Cipher                                                                                                                                            | Polyalphabetic Cipher                                                                                                                                                                                                                         |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| A monoalphabetic cipher is one where each symbol in plain text is mapped to a fixed symbol in cipher text.                                                       | Polyalphabetic cipher is any cipher based on substitution, using multiple substitution alphabets.                                                                                                                                             |
| The relationship between a character in the plain text and the characters in the cipher text is one-to-one.                                                      | The relationship between a character in the plain text and the characters in the cipher text is one-to-many.                                                                                                                                  |
| Each alphabetic character of plain text is mapped onto a unique alphabetic character of a cipher text.                                                           | Each alphabetic character of plain text can be mapped onto ‘m’ alphabetic characters of a cipher text.                                                                                                                                        |
| A stream cipher is a monoalphabetic cipher if the value of key does not depend on the position of the plain text character in the plain text stream.             | A stream cipher is a polyalphabetic cipher if the value of key does depend on the position of the plain text character in the plain text stream.                                                                                              |
| It includes additive, multiplicative, [affine](https://www.geeksforgeeks.org/implementation-affine-cipher/) and monoalphabetic substitution cipher.              | It includes [autokey](https://www.geeksforgeeks.org/autokey-cipher-symmetric-ciphers/), Playfair, Vigenere, Hill, one-time pad, rotor, and [Enigma cipher.](https://www.geeksforgeeks.org/enigma-definition-english-meaning-machine-history/) |
| It is a simple substitution cipher.                                                                                                                              | It is multiple substitutions cipher.                                                                                                                                                                                                          |
| Monoalphabetic Cipher is described as a substitution cipher in which  the same fixed mappings from plain text to cipher letters across the entire text are used. | Polyalphabetic Cipher is described as substitution cipher in which plain text letters in different positions are enciphered using different cryptoalphabets.                                                                                  |
| Monoalphabetic ciphers are not that strong as compared to polyalphabetic cipher.                                                                                 | Polyalphabetic ciphers are much stronger.                                                                                                                                                                                                     |

___

[[Mono alphabetic Cipher]] :luc_arrow_left:
[[Vignere Cipher]] :luc_arrow_right: