## Activity Objectives
Students will learn the syntax and structure of cron job definitions, as well as how to configure and manage cron jobs to automate tasks. By the end of this activity, students will be able to schedule both user-level and system-level cron jobs within a Linux environment.  Specifically, students will:
1. Understand the difference between user-level and system-level cron jobs and their use cases.
1. Edit and create user-level cron jobs using the crontab command.
2. Configure system-level cron jobs by editing system-wide cron files (/etc/crontab, /etc/cron.d/, and /etc/cron.daily/).
3. Set up basic cron job schedules (e.g., hourly, daily, weekly) and understand cron syntax for scheduling.
4. Verify and troubleshoot cron jobs, ensuring they are scheduled and executed correctly.
5. Implement real-world use cases, such as automating log file management and system maintenance tasks using cron.

## Activity Instructions

This activity will provide students with practical experience in scheduling jobs via cron to be able to automate tasks. 
1. Download the script provided [here](https://drive.google.com/file/d/1ARtC9Q8uOd0t14xy3hyRziF6Vy0WAYJy/view) and set the execute permission for your user using the chmod command.
<details closed> 
   <summary>Answer Key</summary>
   <code>sudo chmod u+x /pathtoFile/4.6.3-ActivitySetupScript.sh</code>
</details>

2. Execute the activity setup script using the bash command.
<details closed> 
   <summary>Answer Key</summary>
   <code>sudo bash /pathtoFile/4.6.3-ActivitySetupScript.sh</code>
</details>

3. Create a directory in your Documents directory named "Ticket-Evidence".
<details closed> 
   <summary>Answer Key</summary>
   <code>mdkir ~/Documents/Ticket-Evidence</code>
</details>

4. Within the Ticket-Evidence directory create two more directories. One named "Customer-Ticket-Photos" and the other "Customer-Ticket-Comments".
<details closed> 
   <summary>Answer Key</summary>
   <code>mdkir ~/Documents/Ticket-Evidence/Customer-Ticket-Comments</code>, <code>mdkir ~/Documents/Ticket-Evidence/Customer-Ticket-Photos</code>
</details>

5. Create a user-level cron job that will move the jpeg files in your Downloads directory to the Customer-Ticket-Photos directory every day at 9:00pm.
<details closed> 
   <summary>Answer Key</summary>
   Execute <code>crontab -e</code>, and add the cron job entry: <code>0 21 * * * mv ~/Downloads/*.jpeg ~/Customer-Ticket-Photos/</code>
</details>

6. Verify that the cron job has been added corrretly.
<details closed> 
   <summary>Answer Key</summary>
   <code>crontab -l</code>
</details>

7. Create a user-level cron job that will move the text files in your Downloads directory to the Customer-Ticket-Comments directory every day at 9:00pm.
<details closed> 
   <summary>Answer Key</summary>
   Execute <code>crontab -e</code>, and add the cron job entry: <code>0 21 * * * mv ~/Downloads/*.txt ~/Customer-Ticket-Comments/</code>
</details>

8.Verify that the cron job has been added corrretly.
<details closed> 
   <summary>Answer Key</summary>
   <code>crontab -l</code>
</details>

9.   Use sudo to create a system-wide  cron job that will run apt update && apt upgrade every Sunday at 12am. 
<details closed> 
   <summary>Answer Key</summary>
   Execute <code>sudo crontab -e</code>, and add the cron job entry: <code>0 0 * * 0 apt update && apt upgrade -y</code>
</details>

10. Verify taht the system-level cron job has been added correctly.
<details closed> 
   <summary>Answer Key</summary>
   <code>sudo crontab -l</code>
</details>
