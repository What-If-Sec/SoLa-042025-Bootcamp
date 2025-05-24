## Activity Objective

By the end of this exercise, students will be able to:
1. Demonstrate proficiency in using the touch command to create six files of different names within a designated directory.
2. Understand the concept of file permissions and their significance in Unix-like operating systems.
3. Modify the permissions of the created files using both symbolic and octal notation with the chmod command.
4. Discriminate between symbolic and octal notation methods and articulate their advantages and limitations.
5. Apply appropriate permissions to the files to achieve desired levels of access for different user categories (owner, group, and others).
6. Verify the changes in file permissions using the ls -l command and interpret the output to ensure proper modifications.

## Activity Instructions

For this activity, download the script located here to your VM, and then open your terminal and run the following commands: ```chmod +x ~/Downloads/4.4.1-ActivitySetupScript.sh && bash ~/Downloads/4.4.1-ActivitySetupScript.sh```.
1. Open a terminal and navigate to the "Documents/Activity4.4.1" directory.
2. For "file1.txt" use the chmod command with octal notation to set the user permissions to read only, group permissions to read only, and other permissions to none.
<details closed>
<summary>Answer Key</summary>
  <code>chmod 444 file1.txt</code>
</details>

3. Verify that the permissions were set correctly for file 1.
<details closed>
<summary>Answer Key</summary>
  <code>ls -l file1.txt</code><br>
  The permisisons should be set to: <code>-r--r--r--</code>
</details>

4. For "file2.txt" use the chmod command with symbolic notation to set the user permissions to none, the group permission to read only, and other permissions to none.
<details closed>
<summary>Answer Key</summary>
  <code>chmod u=,g=r,o= file2.txt</code>
</details>

5. Verify that the permissions were set correctly for file 2.
<details closed>
<summary>Answer Key</summary>
  <code>ls -l file2.txt</code><br>
  The permisisons should be set to: <code>----r-----</code>
</details>

   
6. For "file3.txt" use the chmod command with octal notation to set the user permissions to none, the group permissions to none, and other permissions to none.
<details closed>
<summary>Answer Key</summary>
  <code>chmod 000 file3.txt</code>
</details>

7. Verify that the permissions were set correctly for file 3.
<details closed>
<summary>Answer Key</summary>
  <code>ls -l file3.txt</code><br>
  The permisisons should be set to: <code>----------</code>
</details>

8. For "file4.txt" use the chmod command with symbolic notation to set the user permissions to read, write, and execute, group permissions to read and write, and other permissions to read only.
<details closed>
<summary>Answer Key</summary>
  <code>chmod u=rwx,g=rw,o=r file4.txt</code>
</details>

9. Verify that the permissions were set correctly  for file 4.
<details closed>
<summary>Answer Key</summary>
  <code>ls -l file4.txt</code><br>
  The permisisons should be set to: <code>-rwxrw-r--</code>
</details>

10. For "file5.txt" use the chmod command with octal notation to set the user permissions to write only, the group permissions to none, and the other permissions to none.
<details closed>
<summary>Answer Key</summary>
  <code>chmod 200 file5.txt</code>
</details>

11. Verify that the permissions were set correctly for file 5.
<details closed>
<summary>Answer Key</summary>
  <code>ls -l file5.txt</code><br>
  The permisisons should be set to: <code>--w-------</code>
</details>

12. For "file6.txt" use the chmod command with symbolic notation to set the user permissions to read only, group permissions to read only, and other permissions to none.
<details closed>
<summary>Answer Key</summary>
  <code>chmod u=r,g=r,o= file6.txt
</code>
</details>

13. Verify that the permissions were set correctly for file 6.
<details closed>
<summary>Answer Key</summary>
  <code>ls -l file5.txt</code><br>
  The permisisons should be set to: <code>-r--r-----</code>
</details>

14. Attempt to read each file. Which files were you able to successfully read and which ones were you not able to? Why or why not?
<details closed>
<summary>Answer Key</summary>
<b>Successfully read files</b>: file1.txt, file4.txt, file6.txt (depending on user/group membership for file6.txt). <br>
<b>Not successfully read files</b>: file2.txt (if you're not in the group), file3.txt, file5.txt because the user was not granted read permissions. <br>
</details>

15. Attempt to write to (modify) each file using nano. Which files were you able to successfully modify and which ones you were not able to? Why or why not?
<details closed>
<summary>Answer Key</summary>
<b>Successfully modified files</b>: file4.txt (as the user or group) due to the permisisons set. <br>
<b>Not successfully modified files</b>: file1.txt, file2.txt, file3.txt, file5.txt, and file6.txt due to lack of write permissions.
</details>

16. Analyze the chmod command used to grant permissons to the ActivitySetupScript. What permission is being set, and why is this permission needed to run the bash script file? Does this command introduce any potential security vulnerabilities? how could it be updated?
 <details closed>
<summary>Answer Key</summary>
The <code>chmod +x ActivityScriptSetup.sh</code> command provides execute permissions to the user, group, as well as others enabling the shell script (.sh) file to be able to be executed as a program. However, because <code>chmod +x</code> grants execute permission to the user, group, and others. If the script contains sensitive information or operations that should only be executed by privileged users, granting execute permissions to everyone can increase the risk of unauthorized access or misuse. As a result, because only the user needs to have execute permissions for the script to be ran, the command that should be executed is <code>chmod u+x ActivityScriptSetup.sh</code>
</details>   

17. Submit your answers to question 14, 15, and 16 on EducateMe.
