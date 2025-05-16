## Activity Objective:
Students will practice using the * wildcard character in various commands within an Ubuntu VM. This activity will help them understand how the wildcard can be used to match patterns in filenames, directories, and command outputs, enhancing their efficiency in navigating and managing files.

By completing this activity, students will:
1. Understand the utility of the * wildcard for pattern matching in filenames and commands.
2. Learn to use * with common commands like ls, grep, find, and rm.
3. Gain confidence in managing files and directories within an Ubuntu VM using the command line.

## Activity Instructions
For this activity download the script located [here](https://drive.google.com/file/d/1NYrMJ3Fa-o72Lisimz1UXWrQj6VgHJpY/view) to your VM. Afterwards open your terminal and run the following commands: ```sudo apt install pandoc -y && chmod u+x ~/Downloads/4.2.4-ActivitySetupScript.sh && bash ~/Downloads/4.2.4-ActivitySetupScript.sh```

Once activity setup is completed, do the following:
1. Use the find command to locate the directory to start this activity. The output from the setup script will provide you with a hint.
<details closed>
<summary>Answer Key</summary>
Command: <code>find /var -type d -name "*4.2.4"</code><br>
Directory: <code>/home/your-user-account/Activity-4.2.4/YouFoundMe/Now/Lets/Go/Deeper/Wildcard-Practice</code>
</details>

2. Use the cd command to navigate to the activity directory.
<details closed>
<summary>Answer Key</summary>
Command: <code>cd ~/Activity-4.2.4/YouFoundMe/Now/Lets/Go/Deeper/Wildcard-Practice</code><br>
</details>

3. From the current directory, use the find command to locate the files containing the word "image" at the beginning of their file name. (Hint: Use "." to specify the current directory when using find)
<details closed>
<summary>Answer Key</summary>
Command: <code> find . -type f -iname "image*"</code><br>
</details>

4. From the current directory use the find command to locate the directory containing text files.
<details closed>
<summary>Answer Key</summary>
Command: <code> find . -type f -iname "*.txt"</code><br>
</details>

5. From your current directory, use the ls command along with the * wildcard character to list only the text files contained within the directory identified in question 4.
 <details closed>
<summary>Answer Key</summary>
Command: <code> ls tmp/pictures/storage/*.txt"</code><br>
</details>

6. From your current directory, use the ls command along with the * wildcard character to list every file that is not a text file contained within the directory identified within question 4. (Hint: Use the --ignore option).
<details closed>
<summary>Answer Key</summary>
Command: <code>ls tmp/pictures/storage/ --ignore=*.txt </code><br>
</details>

7. From your current directory, use grep to search only the text file(s) for the word "flag", within the directory identified within question 4.  (Hint: Use the --include option).
<details closed>
<summary>Answer Key</summary>
Command: <code>grep -Ri "flag" --include=tmp/picture/storage/*.txt</code><br>
</details>

8. From you current directory, use grep to search only the log file(s) for the word "flag", within the directory identified within question 4. (Hint: Use the --include option).
<details closed>
<summary>Answer Key</summary>
Command: <code>grep -Ri "flag" --include=tmp/picture/storage/*.log</code><br>
</details>

9. From you current directory, use grep to identify if a word that begins with` "flag" is contained within the docx and pdf files contained within the directory identified within question 4. Were you able to grep the files? If not why were you unable to?
<details closed>
<summary>Answer Key</summary>
Command: <code>grep -i "flag*" tmp/picture/storage/summary.docx tmp/picture/storage/notes.pdf</code><br><br>
The above command will return no results; however this is not because neither file contains the word flag (one of them does), but due to the fact that grep only works on text files, and both the docx and pdf files are binary files.  
</details>

10. Use rm to delete all text files within the Activity-4.2.4 and sub-directories? Then check each directory confirm only the text files were deleted.
<details closed>
<summary>Answer Key</summary>
<code>rm -rf *.txt</code>
</details>
