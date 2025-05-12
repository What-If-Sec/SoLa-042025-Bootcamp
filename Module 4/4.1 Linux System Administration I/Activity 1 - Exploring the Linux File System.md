## Activity Objective

The objective of this hands-on activity is to familiarize students with the Linux file system by navigating through common directories using the cd command within your VM’s terminal. In this exercise, students will practice creating a file using the touch command and recording their observations within the created text file.

## Activity Instructions
Within this activity you will be using your Ubuntu VM to answer each question.
<br>
### Activity
1.	Open a new terminal, which command would you use to successfully create the file named "Module4.1-Observations.txt" on your Desktop?
    1.	touch
    2.	touch Module4.1-Observations.txt
    3.	touch /Desktop/Module4.1-Observations.txt
    4.	touch ~/Desktop/Module4.1-Observations.txt
<details closed>
<summary>Answer Key</summary>
touch ~/Desktop/Module4.1-Observations.txt
</details>

2.	Which command would allow you to change your current working directory to the Desktop directory?
    1.	cd ../Desktop
    2.	cd /Desktop
    3.	cd Desktop
    4.	cd
<details closed>
<summary>Answer Key</summary>
cd Desktop
</details>

3.	Which command(s) would allow you to view the contents of the Desktop directory? Select all that apply.
    1.	ls Desktop
    2.	ls ~/Desktop
    3.	ls ../Desktop
    4.	ls
<details closed>
<summary>Answer Key</summary>
ls ~/Desktop, ls ../Desktop, ls
</details>

4.	Which ls command from the previous question did not work, and why?
<details closed>
<summary>Answer Key</summary>
"ls Desktop" did not work due to the fact that our current working directory is the Desktop directory and the Desktop directory does not contain another directory within it that is also named "Desktop", resulting in the error message "ls: cannot access 'Desktop': No Such File or Directory to be displayed.
</details>

5.	Which command would allow you to navigate to the system's root directory?
    1.	cd root
    2.	ls /
    3.	pwd
    4.	cd /
<details closed>
<summary>Answer Key</summary>
cd /
</details>

6.	Use the ls command and verify which directories are sub-directories of the system's root directory?
    1.	bin
    2.	sbin
    3.	Documents
    4.	etc
    5.	trash
    6.	Desktop
    7.	var
<details closed>
<summary>Answer Key</summary>
bin, sbin, etc, var
</details>

7.	If your terminal's current working directory is your system's root directory, which command would allow you to navigate to the system's home directory within the terminal? Select all that apply.
    1.	cd home
    2.	ls home
    3.	touch home
    4.	cd /home
<details closed>
<summary>Answer Key</summary>
cd home, cd /home
</details>

8.	Which command would allow you to navigate to your user's home directory?
    1.	cd home
    2.	cd ~
    3.	cd /home
    4.	cd ~/home
<details closed>
<summary>Answer Key</summary>
cd ~
</details>

9.	If your terminal's current working directory is your Pictures directory, which command would allow you to change to your Desktop directory using a relative path?
    1.	cd ~/Desktop
    2.	cd Desktop
    3.	cd ../Desktop
    4.	cd /home/Desktop
<details closed>
<summary>Answer Key</summary>
cd ../Desktop
</details>

10.	If your terminal's current working directory is your Desktop directory, which command would allow you to change to your Documents directory using an absolute path?
    1.	cd ~/Documents
    2.	cd /Documents
    3.	cd ../Documents
    4.	cd Documents
<details closed>
<summary>Answer Key</summary>
cd ~/Documents
</details>

11.	If your terminal's current working directory is your Desktop directory, where would "myFile" be created if the following command is executed: ```touch ../myFile```
    1.	The user's desktop directory
    2.	The user's home directory
    3.	The system's home directory
    4.	The file will not be created
<details closed>
<summary>Answer Key</summary>
The user's home directory
</details>
