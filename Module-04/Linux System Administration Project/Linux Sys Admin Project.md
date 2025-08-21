# Welcome, Future Sys Admins!

In this project, you will take on the role of a Linux System Administrator responsible for deploying, securing, and maintaining a Linux environment. Your mission is to ensure the system is properly configured, hardened, and operational—just as you would in a real-world IT environment.

Throughout this project, you will:
1. Install and configure a Linux system from scratch.
2. Provision user accounts following best practices, including enforcing least privilege and secure authentication policies.
3. Manage passwords and groups to control access and enhance security.
4. Harden the system by applying security best practices, disabling unnecessary services, and implementing firewall rules.
5. Implement log management and monitoring to detect anomalies, track system activity, and maintain compliance.
6. Patch and maintain the system to keep it secure and up to date.

As you work through these tasks, think like a professional system administrator—focus on security, efficiency, and reliability. By the end of this project, you'll have hands-on experience in essential sysadmin duties that are critical for IT and cybersecurity roles.

## Introduction

This project will demonstrate a wide range of Linux system administration skills and provide practical experience in managing a complex server environment. Through this project students will:
- Implement user and group management strategies, creating distinct accounts for departments such as Sales, Engineering, and HR.
- Implement a strong password policy to reduce the effectiveness of brute-force attacks against an user's account.
- Configure permissions and access controls using ACLs, ensuring secure data access tailored to departmental needs.
- Implement log rotation and retention policies, optimizing storage usage and compliance with data retention regulations.
- Install and configure services like Git utilizing systemctl for service managementDevelop comprehensive documentation covering system configurations, user guides, and troubleshooting procedures.
- Generate reports and audits using providing insights into performance metrics and compliance status

#### For this project students will create a new Ubuntu Server VM. 
- Windows & Mac (Intel Chip): https://ubuntu.com/download/server#manual-install
- Mac (Arm Chip): https://ubuntu.com/download/server/arm

> Use the lecture slides, videos, supplemental readings, and the internet as a whole as resource!!!
> However, remember that learning how and what to google to solve each task is an important skill to have, so don't use AI tools like chatgpt to cheat yourself from gaining this skill.

## Prerequisites:

Task: Complete the following prior to starting your project
1. Deploy a Ubuntu Server VM within VMware or VirtualBox, and configure the username of your Ubuntu Server VM to be sysadmin.
2. Install auditd using apt

## Part 1: Log Management and Monitoring

#### Task: As the sysadmin user integrate log management with service monitoring to provide a holistic view of the system's health through setting up alerts.
1. Default Log Rotation and Retention: Configure ```logrotate``` to manage log file sizes and retention periods. Ensure by default logs are (1) rotate every 4 weeks of backlogs,(2) create new empty log files after rotating old ones, (3) do not rotate empty logs, and (4) compress log files.
2. Service Log Rotation and Retention: Configure ```logrotate``` to mange log file sizes and retention periods for the /var/log/syslog named syslog, ```/var/log/cron.log``` named cron, ```/var/log/auth.log``` named auth. Log files should be configured (1) daily, (2) rotate every 30 days, (3) compress, (4) delay compression, (5) don't rotate if log file is empty, (6) add the date to the end of the rotated file, and (7) create the log file to be owned by the root user and group as well as have read and write permissions for the user and read permissions for the group and read permissions for others.
3. Implement Log Analysis: Open another terminal and use  ```journalctl``` to analyze log data in real-time as you complete your project. (As you configure your system check journalctl for any error messages)
4. Monitor User Management Events: Use ```auditd``` to create multiple audit rules named "User_Management" to monitor for the following security-related events:  (1) execution of the ```useradd``` command, (2) execution of the ```usermod``` command, and (3) execution of the ```userdel``` command. (Hint: Create the audit rules to monitor for the execution of each of the user management command files located in the/usr/sbin/directory.)
5. Monitor Group Management Events: Use ```auditd``` to create multiple audit rules named "Group_Management" to monitor for: (1) the execution of the ```groupadd``` command, (2) execution of the ```groupdel``` command,  (3) execution of the ```groupmod``` command, and (4) write access and attribute changes to ```/etc/group```. (Hint: Create the audit rules to monitor for the execution of each of the group management command files located in the /usr/sbin/ directory.)
6. Monitor Log Events: Use ```auditd``` to create an audit rule named "Log_Management" to monitor write access to ```/var/log```
7. Monitor Security Events: Use ```auditd``` to create an audit rule named "Passwrd_Changes" to monitor write access and attribute changes to ```/etc/passwd``` and create an audit rule named "Shadow_Changes" to monitor read and write access as well as attribute changes to ```/etc/shadow```.
8. Monitor System Events: Use ```auditd``` to create an audit rule named "Monitor_Cron" to monitor the following system-related event: write changes to /etc/crontab for the sysadmin user and the root user.
9. Apply your changes by restarting the auditd service using ```systemctl```.
10. Document the Log Management Process: Provide detailed documentation on the process and key components of Log Management (including generation, collection, etc.) as well as the tools, utilities, and programs used to establish log rotation and management within a Linux environment including their configuration, and procedures for analysis and alerting. Furthermore, provide details about the importance and significance of creating audit rules to monitor for events like access to sensitive files and the execution of certain commands.

