## Activity Objectives

Students will practice configuring Thunderbird with OpenPGP to generate key pairs, exchange public keys, and send signed and encrypted emails to classmates. This activity will help them understand the fundamentals of secure communication, key management, and the importance of encryption in protecting sensitive information.

By the end of this activity, students will be able to:
- Install and configure Thunderbird as an email client on Ubuntu.
- Generate OpenPGP key pairs and link them to an email account.
- Export, share, and import public keys for secure communication.
- Send and receive signed and encrypted email messages using OpenPGP.
- Explain the role of private keys, public keys, and digital signatures in email security.
- Reflect on real-world applications of encrypted email in cybersecurity.

## Activity Instructions

Follow the instructions below.
1. On your Ubuntu VM, open a terminal and run `sudo apt update && sudo apt install thunderbird -y` to install Thunderbird.
2. Launch Thunderbird from the Applications menu (or by typing `thunderbird &`).
3. Add your existing email account (Gmail, Yahoo, Outlook, etc.). Thunderbird will auto-detect settings; if using Gmail/Outlook with 2FA, you may need to generate an app password.
4. In Thunderbird, go to Account Settings for your email. Under End-to-End Encryption, click `Add Key → Generate a new OpenPGP key`.
5. Accept the defaults (3072/4096-bit RSA), then wait for the keys to generate and confirm it is now linked to your account.
6. Next, export your public key. Still under End-to-End Encryption, click `More → Manage Keys`, select your key, choose Export Public Key(s) Only, and save the file (e.g., studentname_pubkey.asc).
7. Send this file to your partner by email. When you receive your partner’s .asc file, save it.
8. In Thunderbird go to Manage Keys again and choose Import. After importing, mark the key as Accepted so you can encrypt messages to them.
9. Compose a new email to your partner. In the message window, enable both the padlock (Encrypt) and the pen (Sign). Write a short message and send it.
10. When you receive your partner’s reply, Thunderbird will automatically decrypt it with your private key and show you whether the digital signature is valid.
11. Finally, reflect: What extra steps did you have to take compared to sending a normal email? Why does control of private keys matter? How could encrypted email be useful in the real world?
12. Submit your reflection.
