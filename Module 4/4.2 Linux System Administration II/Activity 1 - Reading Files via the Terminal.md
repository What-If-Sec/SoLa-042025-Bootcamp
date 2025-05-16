## Activity Objective

By the end of this activity, students will be able to demonstrate proficiency in utilizing the more, less, head, tail, and nano commands within a Unix-like operating system to effectively read and navigate through text files. Specifically, they will:

1. Understand the functionality and purpose of the more, less, head, and tail commands.
2. Utilize the more and less commands to view the contents of a file, navigate through its content, and understand the differences between the two commands.
3. Apply the head command to display the beginning portion of a file and comprehend its practical use cases.
4. Apply the tail command to display the ending portion of a file and grasp its significance in various scenarios.
5. Practice navigating through files of different sizes and formats using these commands, thereby enhancing their proficiency in file management and text processing tasks in a Unix-like environment.

## Activity Instructions
For this activity download the script located [here](https://drive.google.com/file/d/1NYrMJ3Fa-o72Lisimz1UXWrQj6VgHJpY/view) to your VM. Afterwards open your terminal and run the following commands: ```chmod u+x ~/Downloads/4.2.1-ActivitySetupScript.sh && bash ~/Downloads/4.2.1-ActivitySetupScript.sh```

Once activity setup is completed, use the head, tail, more, and less command to view the contents of each file within the investigation_evidence directory created on your Desktop by completing the following tasks below:
1. Use the head command to view the first 10 lines of the app log file.
<details closed>
<summary>Answer Key</summary>
<code>head ~/Desktop/investigation_evidence/applog.txt</code>
</details>

2. Use the tail command to view the last 10 lines of the app log file.
<details closed>
<summary>Answer Key</summary>
<code>tail ~/Desktop/investigation_evidence/applog.txt</code>
</details>

3. Use the head command to view the first 2 lines of the email log file.
<details closed>
<summary>Answer Key</summary>
<code>head -2 ~/Desktop/investigation_evidence/emaillog.txt</code>
</details>

4. Use the tail command to view the last 2 lines of the email log file.
<details closed>
<summary>Answer Key</summary>
<code>tail -2 ~/Desktop/investigation_evidence/emaillog.txt</code>
</details>

5. Use the head command to view the first 15 lines of the syslog1 file
<details closed>
<summary>Answer Key</summary>
<code>head -15 ~/Desktop/investigation_evidence/syslog1.txt</code>
</details>

6. Use the tail command to view the last 15 lines of the syslog2 file
<details closed>
<summary>Answer Key</summary>
<code>tail -15 ~/Desktop/investigation_evidence/syslog2.txt</code>
</details>

7. Use the more command to view and scroll through the syslog1 file.
<details closed>
<summary>Answer Key</summary>
<code>more syslog1.txt</code>
</details>

8. Use the less command to view and scroll through the syslog2 file.
<details closed>
<summary>Answer Key</summary>
<code>less syslog1.txt</code>
</details>
