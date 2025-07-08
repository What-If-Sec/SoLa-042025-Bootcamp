## Activity Objectives

By the end of this activity, students will be able to identify and explain the structure and purpose of Bash functions, understand how arguments are passed into functions, and recognize key built-in variables used in Bash scripting. Students will analyze a given script to reinforce foundational scripting concepts before creating their own scripts in future lessons.



## Activity Instructions

Download the script located [here](https://drive.google.com/file/d/1p11ngvWJj_77DTis2XZkYlqy-1IKEF9X/view?usp=sharing), and then complete the knowledge check.

### Activity
1.	What does $0 display when the script is run?
    1.	The name of the user.
    2.	The name of the script file.
    3.	The script's return value.
    4.	The home directory.
<details closed>
<summary>Answer Key</summary>
The name of the script file
</details>

2.	What is the purpose of the greet_user function?
    1.	To show system information.
    2.	To display the current date.
    3.	To greet the user with their name and role.
    4.	To create a backup.
<details closed>
<summary>Answer Key</summary>
To greet the user with their name and role
</details>

3.	What is the local keyword used for in a function?
    1.	To create a variable that only exists inside the function.
    2.	To reference a global variable.
    3.	To make a variable accessible from any script.
    4.	To import a variable from another file.
<details closed>
<summary>Answer Key</summary>
To create a variable that only exists inside the function.
</details>

4.	What are $1 and $2 used for in the greet_user function?
    1.	The first and second variables defined in the script.
    2.	The first and second commands in the script.
    3.	The first and second parameters used in the script.
    4.	The first and second command-line arguments passed to the script
<details closed>
<summary>Answer Key</summary>
The first and second command-line arguments passed to the function
</details>

5.	What is the purpose of a function in Bash?
    1.	To execute a command from an external file.
    2.	To repeat a set of commands without writing them multiple times.
    3.	To assign values to variables.
    4.	To run a script in a different directory.
<details closed>
<summary>Answer Key</summary>
To repeat a set of commands without writing them multiple times
</details>

6.	How do you call a function in Bash?
    1.	By using the function_name with no arguments.
    2.	By specifying call function_name.
    3.	By typing run function_name.
    4.	By writing the function’s name followed by any arguments in the script.
<details closed>
<summary>Answer Key</summary>
By writing the function’s name followed by any arguments in the script.
</details>

7.	What will happen if you call greet_user script without passing any arguments?
    1.	It will continue without greeting the user
    2.	The script will display an error message and stop.
    3.	It will prompt the user to enter values for the arguments.
    4.	It will display only the role, not the name.
<details closed>
<summary>Answer Key</summary>
It will prompt the user to enter values for the arguments.
</details>

8.	What is a function parameter in Bash, and how does it differ from a variable?
    1.	A function parameter is a value passed to the function when it is called, while a variable is a storage location that can be accessed globally across the script.
    2.	A function parameter is a value defined inside the function, and a variable is used to hold a constant value throughout the script.
    3.	A function parameter is a variable that holds values only inside the script, while a variable is used only within functions.
    4.	A function parameter is a command used within the script, while a variable stores a function's output.
<details closed>
<summary>Answer Key</summary>
A function parameter is a value passed to the function when it is called, while a variable is a storage location that can be accessed globally across the script.
</details>

9.	How are script arguments passed to the greet_user function as parameters in the script? (Select all that apply)
    1.	The values for the arguments are passed when calling the function, such as greet_user "$1" "$2".
    2.	The function parameters ($1, $2) are automatically populated by the system when the script is executed.
    3.	The arguments are passed inside the parentheses after the function name, and each one corresponds to a parameter in the function.
    4.	The function parameters are assigned default values, so they don’t need to be passed when the function is called.
<details closed>
<summary>Answer Key</summary>
1 & 3
</details>