### Reflections
- What challenges did you encounter while configuring log rotation and audit rules?
- What different log monitoring tools exist?
- How do different log monitoring tools complement each other? 

## Part 2: Service and Process Management

#### Tasks: Install and configure a service, ensuring that best practices are followed.
1. Create a system-wide cronjob to update (apt update) and upgrade (apt upgrade) the system every Sunday at 12am.
2. Read: https://docs.github.com/en/get-started/start-your-journey/about-github-and-git
3. As the sysadmin user, install Git Services on your VM: Install git using ```sudo apt update && sudo apt install git```
4. Create a Service Account for Git:  This user will manage the repositories and SSH access
5. Configure Git Service: Set up a repository directory where your Git repos will be stored named /srv/git. Set the git service account as the owner of the directory /srv/git (Note: Typically you would configure SSH keys to authenticate the git user, however this is out of scope).
6. Configure SSH daemon to allow SSH access for the git user: sudo nano /etc/ssh/sshd_config. Add or modify the sshd_config file to match the settings below.
<pre>
SSH Configuration Settings

Match User git
    AllowUsers git
    PasswordAuthentication no
    PermitEmptyPasswords no
    AuthorizedKeysFile      %h/.ssh/authorized_keys
    PubkeyAuthentication yes
    PermitRootLogin no
</pre>
7. Restart the SSH service using systemctl and confirm that it is running.
8. Manage Service Dependencies and Startup Behavior: Use systemctl to enable Git service at startup.
9. Monitor and Control Processes: Use top and ps to monitor the user and group management tasks.
10. Document the Service and Process Management Procedures: Provide detailed documentation on service configuration, process monitoring, and troubleshooting steps. Moreover, provide details about why and how service accounts are used to manage access and ensure security.

### Reflections
- What security risks are you introducing by setting up Git as a service?
- How could process monitoring help in identifying potential issues?

## Part 3: Password, User, and Group Management

#### Tasks: Ensure that only authorized users have access to sudo, specific logs, services, etc. Configuring file and directory permissions using ACLs and group-based permissions.

