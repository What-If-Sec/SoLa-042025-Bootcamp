## Activity Objective 

Students will explore and apply public key cryptography using GPG (GNU Privacy Guard) through a series of practical tasks. By completing this activity, students will:
1. Generate Key Pairs: Create a personal GPG key pair (public and private keys) for use in encryption and decryption operations.
2. Encrypt and Decrypt Messages: Encrypt a message using a classmate’s public key and then decrypt it using their private key to practice secure communication.
3. Exchange Keys and Messages: Import and export public keys with classmate

## Activity Instructions

> Note: When you're ready to share your public key with a classmate for this activity, the easiest method is to upload the public key file to a cloud storage service such as Google Drive, Dropbox, or OneDrive. Once uploaded, make sure the sharing settings allow the recipient to view or download the file by setting the link to “anyone with the link can view.”
>
> You can then copy and share that link through platforms like Slack or Discord. Another option is to upload the public key file directly into the chat on Discord, Slack, etc. by dragging and dropping it.
>
> Remember, you should only share your public key and never your private key.

Follow the instructions below:
1. Ensure that GPG is installed on your Ubunutu VM.
<details closed> <summary>Answer</summary> <code>gpg --version</code><br><br> <p>If GPG is not installed, install it using:</p> <code>sudo apt update && sudo apt install gnupg -y</code> </details>

2. Generate a RSA 2048 bit public-private key pair using GPG that does not expire, using your name and email address as the user ID to identify your key. (Make sure to set a strong passphrase).
<details closed> <summary>Answer</summary> <code>gpg --full-generate-key</code> </details>

3. Verify that your keys were generated.
<details closed> <summary>Answer</summary> <code>gpg --list-keys</code><br><br> <p>This will show your public key(s) in the keyring.</p> </details>

4. Export your public key.
<details closed> <summary>Answer</summary> <code>gpg --armor --output my_public_key.gpg --export your_email@example.com</code><br><br> <p>This creates a shareable ASCII version of your public key.</p> </details>

5. Verify the contents of the exported file to ensure it contains your public key.
<details closed> <summary>Answer</summary> <code>cat my_public_key.gpg</code><br><br> <p>You should see a block starting with:</p> <code>-----BEGIN PGP PUBLIC KEY BLOCK-----</code> </details>

6. Upload your public key file to the live channel within Slack, Discord, etc. (Upload the file, not the contents of your public key file).
<details closed> <summary>Answer</summary> <p>In your class Slack, Discord, or other live channel:</p> <ul> <li>Upload the file <code>my_public_key.gpg</code></li> <li><strong>Do not paste the contents</strong>; upload the file directly</li> </ul> </details>

7. Within the Slack , Discord, etc. live channel, select 1-2 students (whom have posted their public key file) and import their public key into your keyring. (You will need to be logged into Slack, Discord, etc. within your VM).
<details closed> <summary>Answer</summary> <code>gpg --import classmate_public_key.gpg</code><br><br> <p>This adds their key to your keyring so you can encrypt messages to them.</p> </details>

8. Create two text files containing a message for each student, include your name at the end.
<details closed> <summary>Answer</summary> <code>echo "Hey [Name], great job! – Your Name" > message_to_classmate.txt</code><br><br> <p>Repeat this for one or two classmates.</p> </details>

9. Encrypt your message using the desired recipient's public key, and DM them the message.
<details closed> <summary>Answer</summary> <code>gpg --output message_to_classmate.txt.enc --encrypt -r classmate_email@example.com message_to_classmate.txt</code><br><br> <p>This creates an encrypted file only the recipient can open.</p> </details>

10. When you receive an encrypted message from your classmate, decrypt it using your private key and submit their messages.
<details closed> <summary>Answer</summary> <code>gpg --output decrypted_message.txt --decrypt received_message.enc</code><br><br> <p>Then read the message:</p> <code>cat decrypted_message.txt</code> </details>


GPG Commands
```bash
# Remember .ext represents the file extension and is a placeholder value

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
```
