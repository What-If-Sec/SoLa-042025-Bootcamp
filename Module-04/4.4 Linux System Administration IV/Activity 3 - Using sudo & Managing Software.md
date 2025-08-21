## Activity Objective:

In this activity, you will learn about the sudo command, the sudoers file, and the security implications of using elevated privileges on a Linux system to be able to manage installed software packages using apt. 

By the end of the activity, you will understand the following key concepts: 

1. The purpose and functionality of the sudo command, and how it allows users to execute commands with superuser privileges.
2.  How to safely access and modify the sudoers file using the visudo command to assign appropriate privileges to users and groups.
3. The potential security risks associated with improper use of sudo and the sudoers file, including the risks of granting excessive privileges and the importance of following the principle of least privilege.
4. Use sudo and apt to manage the software packages installed on a system.
5. The importance of maintaining an up-to-date software package list and why it's essential for system security and performance.

## Activity Instructions:

In the activity you will do the following to understand the proper process when managing software packages installed on a Linux system
1. Open your terminal and verify that your user has sudo privileges using ```sudo -v```. If an error/ warning message does not appear, your has sudo access.
2. List the sudo privileges your user currently has by using ```sudo -l```, and verify that your user has (ALL :ALL) ALL permissions set.
3. Use ```sudo visudo``` to access the suoders file, and verify that the root user as well as the sudo group has the ALL=(ALL :ALL) ALL permissions  set, then exit the sudoers file without saving.
4. List the software packages installed on your VM using ```apt list --installed```.
5. Update the package list on your VM by running ```sudo apt update```.
6. Remove outdated package files that can no longer be downloaded to free up your diskspace by using ```sudo apt autoclean```.
7. View the software packages that can be upgraded on your VM using ```apt list --upgradeable```.
8. Upgrade the packages on your VM by running ```sudo apt full-upgrade```.
9. Install the following software: auditd, net-tools, nmap, zenmap, john, and wireshark to your VM using ```sudo apt install <package_name>```.
<details closed>
<summary>Answer Key</summary>
  <code>sudo apt install -y auditd net-tools nmap zenmap john wireshark</code>
</details>

10. Update your VM's software package list to contain the software you just installed by running ```sudo apt update```.
11. View the details of the john software package using ```apt show <package_name>```.
<details closed>
<summary>Answer Key</summary>
  <code>apt show john</code>
</details>

12. Uninstall the following software: pandoc, tdb-tools, and samba-ad-provision  from your VM using ```sudo apt remove --purge <package_name>```.
<details closed>
<summary>Answer Key</summary>
  <code>sudo apt remove --purge pandoc tdb-tools samba-ad-provision</code>
</details>

13. Update your VM's software package list to remove the software you uninstalled from your VM by running ```sudo apt update```.
14. Within this activity you installed new software to your VM, and later uninstalled software you did not need. Why do you believe sudo was need to run certain apt commands, but not others?
<details closed>
<summary>Answer Key</summary>
Installing software requires modifying system files, downloading packages from repositories, and placing them in specific system directories (e.g., /usr, /bin, /etc), while removing software also involves modifying system files and directories to delete or remove certain packages. Like installation, these actions affect the system at a global level, which requires administrative privileges.
</details> 

15. Within this activity after installing/ uninstalling software, you also updated your software package list immediately after each time.  Why do you think it is considered best practice to update the software package list after installing or uninstalling packages?
<details closed>
<summary>Answer Key</summary>
When you install or uninstall software, the local package list on your system becomes out of sync with the repositories. Running sudo apt update updates the package cache to reflect the current state of the repositories, including any newly available packages or changes to existing ones. If you skip this step, you might face issues such as failing to find newly installed packages or outdated package information, leading to incomplete installations or failures when upgrading the system.
</details> 

16. Why do you believe an admin may want to run apt update  weekly or daily ?
<details closed>
<summary>Answer Key</summary>
Depending on the criticality of the system, for example, an IT system used by the US Military may have a daily maintenace cycle so that the admin is aware of the latest security patches and software updates. While for a hosptal, weekly updates may be better as it strikes a balance between system uptime and software stability, ensuring that the system remains secure without requiring constant monitoring.
</details> 

17. Submit your answers for question 14, 15, & 16 on EducateMe.

