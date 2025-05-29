## Activity Objective

Students will demonstrate their understanding of foundational Linux concepts by applying previously learned skills to navigate the file system, read and write files, execute essential commands (ls, cd, rm, mkdir, touch, sed, awk, cat, grep, find), use wildcards (*), manage file permissions, and install or remove software packages using apt. '

This activity will reinforce practical Linux knowledge and builds confidence in real-world scenarios, by covering the following topics:
1. File System Navigation: Students will effectively navigate the Linux file system using commands like ls, cd, and find.
2. File Management: Students will create, modify, and delete files and directories using commands such as mkdir, touch, and rm.
3. Text Processing: Students will use sed and awk to manipulate and analyze text data.
4. Data Access: Students will use commands like cat, grep, and wildcards (*) to search, display, and filter file content.
5. File Permissions: Students will manage file and directory permissions to ensure proper access controls.
6. Software Management: Students will install, update, and remove software packages using apt.
7. Critical Thinking: Students will apply Linux commands and techniques in problem-solving scenarios to reinforce their understanding of system operations.

## Activity Instructions

Complete the review.

### Review Questions
1. Which command lists all files, including hidden ones, in the current directory?
    1.	ls
    2.	ls -a
    3.	ls -l
    4.	ls -h
<details closed>
<summary>Answer Key</summary>
<code>ls -a</code>
</details>
   
2. What is the purpose of the cd command?
    1.	Create directories
    2.	Copy directories
    3.	Change the current working directory
    4.	Delete directories
<details closed>
<summary>Answer Key</summary>
Change the current working directory
</details>

3. If you are in /home/user/docs, what command will take you to /home/user?
    1.	cd ..
    2.	cd /
    3.	cd ../
    4.	cd user
<details closed>
<summary>Answer Key</summary>
<code>cd ..</code>
</details>

4. Which command would you use to find a file named report.txt starting from the root directory?
    1.	find report.txt
    2.	find /root -type f -name  report.txt
    3.	find / -type d -iname report.txt
    4.	find /  -type f -name report.txt
<details closed>
<summary>Answer Key</summary>
<code>find /  -type f -name report.txt</code>
</details>

5. Which command(s) would create the file "myFile.txt" in Alice's documents directory if the current working directory is the desktop directory? Select all that apply.
    1.	touch /Documents/myFile.txt
    2.	touch ~/Documents/myFile.txt
    3.	touch /home/Alice/Documents/myFile.txt
    4.	touch ../Documents/myFile.txt
<details closed>
<summary>Answer Key</summary>
<code>touch ~/Documents/myFile.txt</code>, <code>touch /home/Alice/Documents/myFile.txt</code>, <code>touch ../Documents/myFile.txt</code>
</details>

6. Which command will remove a directory and all its contents?
    1.	rm -r
    2.	rmdir -r
    3.	rm
    4.	rmdir
<details closed>
<summary>Answer Key</summary>
<code>rm -r</code>
</details>

7. What command would create a directory named projects?
    1.	nano projects
    2.	touch projects
    3.	mkdir projects
    4.	echo projects
<details closed>
<summary>Answer Key</summary>
<code>mkdir projects</code>
</details>

8. You want to move a file named data.txt from /home/user to /home/user/docs if your current working directory is the user's home directory. Which command(s) would you use? Select all that apply.
    1.	mv data.txt /home/user/docs
    2.	mv data.txt home/user/docs/
    3.	mv data.txt docs/
    4.	mv data.txt /home/user/docs/
    5.	mv data.txt ~/docs/
    6.	mv data.txt docs
<details closed>
<summary>Answer Key</summary>
<code>mv data.txt docs/</code>, <code>mv data.txt /home/user/docs/</code>, <code>mv data.txt ~/docs/</code>
</details>

9. You want to copy a file named data.txt from /home/user/desktop to /home/user/docs if your current working directory is the user's home directory. Which command(s) would you use? Select all that apply.
    1.	cp ~/Desktop/data.txt ~/docs/
    2.	cp data.txt ~/docs/
    3.	cp /home/user/Desktop/data.txt  /home/user/docs/
    4.	cp data.txt docs/
    5.	cp Desktop/data.txt docs/
