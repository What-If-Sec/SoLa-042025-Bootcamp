## Activity Objective

Students will demonstrate their understanding of how to chain Bash commands using the ;, &&, and || operators. Students will gain hands-on experience with these operators to control the flow of execution based on command success or failure, and they will apply this knowledge to automate tasks and handle errors effectively.

By the end of the activity, students will:

1. Understand and explain the purpose and behavior of ;, &&, and || operators in Bash.
2. Chain multiple commands together in a logical sequence to optimize workflow.
3. Use ; to execute commands sequentially, regardless of success or failure.
4. Use && to ensure the second command executes only if the first command is successful.
5. Use || to execute the second command only if the first command fails.
6. Evaluate the output of chained commands to verify command success or failure and handle exceptions.

## Activity Instructions

Open your Ubuntu virtual machine and run the commands provided within the knowledge check. After running each command, choose the correct answer based on what is printed in the terminal.

### Knoweldge Check
1. ```echo "Hello, world!"; echo "This is Bash."; echo "Commands are chained."```
What will be the output?
    1. Hello, world! This is Bash. Commands are chained.
    2. Hello, world! This is Bash.
    3. Hello, world!
    4. An error message will appear.
<details closed>
<summary>Answer Key</summary>
  Hello, world! This is Bash. Commands are chained.
</details>

2. ```mkdir test_folder && echo "Folder created successfully!"```
What will be the output?
    1. Nothing will be printed
    2. An error message saying "Folder already exists"
    3. Folder created successfully!
    4. mkdir: cannot create directory 'test_folder': File exists
<details closed>
<summary>Answer Key</summary>
  Folder created successfully!
</details>

3. ```rmdir non_existent_folder || echo "Directory does not exist."```
What will be the output?
    1. rmdir: failed to remove 'non_existent_folder': No such file or directory
    2. Nothing will be printed.
    3. Directory removed successfully.
    4. Directory does not exist.
<details closed>
<summary>Answer Key</summary>
  Directory does not exist.
</details>

4. ```mkdir test_dir && echo "Directory created" || echo "Directory creation failed"```
What will be the output if the directory test_dir does not exist?
    1. Directory creation failed
    2. Directory created
    3. Nothing will be printed.
    4. mkdir: cannot create directory 'test_dir': File exists
<details closed>
<summary>Answer Key</summary>
  Directory created
</details>

5. ```mkdir test_dir ; ls test_dir || echo "Unable to list directory contents"```
What will be the output if the directory test_dir does  exist? Select all that apply.
    1. Nothing will be printed
    2. mkdir: cannot create directory 'test_dir': File exists
    3. The contents of the test_dir will be displayed
    4. Unable to list directory contents
<details closed>
<summary>Answer Key</summary>
  mkdir: cannot create directory 'test_dir': File exists <br>
  The contents of the test_dir will be displayed
</details>

6. ```ls ~/Documents || echo "Directory not found"```
What will be the output if the directory test_dir does not exist?
    1. An error message will be displayed.
    2. The contents of the user's documents directory.
    3. Directory not found.
    4. ls: cannot access 'non_existent_file': No such file or directory
<details closed>
<summary>Answer Key</summary>
  The contents of the user's documents directory.
</details>

7. ```rm test_file.txt && echo "File deleted" || echo "File not found"```
What will be the output if the directory test_dir does not exist?
    1. File deleted
    2. File not found
    3. Nothing will be printed.
    4. rm: cannot remove 'test_file.txt': No such file or directory
<details closed>
<summary>Answer Key</summary>
  The contents of the user's documents directory.
</details>

8. ```mkdir my_folder && echo "Created my_folder" || echo "Failed to create my_folder"; echo "Done"```
Assume that my_folder does not exist when you run the command. What will be the output?
    1. Created my_folder, Failed to create my_folder, and  Done
    2. Failed to create my_folder and Done
    3. Done
    4. Created my_folder and Done 
<details closed>
<summary>Answer Key</summary>
Created my_folder and Done 
</details>

9. ```mkdir my_folder && echo "Created my_folder" || echo "Failed to create my_folder"; echo "Done"```
Assume that my_folder does not exist when you run the command. What will be the output?
    1. Created my_folder, Failed to create my_folder, and  Done
    2. Failed to create my_folder and Done
    3. Done
    4. Created my_folder and Done 
<details closed>
<summary>Answer Key</summary>
Created my_folder and Done 
</details>

10. Which of the following best describes the behavior of the ; operator in Bash?
    1. It ensures that the second command runs only if the first command is successful.
    2. It ensures that the second command runs only if the first command fails.
    3. It executes all commands sequentially, regardless of the success or failure of the previous commands.
    4. It stops execution after the first command.
<details closed>
<summary>Answer Key</summary>
It executes all commands sequentially, regardless of the success or failure of the previous commands.
</details>

11. You want to create a directory named my_project and display the message "Directory created" only if the directory was successfully created. Which operator would you use to achieve this?
    1. ;
    2. ||
    3. &&
    4. |
<details closed>
<summary>Answer Key</summary>
;
</details>

12. Which of the following scenarios best describes when the || operator would be used in Bash?
    1. To execute a second command regardless of whether the first command succeeds or fails.
    2. To execute a second command only if the first command fails.
    3. To execute a second command only if the first command succeeds.
    4. To execute both commands in parallel.
<details closed>
<summary>Answer Key</summary>
To execute a second command only if the first command fails.
</details>

13. Which of the following statements about ;, &&, and || is correct?
    1. && runs the second command only if the first one fails, and || runs the second command only if the first one succeeds.
    2. Both ; and && execute the second command only if the first command is successful.
    3. ; runs all commands sequentially, while && and || are dependent on the success or failure of the first command.
    4. ; is the same as && but allows for more commands to be chained.
<details closed>
<summary>Answer Key</summary>
; runs all commands sequentially, while && and || are dependent on the success or failure of the first command.
</details>

14. ```mkdir my_folder && echo "Success" || echo "Failure"```
What does the following command accomplish?
    1. Displays both "Success" and "Failure" regardless of whether my_folder is created.
    2. Displays "Failure" if my_folder is created; otherwise, displays "Success."
    3. Displays "Success" if my_folder is created; otherwise, displays "Failure."
    4. Only creates the directory my_folder without printing anything.
<details closed>
<summary>Answer Key</summary>
Displays "Success" if my_folder is created; otherwise, displays "Failure."
</details>
