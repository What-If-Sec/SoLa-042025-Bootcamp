## Activity Objectives

Students will demonstrate their ability to automate backup processes by utilizing cron to schedule regular backups of their user’s home directory on Ubuntu Virtual Machines. This activity will emphasize the importance of automation in maintaining consistent data security and availability. 

By the end of the activity, students will be able to: 

Explain the purpose and benefits of using cron for task automation in system administration.Write and configure cron jobs to schedule periodic backups of the user’s home directory.Use the tar command to create backups within a scheduled cron job. Verify the successful execution of scheduled backups by reviewing log files and backup directories. Modify and troubleshoot cron schedules to adapt to changing backup requirements.

## Activity Instructions
 Students will learn to manually schedule and automate the creation of full backups of their Documents, Downloads, and Desktop directories using cron and the tar commands. You will also generate SHA-256 hashes for each full backup to ensure data integrity.  

> Remember: You can use tools like [crontab-generator](https://crontab-generator.org/) to help with creating and scheduling cron jobs.
1. If you have not done so, create a directory named Backups in the home directory to store your backup files.
<details closed> 
   <summary>Answer Key</summary>
   <code>mkdir ~/Backups</code>
</details>  

2. Open the cron table for editing.
<details closed> 
   <summary>Answer Key</summary>
   <code>crontab -e</code>
</details>  

3. Create a cron job to schedule a full backup of your user's Desktop, Downloads, & Documents directory to run every Friday at 11:59pm. (Hint: We can use command substitution to dynamically add YYYY-MM-DD to the file's name by placing the text with "$(date +\%F)" in the file's name").
<details closed> 
   <summary>Answer Key</summary>
   <code>59 23 * * 5 tar -czf ~/Backups/$(date +\%F)-backup.tar.gz ~/Desktop ~/Downloads ~/Documents</code>
</details>
   
4. Create a cron job to schedule a hash to be created of the archive file previously scheduled.
<details closed> 
   <summary>Answer Key</summary>
   <code>0 1 * * 6 sha256sum ~/Backups/$(date +\%F)-backup.tar.gz > ~/Backups/$(date +\%F)-backup.sha256</code>
</details>
   
5. Verify the cron jobs you created.
<details closed> 
   <summary>Answer Key</summary>
   <code>crontab -l</code>
</details>  