<details closed>
<summary>Answer Key</summary>
<code>cp   ~/Desktop/data.txt ~/docs/</code>, <code>cp   /home/user/Desktop/data.txt  /home/user/docs/</code>, <code>cp Desktop/data.txt docs/</code>
</details>

10. What happens if you execute the command rm * in a directory? (Hint: To answer create a new directory and populate it with files, then navigate to this new directory in your terminal.)
    1.	Removes all files in the directory
    2.	Removes all directories
    3.	Displays an error
    4.	Removes hidden files only
<details closed>
<summary>Answer Key</summary>
Removes all files in the directory
</details>

11. What command would rename a file oldname.txt to newname.txt?
    1.	mv oldname.txt newname.txt
    2.	cp oldname.txt newname.txt
    3.	rename oldname.txt newname.txt
    4.	mv oldname.txt /newname.txt
<details closed>
<summary>Answer Key</summary>
<code>mv oldname.txt newname.txt</code>
</details>

12. What is the purpose of the grep command?
    1.	Display file permissions
    2.	Search for patterns in text files
    3.	Edit files interactively
    4.	Find files within a directory
<details closed>
<summary>Answer Key</summary>
Search for patterns in text files
</details>

13. Which command replaces all occurrences of the word "Linux" with "UNIX" in a file named notes.txt?
    1.	sed '/Linux/UNIX/' notes.txt
    2.	awk 's/Linux/UNIX/g' notes.txt
    3.	sed -F '{print $1}' notes.txt
    4.	sed 's/Linux/UNIX/g' notes.txt
<details closed>
<summary>Answer Key</summary>
<code>sed 's/Linux/UNIX/g' notes.txt</code>
</details>

14. Which command displays the content of a file one page at a time?
    1.	cat
    2.	more
    3.	head
    4.	tail
<details closed>
<summary>Answer Key</summary>
<code>more</code>
</details>

15. Which command displays the content of a file one page at a time?
    1.	Delete files
    2.	Replace text within files
    3.	Extract and process text from files
    4.	Normalize data within files
<details closed>
<summary>Answer Key</summary>
Extract and process text from files
</details>

16. What command would you use to display the first 25 lines of a file named log.txt? Select all that apply.
    1.	head -n 25 log.txt
    2.	head 25 log.txt
    3.	head log.txt
    4.	head -25 log.txt
<details closed>
<summary>Answer Key</summary>
<code>head -n 25 log.txt</code>, <code>head -25 log.txt</code>
</details>

17. How would you count the number of lines in a file named data.csv?
    1.	wc -l data.csv
    2.	grep -c data.csv
    3.	awk -l data.csv
    4.	lines data.csv
<details closed>
<summary>Answer Key</summary>
<code>wc -l data.csv</code>
</details>

18. What does the wildcard * represent?
    1.	Zero or more characters
    2.	One character only
    3.	Hidden files
    4.	All characters
<details closed>
<summary>Answer Key</summary>
<code>Zero or more characters</code>
</details>

19. Which command lists all .txt files in the current directory?
    1.	ls *txt
    2.	ls .txt*
    3.	ls *.txt*
    4.	ls *.txt
<details closed>
<summary>Answer Key</summary>
<code>ls *.txt</code>
</details>

20. If you want to match files that start with "file" and end with ".log", which wildcard would you use?
    1.	file?.log
    2.	file*.log
    3.	file[1-5].log
    4.	*file.log*
<details closed>
<summary>Answer Key</summary>
<code>file*.log</code>
</details>

21. Which command finds all files in the current directory and its subdirectories?
    1.	find / -type f
    2.	find . -type f -a
    3.	find . -type f
    4.	find ~ -type f
<details closed>
<summary>Answer Key</summary>
<code>find . -type f</code>
</details>

