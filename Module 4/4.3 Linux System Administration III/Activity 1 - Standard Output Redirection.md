## Activity Objective:

Students will demonstrate the ability to manage command output by using the > (overwrite), >> (append), and | (pipe) operators to redirect the output of Linux commands to files or other commands. By completing this activity, students will understand how to:

## Activity Instructions:
Complete the following tasks below to generate a system report:

> Remember that you can use man and help pages to learn about commands you are unfamiliar with.

1. Launch your Ubuntu VM and open the terminal.
2. Navigate to your Documents directory, and create a new directory for this activity named "redirection_practice" and change to this directory.
<details closed>
<summary>Answer Key</summary>
  <code>mkdir redirection_practice</code><br>
  <code>cd redirection_practice</code>
</details>

3. Add a separator line "--------------------" to make the report header more readable, by using echo with redirection to a file named "report-header.txt".
<details closed>
<summary>Answer Key</summary>
  <code>echo "--------------------" > report-header.txt</code>
</details>

4. Use ```echo``` with redirection to append the report title "System Report" to report-header.txt.
<details closed>
<summary>Answer Key</summary>
  <code>echo "System Report" >> report-header.txt</code>
</details>

5. Use ```echo``` with redirection to append your first and last name to report-header.txt.
<details closed>
<summary>Answer Key</summary>
  <code>echo "Your-First-Name Your-Last-Name" >> report-header.txt</code>
</details>

6. Use the ```date``` command to capture the current date and time and append it to report-header.txt.
<details closed>
<summary>Answer Key</summary>
  <code>date >> report-header.txt</code>
</details>

7. Append another separator line "--------------------" to make the report header more readable, by using ```echo``` with redirection to report-header.txt.
<details closed>
<summary>Answer Key</summary>
  <code>echo "--------------------" >> report-header.txt</code>
</details>

8. Verify that your report header has been generated successfully, by comparing to this example report's header, [here](https://drive.google.com/file/d/10QeW4CVQcdwLIZ6-2JWCGt1GWoLjiCeT/view?usp=drive_link).
<details closed>
<summary>Answer Key</summary>
  <code>head report-header.txt</code>
</details>

9. Use the ```uptime``` command and create another file named "report.txt" containing the system uptime information.
<details closed>
<summary>Answer Key</summary>
  <code>uptime > report.txt</code>
</details>

10. Use the ```df -h``` command to display human-readable disk usage information and append it to report.txt.
<details closed>
<summary>Answer Key</summary>
  <code>df -h >> report.txt</code>
</details>

11. Use the ```ip addr show``` command to list all active network interfaces and settings, and pipe the command's output to the ```grep``` command to filter for your IP address "inet", and then append it to report.txt.
<details closed>
<summary>Answer Key</summary>
  <code>ip addr show | grep inet >> report.txt</code>
</details>

12. Use the ```ls``` command to recursively list the contents of your user's home directory and pipe its output to the ```wc``` command to display the number of files within your user's home directory and their sub-directories. Append this output to report.txt.
<details closed>
<summary>Answer Key</summary>
  <code>ls -R ~ | wc -l >> report.txt</code>
</details>

13. Verify that your report content has been generated successfully, by comparing to this example report's content, [here](https://drive.google.com/file/d/146Ry7fHE8fbfgSpkyZBvKkVAQJ7cqQbe/view?usp=drive_link).
    
14. Create another file named "report-footer.txt" and add a separator line  by using ```echo``` with redirection to create a file named report-footer.txt.
<details closed>
<summary>Answer Key</summary>
  <code>echo "--------------------" > report-footer.txt</code>
</details>
    
15. Use ```echo``` to append the message "System Report Completed" to the end of report-footer.txt
<details closed>
<summary>Answer Key</summary>
  <code>echo "System Report Completed"  >> report-footer.txt</code>
</details>

16. Verify the contents of the report.txt file, and compare it to the format of the report file [here](https://drive.google.com/file/d/1zFmyYdaDJR6d-kkU0AXW9kx6yIUGVW-w/view?usp=drive_link).
<details closed>
<summary>Answer Key</summary>
  <code>less report.txt</code>
</details>

17. Submit your report.txt file on EducateMe.