1. Password Management: Create a password management policy through modifying the ```/etc/login.defs``` file and set: (1) the maximum number of days a password may be used to 90 days, (2) the minimum number of days allowed between password changes to 10 days, (3) the number of days warning given before a password expires to 7 days, (4) the number of  allowed login retries to 5, and (6) the login prompt timeout to 60 seconds.
2. Create and Manage User Accounts: As the sysadmin user create a user account for yourself, as well as user accounts: Alice, Bob, and Charles (4 in total). Each user account should have a home directory and a default shell, and only your user account (the account named after you) should have sudo access. (Remember: the -G option for the ```useradd``` command will add a user to the sudo group, and the -m option to create a home directory). Each user should also be created with a default password of "password123", and use the ```chage``` command to force password reset on first logon for each user.
3. Implement Group-Based Access Controls:  As the sysadmin user create groups for each department ( sales, engineering, and hr) as well as a group for cross-departmental projects ( general). Once done assign Alice to sales, Bob to engineering, Charles to hr , and assign everyone to the general group.
4. As the sysadmin user create a file titled "idME.sh" with the text below, and change the group ownership to general and the file permissions to read, write, and execute for the user, read and execute for the group, and no permissions for others. (Hint: use ```nano``` to create the file)
<pre>
#!/bin/bash
whoami
</pre>
5. Use the ```su``` command to change to each user and verify that they can execute the script.
6. Use the ```su``` command to change to your user account, and then add your user account to become a member of the engineering group as well.
7. Document the Password, User, and Group Management Policies: Provide detailed documentation of the password, user, and group management process, including command examples as well as best practices in regards to Linux identity and access management and how you implemented these practices.

### Reflections
- How did your user and group policy enhance security?
- What were some challenges in enforcing password management rules?

## Part 4: System Audit

#### Tasks: Analyze logs and identify

1. As the sysadmin user use  ```journalctl``` to create a report of the system log data generated from the start of your project till you completed your project. The name of the report should be [yourname-journal]
2. As the sysadmin user use ```ausearch``` to search for events associated with changes to the passwd, shadow, and crontab files as well user and group management rules.
3. Compare the data supplied by journalctl and ausearch. Are there similarities? Differences?
4. As the sysadmin user use ```aureport``` to generate reports based on account modifications and analyze the report to identify when user and group management activities occurred.
5. As the sysadmin user use ```aureport``` to generate a report for each of the audit rules you created  to further identify and correlate when user and group management activities occurred.
6. As the sysadmin user use ```aureport``` to generate a report based on the your log management rule, and analyze the report to identify what logs were written to and why while completing your project activities.
7. As the sysadmin user using ```cron``` schedule to generate each of the reports Password_Change, Shadow_Change, User_Management, etc. to be generated every week, every Monday, at 7am for the sysadmin user on the user's Desktop.
8. Document Audit Policies: Create comprehensive documentation detailing audit rule configurations, reports, and monitoring procedures as well as the similarities and differences when analyzing system vs audit logs.

### Reflections
- What insights did the audit reports reveal about system activity during your project?
- How could automation improve audit reporting efficiency?

## Documentation Guidelines

Comprehensive Documentation:
- Provide a single document covering all aspects of the project, including user and group management, log management, service/process management, and system auditing.
- Include command examples, configuration file snippets, screenshots, and best practices.
- Ensure the documentation is clear, concise, and well-organized, making it easy to understand and follow.

Your report should contain the following sections:
1. A Cover Page
2. A Table of ContentsA Section for each part (part 1, part 2, etc.) of the project.
3. Each section should include an overview of the activities performed, a detailed breakdown of how the project instructions were executed (including screenshots), and a conclusion on the implementation process reflecting on the challenges faced as well as how they were overcome. In addition to, the real-world applications of the skills learned.

An example report template can be found [here](https://docs.google.com/document/d/1Tru44N1B3-MG46xxi_9E13gqBHDxQ2i1/edit?usp=sharing&ouid=106132901521685891305&rtpof=true&sd=true).


## Final Deliverables
1. Configured Linux System: A fully set up and configured Linux system demonstrating user and group management, log management, and service/process management.
2. Documentation: Detailed documentation covering any reflections as well as the tasks and configurations implemented in the project including evidence (screenshots, sample log reports, audit logs, etc.) 



