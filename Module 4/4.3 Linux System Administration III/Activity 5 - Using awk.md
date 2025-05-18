## Activity Objective:

By the conclusion of this activity, students will adeptly employ the awk command in the Linux environment, comprehending its capabilities for text processing, data extraction, and report generation.

Key Learning Outcomes:
1. Grasp the fundamental syntax and usage of the awk command.
2. Learn to extract specific fields or columns from text files using awk.
3. Understand how to perform text pattern matching and filtering with awk.
4. Explore the concept of conditional statements and looping constructs in awk for advanced text processing tasks.
5. Apply awk commands creatively to manipulate and transform text data efficiently.

## Activity Instructions:

In the activity you will do the following:
1. Use the updated_combined_logs.txt file from the previous activity and extract the timestamp and username fields from this file using the awk command.
<details closed>
<summary>Answer Key</summary>
  <code>awk '{print $4, $5, $6}' updated_combined_logs.txt
</code>
</details>

2. Use output redirection to save the results into another file named extracted_combined_logs.txt.
<details closed>
<summary>Answer Key</summary>
  <code>awk '{print $4, $5, $6}' updated_combined_logs.txt > extracted_combined_logs.txt
</code>
</details>

3. Use the awk, sort, and uniq commands along with pipes to identify which user was most likely attempting the brute-force attack, as the account with the most "failed login" attempts could indicate an attacker attempting to perform a bruteforce attack to gain access to the account.
> Hint: You will need to 1st awk extracted_combined_logs.txt, and then pipe its output into the 1st sort command, then pipe its output into the uniq command, and lastly pipe its output to another sort command. Read the man pages for sort and uniq to identify which options to use.

<details closed>
<summary>Answer Key</summary>
  <code>awk '{print $3}' extracted_combined_logs.txt | sort | uniq -c | sort -nr
</code>
</details>

5. Submit who the attacker is on EducateMe.

