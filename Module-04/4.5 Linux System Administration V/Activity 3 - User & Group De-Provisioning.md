## Activity Objectives

Students will learn how to de-provision user accounts within a Linux environment, ensuring effective user account management and security.

Through this exercise students will gain:

1. Understanding the importance of de-provisioning user accounts in maintaining system security.
2. Proficiency in using the usermod, deluser, and delgroup commands to deactivate, delete, and clean up user accounts and associated resources.
3. Awareness of best practices for securely de-provisioning user accounts and managing residual data.
4. Skills in handling user account deactivation and deletion requests in compliance with organizational policies and regulations.

## Activity Instructions

This activity will provide students with practical exercises to reinforce their understanding of user account management in Linux environments. Through a series of guided tasks, students will learn how to lock a user account to prevent the user from accessing system resources, deleting the user and their data from the system, as well as deleting groups from the system using the command-line interface.

1. Lock Virgil's user account using the usermod command.
<details closed>
<summary>Answer Key</summary>
  <code>sudo usermod -L virgil</code>
</details>

2. Remove Virgil from any secondary group he may belong to by using the usermod command.
<details closed>
<summary>Answer Key</summary>
  <code>sudo usermod -G "" virgil</code>
</details>

3. Verify that Virgil only belongs to his own primary group using the groups command.
<details closed>
<summary>Answer Key</summary>
  <code>groups virgil</code>
</details>

4. Delete Virgil's user account, home directory, and data using the deluser command.
<details closed>
<summary>Answer Key</summary>
  <code>sudo deluser --remove-home virgil</code>
</details>

5. Verify that Virgil's home directory has been removed from your system using the ls command on the /home directory.
<details closed>
<summary>Answer Key</summary>
  <code>ls /home</code>
</details>

6. Delete the marketing group through using the delgroup command.
<details closed>
<summary>Answer Key</summary>
  <code>sudo delgroup marketing</code>
</details>

7. Delete Virgil's primary group from your system using the delgroup command.
<details closed>
<summary>Answer Key</summary>
  <code>sudo delgroup marketing</code>
</details>

8. Verify that Virgil's primary group and the marketing group were removed through grepping the /etc/group file. 
<details closed>
<summary>Answer Key</summary>
  <code>grep -e virgil -e marketing /etc/group</code>, since the commmand did not return anything the account and groups were removed.
</details>
