#3 Activity Objective:

Students will utilize Meterpreter to successfully achieve privilege escalation and establish persistence on an Ubuntu Server. 

This activity aims to enhance their understanding of post-exploitation techniques, enabling them to identify vulnerabilities, leverage existing permissions for elevated access, and implement mechanisms to maintain access to a compromised system. Through this exercise, students will gain practical experience in simulating real-world penetration testing scenarios while emphasizing the importance of ethical considerations in cybersecurity.



## Activity Instructions:

#### For Windows & Mac Intel Chip Users

In this activity students will do the following:
1. Identify a suitable process to migrate to by running the ps command within your meterpreter shell.
2. Rename the shell.elf file to obfuscate the malware. Rename it to something like CleanUp.elf, StartUp.elf, etc.
3. Select a target process that runs under root privileges and is less likely to raise alarms like bash or sshd.
4. Use the `migrate <pid>` command where `<pid>` is the process ID of the target process you wish to migrate to.
5. With root privileges, create a cronjob to execute the elf program daily at 7:30pm. 

> Tips for using Meterpreter Migrate Command:
>
> 1. Avoid migrating to processes that are likely to be monitored or are critical to the system’s operation.
> 2. Some processes may crash during migration. If you encounter issues, try migrating to a different process.
> 3. If you're attempting to escalate privileges, ensure the target process runs under a user with higher permissions.



#### For  Mac ARM Chip Users:

Students who are hosting their virtual security testing lab using a Mac M1, M2, etc. device will have to use various manual techniques and strategies to achieve privilege escalation, due to the fact that many meterpreter commands are not supported by aarch64/ Linux.

For this reason, in this activity students will complete the following:
1. Due to the fact that, an attacker can not use the built-in meterpeter commands to be able to achieve privilege escalation on an aarch64 Linux machine. As the pentester, prior to the pentest kick-off you requested permission from the client to be able attempt to phish for the IT admin's credentials. With approval, using spear-phishing you are able to successfully capture the admin's credentials to the web server.
2. With the admin's credentials, once the malware is executed creating a reverse shell, you use the shell command to open a bash shell on the victim's PC.
3. Confirm that you have created a bash shell, by entering the pwd command.
4. Within the bash shell, execute `echo "CapturedAdminPassword" | sudo -S bash -c 'echo "30 19 * * * root /root/to/malware.elf" >> /etc/crontab'`. If the sudo user's password contains special characters like "$" an escape character may be needed in order for echo to work. (For example: If the admin password is Let$GoTrojans, to echo this password to be used with sudo you would execute `echo "Let\$GoTrojans" | sudo -S ...`).
5. The reverse shell is now scheduled to be executed with root permissions every day at 7:30pm.
