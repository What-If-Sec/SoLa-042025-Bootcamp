## Activity Objective

The objective of this activity is to enable students to develop proficiency in utilizing essential Linux bash commands for directory navigation, file management, and manipulation. By the end of the activity, students should be able to execute the following commands confidently: pwd, ls, mkdir, rmdir, rm, mv, cp, and touch. Through this hands-on exercise, students will enhance their understanding of command line interface operations, strengthen their problem-solving skills, and cultivate the ability to efficiently manage files and directories in a Linux environment.



## Activity Instructions

For this activity download the script below to your VM. Afterwards open your terminal and run the following commands: ```chmod u+x ~/Downloads/4.1.2-ActivitySetupScript.sh && bash ~/Downloads/4.1.2-ActivitySetupScript.sh```

[Click to Download Activity Script](https://drive.google.com/file/d/1v9u_36HZSLd4JhlsiutCCVlOjPzt0J9_/view)



Once you have executed the bash script above to complete setting up your enironment for the activity, follow the instructions below:

1. Move the files into their appropriate directory based off of the date in the files name ( i.e. files labeled August should go in the August directory) using the mv command.
<details closed>
<summary>Answer Key</summary>
<code>mv filepath/<file_name> filepath/<directory_name></code>
</details>

2. On your desktop create a directory named "Organized-Files" using the mkdir command.
<summary>Answer Key</summary>
mkdir ~/Desktop/Organized-Files 
</details>
  
3. Move the directories on your desktop i.e. January_Files, March_Files, etc. to the "Organized-Files" directory you created 
<details closed>
<summary>Answer Key</summary>
<code>mkdir ~/Desktop/Organized-Files</code>
</details>
  
4. Copy the Organized-Files directory to your Documents directory. (Note. Use either the cp command's help or man page to find the command option that will allow you to copy the Organized-Files directory and its contents to your Documents directory).
<details closed>
<summary>Answer Key</summary>
<code>cp -r ~/Desktop/Organized-Files ~/Documents</code>
</details>

5. Delete the "Organized-Files" directory located on your desktop.
<details closed>
<summary>Answer Key</summary>
<code>rm -R ~/Desktop/Organized-Files</code>
</details>


6. Within your terminal, change to the November_Files directory located within the Organized-Files directory that you previously copied to your Documents directory, and rename the "November_class-notes.txt" file to "112025_class-notes.txt", "November_personal-notes.txt" file to "112025_personal-notes.txt", and "November_memos.txt" file to "112025_memos.txt".
<details closed>
<summary>Answer Key</summary>
mv ~/Desktop/Organized-Files/November-Files/November_class-notes.txt ~/Desktop/Organized-Files/November-Files/112025_class-notes.txt
mv ~/Desktop/Organized-Files/November-Files/November_personal-notes.txt ~/Desktop/Organized-Files/November-Files/112025_personal-notes.txt
mv ~/Desktop/Organized-Files/November-Files/November_memos.txt" ~/Desktop/Organized-Files/November-Files/112025_memos.txt
</details>


