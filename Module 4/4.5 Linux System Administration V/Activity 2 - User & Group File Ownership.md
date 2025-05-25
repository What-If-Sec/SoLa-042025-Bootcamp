## Activity Objectives

Students will gain a comprehensive understanding of file and group ownership in Linux systems by utilizing the su command to switch between user contexts, creating files for each user on their Linux virtual machine (VM), and then testing access permissions based on ownership. Through the use of the chown and chgrp commands, students will adjust file and group ownership to ensure access to files, thereby enhancing their proficiency in managing file permissions and ownership.

Through this exercise students will:
1. Gain understanding of the significance of file and group ownership in Linux systems.
2. Build proficiency in using the su command to switch between user contexts and test access permissions.
3. Gather hands-on experience in creating files for each user and adjusting file and group ownership using the chown and chgrp commands.
4. Grow the ability to analyze access controls and implement ownership management strategies effectively.

## Activity Instructions

Prior to starting the knowledge check below complete the following tasks:
1. Open your terminal and use the su command to switch to Rosie.
2. On Rosie's desktop directory create a file titled "RosiesScript.sh" using the touch command.
3. echo the text "#!/bin/bash" to the RosiesScript.sh file.echo the text "ls -l"  and append it to the RosiesScript.sh file.
4. Change the file permissions for RosiesScript.sh to read, write, and execute, for the group and user, and read only for others using the chmod command.
5. Change the group ownership of RosiesScript.sh to the developer group using the chown command.
6. Use the su command to switch to Virgil.On Virgil's desktop directory create a file titled "PR-Strategy.txt" with the touch command.
7. echo the text "Cut costs, increase revenue" to the PR-Strategy.txt file.
8. Change the file permissions for PR-Strategy.txt to read and write for the user, read for the group, and no permissions for others using the chmod command.
9. Change the group ownership of the PR-Strategy.txt file to the marketing group using the chgrp command.Once completed start the knowledge check below.

### Knowledge Check
1. What primary group does Virgil belong to?
   1. Virgil
   2. Developer
   3. General
   4. Marketing
<details closed>
<summary>Answer Key</summary>
  virgil
</details>

2. What secondary group(s) does Virgil belong to? Select all that apply.
   1. Virgil
   2. Developer
   3. General
   4. Marketing
<details closed>
<summary>Answer Key</summary>
  General and Marketing
</details>

3. What primary group does Rosie belong to?
   1. Developer
   2. Rosie
   3. General
   4. Marketing
<details closed>
<summary>Answer Key</summary>
  Rosie
</details>

4. What secondary group(s) does Rosie belong to? Select all that apply.
   1. Rosie
   2. General
   3. Marketing
   4. Developer
<details closed>
<summary>Answer Key</summary>
  General and Developer
</details>

5. What is the max number of secondary groups a user can belong to?
   1. 10
   2. 15
   3. 20
   4. 25
<details closed>
<summary>Answer Key</summary>
  15
</details>

6. Within your terminal, as Virgil navigate to Rosie's home directory and use the "ls -l" command to view the file permission for each of Rosie's files and directories.
What permissions are set for Rosie's documents directory?
   1. -rwxr-xr-x
   2. drwxr-xr-x
   3. -rwxr--r-x
   4. drw-r-xr-x
<details closed>
<summary>Answer Key</summary>
  drwxr-xr-x
</details>

7. Within your terminal, as Virgil navigate to Rosie's desktop directory. Were you able to? Explain why or Why not?
<details closed>
<summary>Answer Key</summary>
Given the set permissions for Rosie's desktop directory, others are granted r-x permissions and the directory is owned by the group, rosie. As a result, Virgil is able to use the cd command to navigate to /home/rosie/Desktop.
</details>

8. Within your terminal, as Virgil list the contents of Rosie's desktop directory. Were you able to? Explain why or Why not?
<details closed>
<summary>Answer Key</summary>
Given the set permissions for Rosie's desktop directory, others are granted r-x permissions and the directory is owned by the group, rosie. As a result, Virgil is able to use the ls command to list the contents of /home/rosie/Desktop.
</details>

9. Within your terminal, as Virgil using the touch command to create a file within Rosie's Desktop directory. Were you able to? Explain why or why not?
<details closed>
<summary>Answer Key</summary>
Given the set permissions for Rosie's desktop directory, others are granted r-x permissions and the directory is owned by the group, rosie. As a result, Virgil is not able to use the touch command to write a file to /home/rosie/Desktop.
</details>

10. Within your terminal, as Virgil use the head command to view the contents of the RosiesScript.sh file. Were you able to? Explain why or why not?
<details closed>
<summary>Answer Key</summary>
Since Virgil is not the owner of the file, is not in the rosie group, and other permissions are set to ---, Virgil is not able to use head to read the file.
</details>

11. Within your terminal, as Virgil use the echo command to append the "pwd" to the end of RosiesScript.sh file. Were you able to? Explain why or why not?
<details closed>
<summary>Answer Key</summary>
Since Virgil is not the owner of the file, is not in the developer group, and other permissions are set to ---, Virgil is not able to append the output of the echo command to the file.
</details>

12. Within your terminal, as Virgil run the command ```bash RosiesScript.sh``` to execute the bash script file RosiesScript.sh. Were you able to execute Rosie's script? Explain why or why not?
<details closed>
<summary>Answer Key</summary>
Since Virgil is not the owner of the file, is not in the developer group, and other permissions are set to ---, Virgil is not able to execute the bash script file.
</details>

13. What should you do in order for Virgil to be able to execute Rosie's bash script?
<ol type = i>
   <li>Change the file permissions of the bash script, so others can execute.</li>
   <li>Change the group ownership of the bash script to marketing.</li>
   <li>Change the group ownership of the bash script to general.</li>
   <li>Change the file ownership of the bash script to Virgil.</li>
</ol>
<details closed>
<summary>Answer Key</summary>
Change the group ownership of the bash script to general
</details>

14. Within your terminal, as Rosie navigate to Virgil's desktop and attempt to read the PR-Strategy.txt file. Were you able to? Explain why or why not?
<details closed>
<summary>Answer Key</summary>
Since Rosie is not the owner of the file, is not in the marketing group, and other permissions are set to ---, Rosie is not able to read the file.
</details>

15. Which command(s) would successfully change the group ownership of PR-Strategy.txt to the general group? Select all that could be used.
<ol type = i>
   <li>sudo chgrp PR-Strategy.txt general</li>
   <li>sudo chown general PR-Strategy.txt</li>
   <li>sudo chgrp general PR-Strategy.txt</li>
   <li>sudo chown :general PR-Strategy.txt</li>
</ol>
<details closed>
<summary>Answer Key</summary>
<code>sudo chgrp general PR-Strategy.txt</code>, <code>sudo chown :general PR-Strategy.txt</code>
</details>
