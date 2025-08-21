## Activity Objectives

Students will learn the basics of password cracking using John the Ripper, including installing and configuring the tool, understanding password hashes, and launching basic dictionary and brute-force attacks.

## Activity Scenario

Before leaving Virgil exploits a sudo vulnerability within your Linux system allowing him to gain root access. With root access, Virigil copies the /etc/shadow file to a temporary location and exfiltrates the file to their remote server for offline cracking, using tools like John the Ripper.

Using a wordlist attack, Virgil successfully cracks several password hashes, granting them full control over those user accounts on the system. Enabling Virgil to move laterally within the network or exfiltrate more sensitive data.

Rosie detects weird activity coming from their account and asks you to look into it. Through checking the system's logs you are able to identify anomalous activity, and as a result, you lock her account and decide to start enforcing a  system-wide password policy as well as password complexity requirements to limit the time Virgil can use her account as well as make it harder for him or any other attacker to crack passwords in the future.

## Activity Instructions

#### Complete the tasks below to simulate the cyber attack:

1. Create a copy of the /etc/shadow file using the cp command to the /tmp directory, and name the file "shadow_copy". (Hint: sudo cp /etc/shadow filePath/shadow_copy)
<details closed>
<summary>Answer Key</summary>
  <code>sudo cp /etc/shadow /tmp/shadow_copy</code>
</details>

2. Change the file and group ownership of the shadow_copy file  using the chown command to set the file to be owned by you and your primary group.
<details closed>
<summary>Answer Key</summary>
  <code>sudo chown rosie /tmp/shadow_copyy</code>
</details>

3. Run John the Ripper to crack Rosie's password demonstrating how easy it is to crack weak passwords. 
<details closed>
<summary>Answer Key</summary>
  <code>sudo john --format=crypt /tmp/shadow_copyy</code>
</details>

#### Complete the tasks below to simulate the defensive actions taken to lock Rosie's account and set stronger user account password policies:
1. To prevent Rosie's password from being brute-forced, enforce a stronger password policy on Rosie using the ```chage``` command, with the settings below.
2. Set the the minimum password age (the number of days that  Rosie must wait before being allowed to change their password again after setting a new one) to 0 days.
3. Set the the maximum password age (the number of days until the password expires) to 90 days.
4. Set the last password change date (the most recent date when the user changed the date) to today's date to force Rosie to reset her password.
5. Set the password expiration warning (the number of days before the maximum password age, in which the user will be alerted to change their password) to 14 days.
6. Set the password inactive period (the amount of time after a password has expired during which the user can still log in and change their password before their account is completely disabled) to  7 days.
7. Set the account expiration date to today's date so that Rosie's account will lock and force them to change their password on next log in.
<details closed>
<summary>Answer Key</summary>
  Execute: <code>sudo chage rosie</code> and follow the prompt, or <br>
 Execute: <code>sudo chage -m 0 -M 90 -d 0 -W 14 -I 7 -E $(date +%Y-%m-%d) rosie</code>
</details>

#### Complete the tasks below to simulate the defensive actions taken to enforce system-wide password complexity on your Ubuntu VM:

1. Modify the /etc/pam.d/common-password file using nano and add or modify the pam_pwquality.so line (password requisite pam_pwquality.so) to enforce the maximum number of password retires to 3.
<details closed>
<summary>Answer Key</summary>
  Execute: <code>sudo nano /etc/pam.d/common-password</code> and then locate and modify or add the line: <code>password requisite pam_pwquality.so retry=3
</code>
</details>

2. Modify the /etc/security/pwquality.conf file using nano and add or modify the file to contain the settings below.
3. Set the minimum password length to 8 characters.
4. Set the minimum number of uppercase letters to 1.
5. Set the minimum number of lowercase letters to 1.
6. Set the minimum number of special characters  to 1.
7. Set the minimum number of digits to 1.
8. Require at least 1 uppercase letter.Require at least 1 lowercase letter.
9. Require at least 1 digit.Require at least 1 non-alphabetic character.
10. Set the maximum number of repeatable characters to 2.
11. Set the maximum number of repeated characters from the same class to 3.
12. Enable dictionary checks.
<details closed>
<summary>Answer Key</summary>
  Execute: <code>sudo nano /etc/security/pwquality.conf</code> to modify the file and add or modify the following settings: 
<code>
# Set the minimum password length to 8 characters
minlen = 8
# Set the minimum number of uppercase letters to 1
ucredit = -1
# Set the minimum number of lowercase letters to 1
lcredit = -1
# Set the minimum number of special characters to 1
ocredit = -1
# Set the minimum number of digits to 1
dcredit = -1
# Require at least 1 uppercase letter, 1 lowercase letter, 1 digit, and 1 non-alphabetic character
minclass = 4
# Set the maximum number of repeatable characters to 2
maxrepeat = 2
# Set the maximum number of repeated characters from the same class to 3
maxclassrepeat = 3
# Enable dictionary checks
dictcheck = 1
</code>
</details>
