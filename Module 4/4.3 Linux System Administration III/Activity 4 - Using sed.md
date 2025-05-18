## Activity Objective

By the end of this activity, students will be able to demonstrate proficiency in using the sed command in Linux for text manipulation, including finding and replacing text patterns within files.

Key Learning Outcomes:
1. Understand the syntax and basic usage of the sed command.
2. Learn how to perform text substitution using sed.
3. Explore advanced text manipulation techniques such as deletion, insertion, and global substitution with sed.
4. Apply sed commands in real-world scenarios to modify files efficiently and automate text editing tasks.
5. Develop problem-solving skills by creatively using sed to achieve specific text transformation goals.

## Activity Instructions

In the activity you will do the following:
1. Download to your VM the two log files from different admin websites, [located here](https://drive.google.com/drive/folders/1xJYo5oJgQRNGS4PzUTff0ai5tXXIUYLV).
2. Combine the two log files into a single log file named combined_logs.txt
<details closed>
<summary>Answer Key</summary>
  <code>cat Admin_logA.txt Admin_logB.txt > combined_logs.txt</code>
</details>

3. Use the ```sed``` command to normalize "failed logins" by replacing all instances of INCORRECT_PASSWORD with ACCESS_DENIED so that the data is consistent, and save the output in a new file called updated_combined_logs.txt.
<details closed>
<summary>Answer Key</summary>
  <code>sed 's/INCORRECT_PASSWORD/ACCESS_DENIED/g' combined_logs.txt > updated_combined_logs.txt
</code>
</details>

4. Submit your combined and normaliezed log file here.
>  Note: using sed  with the global option replaces all instances of INCORRECT_PASSWORRD with ACCESS_DENIED
