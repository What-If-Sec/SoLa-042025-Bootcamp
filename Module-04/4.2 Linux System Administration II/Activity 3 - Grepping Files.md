## Activity Objective

By the end of this exercise, students will demonstrate proficiency in utilizing the Linux bash grep command to search for specific patterns within text files. Throughout the exercise, students will:
1. Understand the purpose and functionality of the grep command in the Linux terminal.
2. Learn to search for patterns within one or multiple files, utilizing basic regular expressions if necessary.
3. Gain familiarity with various options and flags available with the grep command to customize search behavior, including case sensitivity, recursive search, and displaying line numbers.
4. Apply their knowledge to real-world scenarios, such as analyzing log files, extracting specific information from large datasets, and debugging code by searching for patterns within source files.



## Activity Instructions
For this activity, download the script located [here](https://drive.google.com/file/d/1kyl2vgejqyghX_3rqr48pdYCwR_GXgfE/view) to your VM, and then open your terminal and run the following commands: ```chmod u+x ~/Downloads/4.2.3-ActivitySetupScript.sh && bash ~/Downloads/4.2.3-ActivitySetupScript.sh```.

Apache logs contain valuable information about website traffic, including IP addresses, user agents, requested URLs, and HTTP status codes. In this exercise by analyzing these logs, students observe the typical content of various different apache logs to identify and respond to security threats, such as hacking attempts, DDoS attacks, or unauthorized access attempts. For this exercise complete the following:
1. Change directories into the Activity-4.2.3 directory located in your Documents directory.
<details closed>
<summary>Answer Key</summary>
<code>cd "~/Documents/Activity-4.2.3"</code>
</details>

2. Execute the grep command and perform a case insensitive search using "http" as the data point on the file dated 10-Apr-2024. 
<details closed>
<summary>Answer Key</summary>
<code>grep -i "http" 10-Apr-2024-apachelog.txt</code>
</details>

3. Execute the grep command and perform a search using the HTTP error code "404" as the data point on the file dated 10-Jan-2024.
<details closed>
<summary>Answer Key</summary>
<code>grep "404" 10-Jan-2024-apachelog.txt</code>
</details>

4. Execute the grep command and get a count of the number of times the data point "script" is present within the file dated 10-Jan-2024.
<details closed>
<summary>Answer Key</summary>
<code>grep -c "script" 10-Jan-2024-apachelog.txt</code>
</details>

5. Lets identify if any other files contain the string "script" within them, so  execute the grep command and perform a recursive case insensitive search, but ONLY identify the file names.
<details closed>
<summary>Answer Key</summary>
<code>grep -Rl "script"</code>
</details>

6. Execute the grep command to get a recursive count of how many times the data point "script" is mentioned within each file.
<details closed>
<summary>Answer Key</summary>
<code>grep -Rc "script"</code>
</details>

7. Execute the grep command to perform a search of the file containing the highest count of the data point "XSS" and include the 3 lines after the string is found. Note: This log file is an example of what a Sys Admin would see if their web server was under a [XSS (Cross-Site Scripting) Attack](https://iaraoz.medium.com/web-security-101-cross-site-scripting-xss-attacks-5b6c6e8020c7).
<details closed>
<summary>Answer Key</summary>
<code>grep -i -A 3 "xss" 10-Jan-2024-apachelog.txt</code>
</details> 
  
8. Execute the grep command to perform a recursive search for the data points "admin" and "script".
<details closed>
<summary>Answer Key</summary>
<code>grep -rE "admin|script"</code>
</details> 

9. Bonus: Take a look at the [grep command cheat sheet](https://quickref.me/grep.html), and attempt to use the commands there to examine the other log files and identify the type of attack occurring.

> At this stage in your learning, it may feel overwhelming or challenging to fully understand how to identify certain attacks in log files. That is completely okay!!!
> 
> As you continue your studies and gain more knowledge about common attack techniques and how they manifest in logs, you'll become more adept at recognizing these patterns.
> 
> I encourage you to revisit this activity as you progress through this course.