22. What does ls a* do?
    1.	Lists hidden files
    2.	Lists all files and directories
    3.	Lists files that start with the letter "a"
    4.	Lists files that contain the letter "a"
<details closed>
<summary>Answer Key</summary>
Lists files that start with the letter "a"
</details>

23. How would add the executable permission for the group to a file named script.sh, without modifying the other granted permissions?
    1.	chmod +x script.sh
    2.	chmod g+x script.sh
    3.	chmod g=x script.sh
    4.	chmod 010 script.sh
<details closed>
<summary>Answer Key</summary>
<code>chmod g+x script.sh</code>
</details>

24. What does chmod 644 file.txt do?
    1.	Grants read and write permissions to the owner and read-only permission to the group and others.
    2.	Grants read and write permissions to the owner and execute-only permission to the group and others.
    3.	Grants read and write permissions to the owner and write-only permission to the groups and others.
    4.	Grants read and write permissions to the owner, group, and others.
<details closed>
<summary>Answer Key</summary>
<code>Grants read and write permissions to the owner and read-only permission to the group and others.</code>
</details>

25. How would you view the current permissions of only the file named example.txt? Select all that apply
    1.	ls -l
    2.	ls -a
    3.	ls -o example.txt
    4.	ls -l example.txt
<details closed>
<summary>Answer Key</summary>
<code>ls -o example.txt</code>, <code>ls -l example.txt</code>
</details>

26. What is a potential security risk associated with using sudo too frequently?
    1.	It grants too many permissions to the root user.
    2.	It exposes sensitive files to unauthorized users.
    3.	It can allow malicious users to gain root privileges if they have access to your account.
    4.	It requires the user to type their password too often.
<details closed>
<summary>Answer Key</summary>
It can allow malicious users to gain root privileges if they have access to your account.
</details>

27. You want to install the nginx service on a server and execute the command "apt install nginx" but receive a "Permission Denied" error. What does the error message most likely indicate?
    1.	That the user does not have the necessary permissions to install the software.
    2.	That the user has the necessary permissions to install the software.
    3.	That the user is in the sudoers group.
    4.	That the file permissions need to be changed.
<details closed>
<summary>Answer Key</summary>
That the user does not have the necessary permissions to install the software.
</details>

28. What command will allow you to check if the current user Alice has sudo privileges?
    1.	sudo -l
    2.	vi sudoers
    3.	sudo -v
    4.	sudo whoami
<details closed>
<summary>Answer Key</summary>
<code>sudo -v</code>, <code>sudo whoami</code>
</details>

29. Which command will list the sudo privileges granted to the user, Alice?
    1.	sudo -v
    2.	sudo -l
    3.	sudo visudo
    4.	sudo Alice
<details closed>
<summary>Answer Key</summary>
<code>sudo -l</code>
</details>

30. Why is apt considered an essential tool for Linux system administrators?
    1.	It is the only tool available for installing software on Linux.
    2.	It simplifies the process of managing software on Debian-based systems.
    3.	It is used for managing user accounts.
    4.	It is the only command that can install packages from the internet.
<details closed>
<summary>Answer Key</summary>
It simplifies the process of managing software on Debian-based systems.
</details>

31. Which command would redirect the output of the ls command to a file named dir_listing.txt and overwrite the file's contents if the file exists?
    1.	ls  -la dir_listing.txt
    2.	ls  -la >> dir_listing.txt
    3.	ls  -la | dir_listing.txt
    4.	ls  -la > dir_listing.txt
<details closed>
<summary>Answer Key</summary>
<code>ls  -la > dir_listing.txt</code>
</details>

32. Which command would redirect the output of the cat command to a grep command to filter for the word "key" or "KEY"?
    1.	cat file.txt | grep -i "\*key"
    2.	cat file.txt | grep "\*key\*"
    3.	cat file.txt | grep -i "key\*"
    4.	cat file.txt | grep -i "\*key\*"
<details closed>
<summary>Answer Key</summary>
<code>cat file.txt | grep "*key*"</code>
</details>
