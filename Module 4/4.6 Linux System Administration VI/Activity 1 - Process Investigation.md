## Activity Objectives

Upon completion of the activity, students will be able to:
1. Identify and analyze processes running on a Linux virtual machine (VM) to discern normal from potentially malicious activities.
2. Utilize system monitoring tools and commands to gather information about processes, including their resource usage and associated metadata.
3. Recognize common indicators of malicious processes, such as unusual behavior, suspicious file locations, or unauthorized access attempts.
4. Employ appropriate commands and techniques to terminate or suspend malicious processes without disrupting essential system functionality.
5. Demonstrate critical thinking and problem-solving skills by effectively assessing, mitigating, and preventing potential security threats posed by malicious processes on their Linux VM environment.

## Activity Instructions
This activity will provide students with practical experience in identifying processes that are currently running on a Linux system. Through a series of guided tasks, students will learn how to identify processes that are currently running, identify suspicious or malicious processes, and stop them from running.
1. Download the script provided [here](https://drive.google.com/file/d/1YyHCUYy5-YsO3VreWwGH3_mUZDmvXL1H/view?usp=sharing) and set the execute permission for your user using the chmod command.
<details closed> 
   <summary>Answer Key</summary>
   <code>sudo chmod u+x /pathtoFile/4.6.1-ActivitySetupScript.sh</code>
</details>

2. Open your terminal and take a snapshot of what processes are currently running on your system through using the ps command. Include all running processes, processes without a TTY, as well as CPU and memory usage.
<details closed>
   <summary>Answer Key</summary>
   <code>ps aux</code>
 </details>

3. Open your terminal and take a snapshot of all processes on the entire system (using the -e option), and compare its output with the output from the previous command.
<details closed>
   <summary>Answer Key</summary>
   <code>ps ux -e</code>
</details>

4. Open your terminal and take a snapshot of all the processes that were ran by the root user.
<details closed>
   <summary>Answer Key</summary>
   <code>ps -u root</code>
</details>

5. Open another terminal and execute the top command.
<details closed>
   <summary>Answer Key</summary>
   <code>top</code>
</details>

6. Filter the top utility based off of your user account.
<details closed>
   <summary>Answer Key</summary>
   Press the <code>u</code> key and when prompted enter your user account name.
 </details>

7. Reset the top utility to show all users
<details closed>
   <summary>Answer Key</summary>
   Press the <code>u</code> key and when prompted leave it blank and press enter.
</details>

8. Execute the activity setup script in another terminal using the bash command.
<details closed>
   <summary>Answer Key</summary>
   <code>sudo bash /pathToFile/4.6.1-ActivitySetupScript.sh</code>
</details>

9. Within the terminal that has the top utility running, identify the malicious process and kill it.
<details closed>
   <summary>Answer Key</summary>
   <code>sudo killall dd</code>
</details>
