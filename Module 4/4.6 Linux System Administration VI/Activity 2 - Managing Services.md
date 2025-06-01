## Activity Objectives

Students will gain an understanding of the systemd system and service manager and learn how to use the systemctl utility to effectively manage services on their virtual machine. By the end of this activity, students will be able to:

Identify the purpose and functionality of systemd and its role in service management.Use the systemctl command to start, stop, restart, enable, and disable services.Check the status of services and analyze system logs to troubleshoot service-related issues.Differentiate between active, inactive, enabled, and disabled service states.Perform essential tasks such as starting, stopping, enabling, disabling, and checking the status of services using systemctl commands.Understand the purpose of service accounts in Linux, including their role in isolating and securing system services.Create and manage service accounts, assign appropriate permissions, and link them to specific services.

## Activity Scenario

Your system have old services running that are no longer used. Because services can be exploited, we want to run as few of them as possible. The services we should check for are:

- File Transfer Protocol (FTP): This file sharing service is outdated, insecure, and easily exploitable. For this reason the Secure File Transfer Protocol (SFTP) is used instead, as cybercriminals often use it to upload malicious files, so we need it removed immediately. Identified as vsftpd.service in Linux and uses a service account named ftp.

- Telnet:  Telnet stands for Telecommunications Network and can be used to connect to another computer remotely across a network, providing you shell access. Telnet is notoriously insecure and easily hacked as all communications between your workstation and that telnet service is not encrypted. Remove it so no one can log in to this machine remotely. Telnet is commonly managed by the Extended Internet Services Daemon (xinetd.service) used for managing Linux connections like the one created when using telnet. Xinetd is generally ran as the root user for administrative purposes and relies on system configurations for access control and service execution; as a result, the service does not have a dedicated service account.

- Samba:  Samba also known as SMB, is a protocol that allows user to observe, download, and store files remotely. It is commonly used for file sharing among Windows computers, but it can be used on Linux machines as well. SMB can be useful, however often it is not secured or hardened, and attacker will frequently target SMB services for this reason. Identified as smbd in Linux and utilizes a service account named "nobody".

## Activity Instructions

This activity will provide students with practical experience in managing services that are currently running in the background on a Linux system. Through a series of guided tasks, students will learn how to identify services that are currently running, stop them, and uninstall them.
1. Download the script provided [here](https://drive.google.com/file/d/10blqzUTEvXAzHmt1IEWHyVooVjECQz80/view) and set the execute permission for your user using the chmod command.
<details closed> 
   <summary>Answer Key</summary>
   <code>sudo chmod u+x /pathtoFile/4.6.2-ActivitySetupScript.sh</code>
</details>

2. Execute the activity setup script using the bash command.
<details closed> 
   <summary>Answer Key</summary>
   <code>sudo bash /pathtoFile/4.6.2-ActivitySetupScript.sh</code>
</details>

3. List all running services and verify that FTP, SMB, and Telnet are running using systemctl.  
<details closed> 
   <summary>Answer Key</summary>
   <code>systemctl  -t service --all --state=running| grep -E 'vsftpd|xinetd|smbd' </code>
</details>

4. Identify the SMB, FTP, and Telnet services in the list to verify that they are running using systemctl.
<details closed> 
   <summary>Answer Key</summary>
   <code>systemctl status smbd.service vsftpd.service xinetd.service </code>
</details>

5.  Stop each service from running using systemctl. 
<details closed> 
   <summary>Answer Key</summary>
   <code>sudo systemctl stop smbd.service vsftpd.service xinetd.service </code>
</details>

6. Verify that each service has been stopped from running using systemctl.
<details closed> 
   <summary>Answer Key</summary>
   <code>systemctl status smbd.service vsftpd.service xinetd.service </code>
</details>

7. Prevent each service from starting automatically when the machine starts using systemctl.
<details closed> 
   <summary>Answer Key</summary>
   <code>sudo systemctl disable smbd.service vsftpd.service xinetd.service </code>
</details>

8.  Verify if service accounts exist for each of the services using the getent command to query the passwd database for the service account's name. 
<details closed> 
   <summary>Answer Key</summary>
   <code>sudo apt purge -y smbd vsftpd telnetd</code>
</details>

9.Verify if a group exists for each service account by grepping the /etc/group file.
<details closed> 
   <summary>Answer Key</summary>
   <code>grep -E 'telnet|ftp|samba' /etc/group</code>
</details>

10. Remove the service and any of its configuration files from the system using the apt purge command.
<details closed> 
   <summary>Answer Key</summary>
   <code>sudo apt purge -y smbd vsftpd telnetd</code>
</details>

11. Verify if the service accounts and their groups were removed. If not, use the deluser to remove the service account or the delgroup command to delete the group.
<details closed> 
   <summary>Answer Key</summary>
   The <code>app purge</code> command previously executed removed the assoicated service account for the FTP service. However, if you execute apt remove you will have to remove the service account by running <code>sudo deluser --remove-all-files [service_acct_name]</code>. To delete the SambaShare group execute: <code>sudo delgroup sambashare</code>
</details>

12. Install tripwire using sudo apt install tripwire. Do not configure Postfix or create/use a site key passphrase during installation.
<details closed> 
   <summary>Answer Key</summary>
   <code>sudo apt install tripwire</code>
</details>

13. Now that tripwire is installed, create a service account and an associated group for tripwire using the useradd command.
<details closed> 
   <summary>Answer Key</summary>
   <code>sudo useradd --system --group --disabled-login --no-create-home tripwire</code>
</details>

