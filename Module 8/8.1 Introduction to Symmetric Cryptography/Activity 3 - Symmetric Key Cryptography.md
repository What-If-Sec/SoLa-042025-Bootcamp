## Activity Objectives

Students will gain practical experience in using OpenSSL for cryptographic operations by creating a symmetric key and initialization vector (IV), encrypting a message using these cryptographic elements, and securely sharing the encrypted message with a classmate. Your classmate will then use the provided key and IV to decrypt the ciphertext and retrieve the original plaintext. This activity aims to:
1. Understand Key and IV Generation: Learn how to generate a symmetric key and an IV using OpenSSL.
2. Implement Encryption: Apply the key and IV to encrypt a plaintext message using OpenSSL commands.
3. Apply Decryption: Use the provided key and IV to decrypt the received ciphertext and verify the correctness of the decrypted message.
4. Secure Communication: Practice securely sharing the encrypted message and the cryptographic elements (key and IV) with a classmate.
5. Enhance Cryptographic Skills: Develop practical skills in handling cryptographic operations and using OpenSSL for encryption and decryption tasks.



## Activity Instructions

Follow the instructions below:
1. Verify you have OpenSSL downloaded to your Ubuntu VM.
<details closed>
<summary>Answer</summary>
<code> openssl version</code> <br><br><p>If OpenSSL is not installed, you can install it with:</p><code>sudo apt update
sudo apt install openssl
</code></details>

2. Create a key and IV using the syntax below.
<details closed>
<summary>Answer</summary>
<code>openssl enc -pbkdf2 -nosalt -aes-256-cbc -k MyStrongPassword123 -P > key_and_iv.txt
</code></details>

3. Create a text file containing a message for a classmate (include your name in the message).
<details closed>
<summary>Answer</summary>
<code>echo "Hi [Classmate's Name], this is [Your Name]! Have a great day!" > message.txt
</code></details>

4. Use the generated key and IV to encrypt a message.
<details closed>
<summary>Answer</summary>
<p>Substitute with your actual key and IV, copying and pasting from the key_and_iv.txt file</p>
<code>openssl enc -pbkdf2 -nosalt -aes-256-cbc -in message.txt -out message.txt.enc -K ACBD18DB4CC2F85CEDEF654FCCC4A4D8ACBD18DB4CC2F85CEDEF654FCCC4A4D8 -iv 1234567890ABCDEF1234567890ABCDEF
</code></details>

5. Verify that your message can be decrypted using your key and IV.
<details closed>
<summary>Answer</summary>
<p>To decrypt the message run:</p><code>openssl enc -d -pbkdf2 -nosalt -aes-256-cbc -in message.txt.enc -out decrypted_message.txt -K ACBD18DB4CC2F85CEDEF654FCCC4A4D8ACBD18DB4CC2F85CEDEF654FCCC4A4D8 -iv 1234567890ABCDEF1234567890ABCDEF
</code><br><p>Verify that your original message can get decrypted.</p>
<code>cat decrypted_message.txt</code></details>

6. Submit your encrypted message (file ending in ".txt.enc") and the file containing your key and IV.





#### OpenSSL Commands:
``` bash
# Remember .ext represents the file extension and is a placeholder value

# Key and IV generation
openssl enc -pbkdf2 -nosalt -aes-256-cbc -k [insert-a-password] -P > [key_and_iv_output-filename]

# Encryption with OpenSSL
openssl enc -pbkdf2 -nosalt -aes-256-cbc -in [input-filename].ext -out [encrypted-filename].ext.enc -K insert-encryption-key -iv insert-IV

# Decryption with OpenSSL
openssl enc -d -pbkdf2 -nosalt -aes-256-cbc -in [encrypted-filename].ext.enc -out [insert-output-filename].ext -K [insert-encryption-key] -iv [insert-IV]
```

 
