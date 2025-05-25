### **Steganography – Overview**

- **Definition**: The practice of **hiding the existence** of a message rather than scrambling its content like encryption.
- Purpose: To ensure that the presence of the message itself is not detected.

### **Techniques of Steganography**
1. **Text-based Techniques**:
    - **First-letter method**: First letters of each word or sentence reveal the hidden message.
    - **Word patterning**: Selecting specific words in a sentence to spell out the message.
2. **Traditional Physical Methods**:
    - **Character marking**: Marking certain letters faintly (e.g., with pencil).
    - **Invisible ink**: Writing with substances that appear only under heat or chemicals.
    - **Pin punctures**: Tiny holes in letters visible only against light.
    - **Typewriter correction ribbon**: Hidden text typed between lines, visible under strong light.
3. **Modern Digital Techniques**:
    - **Least Significant Bit (LSB) encoding**: Hide data in the least significant bits of image/audio/video files (e.g., digital images with minor pixel changes).
    - Tools/software exist to embed messages in **multimedia content**.

### **Advantages of Steganography**
- **Conceals communication**: Hides the _existence_ of the message.
- **Less suspicious** than encryption which signals protected or secret content.
- Can be used in combination with encryption for **added security**.

### **Disadvantages of Steganography**
- **Low data capacity**: Hides only small amounts of information.
- **Easily compromised**: Once the method is known, the system becomes ineffective.
- **High overhead**: Requires more resources (e.g., large media files) to hide small data.
- **Not foolproof**: Detection techniques (steganalysis) can expose hidden data.
