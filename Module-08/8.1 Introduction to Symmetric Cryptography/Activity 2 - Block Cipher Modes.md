## Activity Objective

The objective of this quiz is to deepen your understanding of block cipher modes of operation by evaluating your knowledge of their characteristics, advantages, disadvantages, and practical applications. Through a series of questions and problem-solving tasks, you will demonstrate your ability to:
1. Identify and Describe Modes: Recognize and describe the key features of various block cipher modes of operation, including ECB, CBC, CFB, OFB, CTR, and GCM.
2. Compare and Contrast: Compare the strengths and weaknesses of different block cipher modes, understanding their use cases, and knowing when each mode is appropriate or unsuitable.
3. Apply Knowledge Practically: Solve practical problems involving encryption and decryption using different modes of operation to reinforce your theoretical understanding with real-world applications.
4. Analyze Security Implications: Assess the security implications of each mode, identifying potential vulnerabilities and understanding how each mode addresses or fails to address these security concerns.
By the end of the quiz, you should have a comprehensive understanding of block cipher modes and their practical implications for secure communication and data protection.

## Activity Instructions
Complete the knowledge check below.

## Knowledge Check
1. What is the most basic form of block cipher modes?
   1. Electronic Codebook (ECB)
   2. Cipher Block Chaining (CBC)
   3. Counter (CTR)
   4. Cipher Feedback (CFB)
<details closed>
<summary>Answer</summary>
ECB is the most basic mode, but it is generally not recommended for real-world use due to its lack of security.</details>

2. Which block cipher mode can operate similar to a stream cipher? (Select all that Apply)
   1. Output feedback (OFB)
   2. Cipher Block Chaining (CBC)
   3. Counter (CTR)
   4. Electronic Codebook (ECB)
<details closed>
<summary>Answer</summary>
CTR (Counter) mode and OFB (Output Feedback) mode are block cipher modes that work similarly to stream ciphers by turning block ciphers into a stream of keystream bits. In CTR mode, a counter value is encrypted for each block, and the result is XORed with the plaintext. This allows blocks to be processed in parallel and makes CTR fast and efficient. In OFB mode, an initial value (called the IV) is repeatedly encrypted to create a keystream, which is also XORed with the plaintext. Unlike CTR, OFB does not change the input for each block based on the previous block's output, making it more resistant to certain types of errors. Both modes allow you to encrypt data of any size and avoid the pattern issues seen in basic modes like ECB.</details>

3. In which block cipher mode do you use an IV to start the encryption process?
   1. Cipher Block Chaining (CBC)
   2. Output feedback (OFB)
   3. Electronic Codebook (ECB)
   4. Cipher Feedback (CFB)
   5. Counter (CTR)
<details closed>
<summary>Answer</summary>
An IV is a starting input value used in block cipher modes like CBC, CFB, OFB, and CTR to add randomness and prevent repeatable ciphertext. It's essential for secure encryption and helps ensure that the same plaintext never produces the same ciphertext when encrypted more than once.</details>

4. Which block cipher mode does not hide data patterns well?
   1. Electronic Codebook (ECB)
   2. Cipher Block Chaining (CBC)
   3. Output feedback (OFB)
   4. Cipher Feedback (CFB)
<details closed>
<summary>Answer</summary>
The block cipher mode that does not hide data patterns well is ECB (Electronic Codebook). In ECB mode, the plaintext is divided into fixed-size blocks, and each block is encrypted independently using the same key. This means that if the same plaintext block appears more than once, it will always produce the same ciphertext block. As a result, repeating patterns in the input remain visible in the encrypted output. This makes ECB insecure for most real-world use cases, especially with structured data like images, where patterns can reveal outlines or details even after encryption.</details>

5. Describe the main difference between the ECB and CBC modes.
<details closed>
<summary>Answer</summary>
The main difference between ECB and CBC is how they handle each block of data. In ECB (Electronic Codebook) mode, each block of plaintext is encrypted on its own, so if the same block appears more than once, it produces the same ciphertext. This makes patterns in the data easy to spot, which is a security risk. In CBC (Cipher Block Chaining) mode, each block of plaintext is combined with the previous block's ciphertext before being encrypted, which helps hide patterns and makes the encryption more secure. CBC also uses an IV (Initialization Vector) to start the process and add randomness to the first block.</details>

6. If you were to encrypt a large file and needed to ensure both confidentiality and high performance, which block cipher mode would you choose and why?
<details closed>
<summary>Answer</summary>
If you need to encrypt a large file and want it to be done fast and in a secure manner, CTR would be the best choice. This is because CTR orks by turning a block cipher into a fast stream of encrypted data, allowing the computer to encrypt many parts of the file at the same time. This makes it much faster than other modes like CBC, which have to process each block one after another. CTR also keeps the data secure by hiding patterns, as long as the IV  is different each time. </details>

7. Why is IV reuse a critical security concern in GCM, CTR, OFB, CFB and CBC? What are its implications?
<details closed>
<summary>Answer</summary>
Reusing an IV (Initialization Vector) in block cipher modes like GCM, CTR, OFB, CFB, and CBC is a serious security risk because it can lead to leaks of information or even allow attackers to break the encryption. These modes rely on a unique IV for each encryption to ensure that the same plaintext produces different ciphertext every time. If the same IV is reused with the same key, patterns can appear, and in modes like CTR and GCM, it can allow attackers to recover the original plaintext or forge messages. In simple terms, reusing an IV removes the randomness that protects the data, making the encryption much easier to break and the data no longer secure.</details>

