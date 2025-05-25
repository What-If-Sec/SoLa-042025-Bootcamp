## Activity Objectives

Students will learn how to provision user accounts within a Linux environment using the useradd, passwd, groupadd, and usermod commands, gaining hands-on experience in managing user authentication, group membership, and user account configurations.

Through this activity students will gain:

1. Understanding the role of user accounts and groups in Linux systems.
2. Proficiency in creating and modifying user accounts and groups.
3. Familiarity with password management and security best practices.
4. Ability to assign appropriate permissions and access levels to users and groups.
5. Skills in troubleshooting common user account-related issues.

## Activity Instructions

This activity will provide students with practical exercises to reinforce their understanding of user account management in Linux environments. Through a series of guided tasks, students will learn how to create new user accounts, assign passwords, manage group memberships, and modify user attributes using the command-line interface.

1. Add directories named "Desktop", "Documents", "Downloads", and "Media" to the /etc/skel directory using the mkdir command.
<details closed>
<summary>Answer Key</summary>
  <code>sudo mkdir /etc/skel/Desktop /etc/skel/Documents /etc/skel/Downloads /etc/skel/Media</code>
</details>

2. Create an account for yourself, Rosie, and Virgil using the useradd command.
<details closed>
<summary>Answer Key</summary>
  <code>sudo useradd -m rosie</code>, <code>sudo useradd -m virgil</code>, <code>sudo useradd -m [your-username]</code>
</details>

3. Use the id command to verify that each user was successfully created.
<details closed>
<summary>Answer Key</summary>
  <code>id rosie virgil [your-username]</code>
</details>

4.Create a password for Rosie and Virgil using the passwd command. Rosie's password should be "123456" and Virgil's password should be "welcome", and you can come up with a password for your account.
<details closed>
<summary>Answer Key</summary>
  <code>sudo passwd rosie</code>, <code>sudo passwd virgil</code>, <code>sudo passwd [your-username]</code>
</details>

5. Verify that your, Rosie, and Virigl's user accounts were created correctly through grepping the /etc/passwd file.
<details closed>
<summary>Answer Key</summary>
  <code>grep -E 'your-username|rosie|virgil' /etc/passwd</code>
</details>

6. Create the general, developer, and marketing group using the groupadd command.
<details closed>
<summary>Answer Key</summary>
  <code>sudo groupadd general developer marketing</code>
</details>

7. Verify that the general, developer, and marketing groups were created through grepping the /etc/group file.
<details closed>
<summary>Answer Key</summary>
  <code>grep -E 'general|developer|marketing' /etc/group</code>
</details>

8. Add yourself, Rosie, and Virgil to the general group, using the  usermod command to append each user to the group.
<details closed>
<summary>Answer Key</summary>
  <code>sudo usermod -aG general [your-username]</code>, <code>sudo usermod -aG general rosie </code>, <code>sudo usermod -aG general virgil</code>
</details>
   
9. Add Rosie to the developer group using the usermod command to append the user to the group.
<details closed>
<summary>Answer Key</summary>
  <code>sudo usermod -aG developer rosie </code>
</details>

10. Add Virgil to the Marketing group using the usermod command to append the user to the group.
<details closed>
<summary>Answer Key</summary>
  <code>sudo usermod -aG marketing virgil </code>
</details>

11.  Add yourself to the sudo group to gain sudo access using the usermod command to append your user to the group.
Add Virgil to the Marketing group using the usermod command to append the user to the group.
<details closed>
<summary>Answer Key</summary>
  <code>sudo usermod -aG sudo [your-username][</code>
</details>

12. Verify that yourself, Rosie, and Virgil belong to the correct groups using the groups command. You should now have 4 user accounts on your VM now: admin, Rosie, Virgil, and your own account, as well as 3 secondary groups: general, developer, and marketing.
   <details closed>
<summary>Answer Key</summary>
  <code>groups <your-username> rosie virgil</code>
</details>


