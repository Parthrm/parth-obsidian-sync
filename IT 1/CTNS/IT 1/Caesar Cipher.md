#it1 
Source: [GFG](https://www.geeksforgeeks.org/caesar-cipher-in-cryptography/)

___

The Caesar cipher is a simple encryption technique that was used by Julius Caesar to send secret messages to his allies. It works by shifting the letters in the plaintext message by a certain number of positions, known as the “shift” or “key”. The Caesar Cipher technique is one of the earliest and simplest methods of encryption techniques.

It’s simply a type of substitution cipher, i.e., each letter of a given text is replaced by a letter with a fixed number of positions down the alphabet. For example with a shift of 1, A would be replaced by B, B would become C, and so on. The method is apparently named after Julius Caesar, who apparently used it to communicate with his officials.

## Cryptography Algorithm For the Caesar Cipher

- Thus to cipher a given text we need an integer value, known as a shift which indicates the number of positions each letter of the text has been moved down.   
    The encryption can be represented using modular arithmetic by first transforming the letters into numbers, according to the scheme, A = 0, B = 1,…, Z = 25. Encryption of a letter by a shift n can be described mathematically as. 

- For example, if the shift is 3, then the letter A would be replaced by the letter D, B would become E, C would become F, and so on. The alphabet is wrapped around so that after Z, it starts back at A.

- Here is an example of how to use the Caesar cipher to encrypt the message “HELLO” with a shift of 3:

1. Write down the plaintext message: HELLO
2. Choose a shift value. In this case, we will use a shift of 3.
3. Replace each letter in the plaintext message with the letter that is three positions to the right in the alphabet.

 H becomes K (shift 3 from H)         
 E becomes H (shift 3 from E)      
 L becomes O (shift 3 from L)         
 L becomes O (shift 3 from L)           
 O becomes R (shift 3 from O)

      4.The encrypted message is now “KHOOR”.

- To decrypt the message, you simply need to shift each letter back by the same number of positions. In this case, you would shift each letter in “KHOOR” back by 3 positions to get the original message, “HELLO”.

  
```
En(x)=(x+n)mod 26
(Encryption Phase with shift n)

Dn(x)=(x−n)mod 26
(Decryption Phase with shift n)
```


![Caesar Cipher Technique](https://media.geeksforgeeks.org/wp-content/uploads/ceaserCipher.png)



| Advantages 🟢                                                                                         | Disadvantages 🔴                                                                                                                   |
| ----------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------- |
| Easy to implement and use making it suitable for beginners.                                           | It's not secure against modern decryption methods                                                                                  |
| Can be physically implemented, such as with a set of rotating dicks or a set of cards.                | Vulnerable to know plain text attacks, when an attacker has access to both the encrypted and unencrypted versions of the same text |
| Requires only a small set of pre-shared information                                                   | The small number of possible keys allows the attacker to try all possible keys to find the correct one.                            |
| Can be modified to create a more secure variant, such as by using a multiple shift values or keywords | It is not suitable for secure communication as it is easily broken                                                                 |
|                                                                                                       | Does not provide confidentiality, integrity, and authenticity in a message                                                         |

### **Features of Caesar Cipher**

1. **Substitution cipher:** The Caesar cipher is a type of [substitution cipher](https://www.geeksforgeeks.org/substitution-cipher/), where each letter in the plaintext is replaced by a letter some fixed number of positions down the alphabet.
2. **Fixed key:** The Caesar cipher uses a fixed key, which is the number of positions by which the letters are shifted. This key is known to both the sender and the receiver.
3. **Symmetric encryption:** The Caesar cipher is a [symmetric encryption](https://www.geeksforgeeks.org/what-is-a-symmetric-encryption/) technique, meaning that the same key is used for both encryption and decryption.
4. **Limited keyspace:** The Caesar cipher has a very limited keyspace of only 26 possible keys, as there are only 26 letters in the English alphabet.
5. **Vulnerable to brute force attacks:** The Caesar cipher is vulnerable to [brute force attacks](https://www.geeksforgeeks.org/brute-force-attack/), as there are only 26 possible keys to try.
6. **Easy to implement:** The Caesar cipher is very easy to implement and requires only simple arithmetic operations, making it a popular choice for simple encryption tasks.

### **Rules for the Caesar Cipher**

1. Choose a number between 1 and 25. This will be your “shift” value.
2. Write down the letters of the alphabet in order, from A to Z.
3. Shift each letter of the alphabet by the “shift” value. For example, if the shift value is 3, A would become D, B would become E, C would become F, and so on.
4. Encrypt your message by replacing each letter with the corresponding shifted letter. For example, if the shift value is 3, the word “hello” would become “khoor”.
5. To decrypt the message, simply reverse the process by shifting each letter back by the same amount. For example, if the shift value is 3, the encrypted message “khoor” would become “hello”.

### **Algorithm for Caesar Cipher**

**Input:** 

1. Choose a shift value between 1 and 25.
2. Write down the alphabet in order from A to Z.
3. Create a new alphabet by shifting each letter of the original alphabet by the shift value. For example, if the shift value is 3, the new alphabet would be:
4. A B C D E F G H I J K L M N O P Q R S T U V W X Y Z  
    D E F G H I J K L M N O P Q R S T U V W X Y Z A B C
5. Replace each letter of the message with the corresponding letter from the new alphabet. For example, if the shift value is 3, the word “hello” would become “khoor”.
6. To decrypt the message, shift each letter back by the same amount. For example, if the shift value is 3, the encrypted message “khoor” would become “hello”.

___

[[Basic Cryptography Techniques]] :luc_arrow_left: 
[[Mono alphabetic Cipher]] :luc_arrow_right: