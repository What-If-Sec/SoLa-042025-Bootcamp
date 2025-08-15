## Activity Objective 

Students will use GPG (GNU Privacy Guard) to create and verify digital signatures for ensuring the authenticity and integrity of digital messages. By the end of the activity, students will be able to:
1. Understand Digital Signatures: Explain the principles and importance of digital signatures in verifying message authenticity and integrity, as well as ensuring non-repudiation.
2. Generate GPG Keys: Create a personal GPG key pair (public and private keys) for signing and verifying messages.
3. Sign Messages: Use GPG to generate a digital signature for a given message.
4. Verify Signatures: Verify the authenticity and integrity of messages received from peers using their GPG signatures.
5. Demonstrate and Explain: Present and explain the process of signing and verifying messages using GPG, including how these practices contribute to secure digital communication.



## Activity Instructions

Follow the instructions below:
1. Select two different students whom have posted their public keys to the live channel.

2. Create two different messages for each student, including your name at the end.
<details closed> <summary>Answer</summary> <p>Choose two classmates who have already posted their public key files in the live channel (Slack, Discord, etc.).</p> <p>Then create one personalized message for each of them and include your name.</p> <code> echo "Hey [Student1], keep up the great work! - Your Name" > message_to_student1.txt echo "Hi [Student2], you're doing awesome! - Your Name" > message_to_student2.txt </code> </details>

3. Create a digital signature for each of the plaintext files you created.
<details closed> <summary>Answer</summary> <p>This command will generate a <code>.sig</code> file that can be used to verify the integrity and authenticity of the message file.</p> <code> gpg --detach-sign message_to_student1.txt gpg --detach-sign message_to_student2.txt </code> </details>

4. Encrypt each file using GPG, and DM the encrypted message (.enc) and digital signature (.sig)  files to the appropriate recipient via Slack, Discord, etc.
<details closed> <summary>Answer</summary> <p>Encrypt each message using the corresponding student’s public key.</p> <code> gpg --output message_to_student1.txt.enc --encrypt -r student1_email@example.com message_to_student1.txt gpg --output message_to_student2.txt.enc --encrypt -r student2_email@example.com message_to_student2.txt </code> </details>

5. When you receive an encrypted message along with the digital signature, begin by importing the student's public key (posted to the live channel from the previous activity) to your keyring and then decrypt their message.
<details closed> <summary>Answer</summary> <p>Import your peers public key using:</p> <code> gpg --import classmate_public_key.gpg </code> <br> <p>Use your private key to decrypt the message file you received.</p> <code> gpg --output decrypted_message.txt --decrypt received_message.enc </code>  </details>

6. Once decrypted verify the signature of the file, and if the signature matches submit a screenshot showing this as well as each file.
<details closed> <summary>Answer</summary> <p>Use the sender’s signature file to verify the authenticity and integrity of the decrypted message.</p> <code> gpg --verify received_message.sig decrypted_message.txt </code> </details>

> Note: Within this activity we created a detached digital signature (created with gpg --detach-sign) which signs the plaintext/original file, not the encrypted one. This means that in order to verify the signature, we need to decrypt the file, and then verify the signature of the plaintext file. 

### GPG Commands
``` bash
# Remember .ext represents the file extension

# Create public-private key pair
gpg --full-generate-key

# List keys in keyring
gpg --list-keys

# Export your public key
gpg --armor --output [public_key_name].gpg --export [insert-your-email]

# Import someone else's public key into your keyring
gpg --import [public_key_name].gpg

# Encrypting a message with a recipient's public key using GPG
gpg --output [encrypted_filename].ext.enc --encrypt -r [recipient_email_address] [plaintext_filename].ext

# Decrypting a message with your private key using GPG
gpg --output [decrypted_filename].ext --decrypt [encrypted_filename].ext.enc

# Creating a digital signature separate from the original document
gpg --detach-sign [filename].ext

# Verify the digital signature of a file
gpg --verify [filename].sig [filename].ext
```
