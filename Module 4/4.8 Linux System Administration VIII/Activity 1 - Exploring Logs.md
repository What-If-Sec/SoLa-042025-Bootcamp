## Activity Objectives

Students will learn to identify, access, and analyze various log files within an Ubuntu Virtual Machine (VM). By the end of this activity, students will be able to:

Understand the purpose and importance of different types of log files in system administration.Navigate the /var/log/ directory to locate common system, application, and security logs.Use appropriate commands to view and interpret log file contents.

## Activity Instructions

Complete this quiz by examining the log files within your VM's "/var/log/" directory and leveraging the resources available to you to understand the purpose of each log.

### Activity
1.	Where are log files stored in Linux?
    1.	/var
    2.	/etc
    3.	/var/log
    4.	t/tmp
<details closed>
<summary>Answer Key</summary>
/var/log
</details>

2.	Which log file contains system messages and information about the system's overall operation?
    1.	/var/log/daemon.log
    2.	/var/log/kern.log
    3.	/var/log/auth.log
    4.	/var/log/syslog
<details closed>
<summary>Answer Key</summary>
/var/log/syslog
</details>

3.	Which log file contains boot-related messages logged during system startup?
    1.	/var/log/cron/cron.log
    2.	/var/log/audit/audit.log
    3.	/var/log/boot.log
    4.	/var/log/mail.log
<details closed>
<summary>Answer Key</summary>
/var/log/boot.log
</details>

4.	Which log file contains messages from the kernel during system boots?
    1.	/var/log/kern.log
    2.	/var/log/syslog
    3.	var/log/messages
    4.	/var/log/dmesg
<details closed>
<summary>Answer Key</summary>
/var/log/dmesg
</details>

5.	Which log file, contains detailed information about package installations, removals, and upgrades?
    1.	/var/log/apt/term.log
    2.	/var/log/apt/apt.log
    3.	/var/log/apt/history.log
    4.	var/log/dpkg.log
<details closed>
<summary>Answer Key</summary>
/var/log/apt/history.log
</details>

6.	Which log file, captures terminal output during apt package management operations, providing detailed messages and information?
    1.	/var/log/dpkg.log
    2.	/var/log/apt/term.log
    3.	/var/log/apt/history.log
    4.	/var/log/apt/apt.log
<details closed>
<summary>Answer Key</summary>
/var/log/apt/term.log
</details>

7.	Which log file contains detailed logs of all audit events?
    1.	/var/log/daemon.log
    2.	/var/log/mail.log
    3.	/var/log/mail.err
    4.	/var/log/audit/audit.log
<details closed>
<summary>Answer Key</summary>
/var/log/audit/audit.log
</details>

8.	Which log file contains log messages from system daemons (background services)?
    1.	/var/log/apache2/access.log
    2.	/var/log/daemon.log
    3.	/var/log/apache2/error.log
    4.	/var/log/auth.log
<details closed>
<summary>Answer Key</summary>
/var/log/daemon.log
</details>
