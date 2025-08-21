## Activity Objective

Through this activity, students will attain proficiency in utilizing the Linux bash find command to locate files and directories based on various search criteria. By the end of the activity, students will:
1. Understand the syntax and usage of the find command in the Linux terminal.
2. Learn to search for files and directories recursively within a specified directory hierarchy.
3. Gain competence in specifying search criteria such as file name, file type, modification time, size, and ownership.
4. Explore advanced options of the find command including executing actions on found files/directories.
5. Apply their knowledge to solve real-world file management and system administration tasks efficiently using the find command.

## Activity Instructions

For this activity, download the script located [here](https://drive.google.com/file/d/1NZ_7e_OuPfP3dXgD2FPoT40nMbykwwLI/view) to your VM, and then open your terminal and run the following commands:```chmod +x ~/Downloads/4.2.2-ActivitySetupScript.sh && bash ~/Downloads/4.2.2-ActivitySetupScript.sh```.

> Take note of the output of the command you executed above. The output of the script will give you information on how to complete the tasks below.

Once activity setup is completed use the find command to:
1. Use the find command to confirm that your investigation_evidence directory is no longer located on your VM's desktop. (Note: If there is no command output, the directory does not exist)
<details closed>
<summary>Answer Key</summary>
<code>find ~/Desktop -type d -name "investigation_evidence"</code>
</details>

2.  Use the find command to locate where the investigation_evidence directory has moved to by searching for syslog1.txt
<details closed>
<summary>Answer Key</summary>
<code>find /tmp -type f -name "syslog1.txt"</code>
</details>

3.  Submit the full file path to where the "investigation_evidence" directory moved to as well as the commands used to locate the "investigaition evidence" directory and "syslog1.txt" file.
<details closed>
<summary>Answer Key</summary>
investigation_evidence: <code>/tmp/Activity4.2.2/YouFoundMe/investigation_evidence</code>
</details>

4.  Bonus: For those that finish early, take a look at the [find command cheat sheet](https://quickref.me/find.html#google_vignette), and practice using the find command to locate files based on their size and based on (created by) the user "root".