8. For which mode of operation is each block of plaintext is encrypted independently of the others.
   1. Cipher Block Chaining (CBC)
   2. Counter (CTR)
   3. Output feedback (OFB)
   4. Electronic Codebook (ECB)
<details closed>
<summary>Answer</summary>
The mode of operation where each block of plaintext is encrypted independently of the others is called ECB (Electronic Codebook) mode. In ECB, the plaintext is divided into equal-sized blocks, and each block is encrypted on its own using the same key. This means that if the same block of plaintext appears more than once, it will always produce the same block of ciphertext. While this makes ECB simple and fast, it also makes it insecure, because it does not hide patterns in the data. Repeated content becomes visible in the encrypted output, which can give clues to attackers.</details>

9. Which mode of operation, is designed to use a feedback mechanism to allow encryption of data in smaller increments than the block size?
   1. Output feedback (OFB)
   2. Cipher Feedback (CFB)
   3. Galois/ Counter Mode (GCM)
   4. Cipher Block Chaining (CBC)
<details closed>
<summary>Answer</summary>
CFB (Cipher Feedback) mode is a way of encrypting data that lets you work with small pieces of data, not just full-size blocks. It starts by encrypting a special starting value called an IV (Initialization Vector), then uses part of that to mix with (XOR) a small piece of the real message. That result becomes part of the next step, like a chain. And because it uses a feedback loop, CFB can encrypt data one bit or byte at a time, which is helpful for things like live data or streaming, where the message doesn’t always come in full blocks.</details>

10. Which mode of operation, ensures that each block plaintext is XORed with the previous ciphertext block before encryption?
     1. Electronic Codebook (ECB)
     2. Cipher Feedback (CFB)
     3. Cipher Block Chaining (CBC)
     4. Counter (CTR)
<details closed>
<summary>Answer</summary>
The mode of operation where each block of plaintext is XORed with the previous ciphertext block before encryption is CBC (Cipher Block Chaining) mode.  This creates a chain, where each block depends on the one before it.</details>

11. Which mode of operation involves initializing a nonce, generating a unique counter for each block, encrypting the counter to produce a keystream, XORing the keystream with the plaintext to produce ciphertext, and then computing an authentication tag to ensure data integrity?
     1. Cipher Feedback (CFB)
     2. Counter (CTR)
     3. Galois/ Counter Mode (GCM)
     4. Output feedback (OFB)
<details closed>
<summary>Answer</summary>
GCM (Galois/Counter Mode) is a block cipher mode that provides both encryption and authentication in one process. It starts by using a nonce and a counter to generate a keystream, just like CTR mode, and then XORs that keystream with the plaintext to produce the ciphertext. What makes GCM special is that, after encryption, it also creates an authentication tag using a mathematical process called Galois field multiplication. This tag helps verify that the data has not been tampered with during transmission. Because it ensures both confidentiality (by encrypting the data) and integrity (by checking if the data was changed), GCM is widely used in secure communication like HTTPS and VPNs.</details>

12. Which mode involves using a feedback mechanism where the output of the block cipher is used to generate a keystream that is then XORed with plaintext to produce ciphertext?
     1. Output feedback (OFB)
     2. Cipher Feedback (CFB)
     3. Counter (CTR)
     4. Cipher Block Chaining (CBC)
<details closed>
<summary>Answer</summary>
OFB mode uses a feedback mechanism where the output of the block cipher is not used to encrypt the plaintext directly. Instead, the cipher encrypts an initialization value (IV), and the result becomes part of a keystream. This keystream is then XORed with the plaintext to create the ciphertext. Each new keystream block is generated by encrypting the previous output, not the plaintext or ciphertext, making OFB behave like a stream cipher. It’s useful when you need to encrypt data in small chunks and want to avoid error propagation.</details>

13. Which mode involves encrypting a combination of a nonce and an incrementing counter in order to generate a keystream; then using this keystream to be XORed with plaintext to produce ciphertext?
     1. Galois/ Counter Mode (GCM)
     2. Counter (CTR)
     3. Cipher Block Chaining (CBC)
     4. Output feedback (OFB)
<details closed>
<summary>Answer</summary>
CTR mode works by combining a nonce (a number used once) with an incrementing counter to create a unique value for each block. This value is then encrypted using the block cipher to produce a keystream block. That keystream block is then XORed with the plaintext to generate the ciphertext. Because each counter value is unique, even identical plaintext blocks produce different ciphertext. CTR mode is fast, allows parallel processing, and is commonly used when high performance and security are both important.</details>

14. What is a keystream?
     1. A keystream is a fixed sequence of bits used as a static key for encryption.
     2. A keystream is a sequence of random values that replaces the encryption key in the cipher algorithm.
     3. A keystream is a sequence of encrypted data blocks used to produce plaintext from ciphertext.
     4.  A keystream is a sequence of pseudorandom bits generated using a block or stream cipher
<details closed>
<summary>Answer</summary>
A keystream is a sequence of pseudorandom bits or bytes that is used in certain encryption methods, especially stream ciphers and stream-like block cipher modes (like CTR, OFB, and CFB).</details>

15. Which block cipher modes of operation use a keystream? (Select all that Apply)
     1. Cipher Feedback (CFB)
     2. Cipher Block Chaining (CBC)
     3. Output feedback (OFB)
     4. Counter (CTR)
     5. Galois/ Counter Mode (GCM)
     6. Electronic Codebook (ECB)
<details closed>
<summary>Answer</summary>
CTR, OFB, CFB, and GCM generate a keystream and then XOR it with plaintext to produce ciphertext. This makes them behave like stream ciphers, allowing for efficient and flexible encryption of data of any size.</details>
