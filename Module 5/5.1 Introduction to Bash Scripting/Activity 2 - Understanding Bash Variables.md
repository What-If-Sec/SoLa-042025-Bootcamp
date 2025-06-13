## Activity Objectives

By the end of this activity, students will be able to:
- Understand how variables are defined and accessed within a script.
- Understand how and why the declare command is used to define  variables.
- Build an understanding of variable expansion. command substitution, and arithmetic expansion though analyzing bash syntax.

## Activity Instructions

Complete the knowledge check below.

### Activity
1.	What is the correct way to create a variable named name and assign it the value "John" in Bash?
    1.	var name = "John"
    2.	name = "John"
    3.	name="John"
    4.	name : "John"
<details closed>
<summary>Answer Key</summary>
<code>name="John"</code>
</details>

2.	How do you access the value stored in the variable name that you created in Question 1?
    1.	print $name
    2.	$name
    3.	echo name
    4.	name
<details closed>
<summary>Answer Key</summary>
<code>$name</code>
</details>

3.	You created a variable name with the value "John". What is the correct way to change its value to "Alice"?
    1.	name="Alice"
    2.	name := "Alice"
    3.	name = "Alice"
    4.	change name to "Alice"
<details closed>
<summary>Answer Key</summary>
<code>name="Alice"</code>
</details>

4.	How can you combine the two variables "first_name" and "last_name" into a single string and assign it to a new variable called full_name?
    1.	full_name=$first_name$last_name
    2.	full_name="$first_name & last_name"
    3.	full_name=$first_name + $last_name
    4.	full_name="$first_name $last_name"
<details closed>
<summary>Answer Key</summary>
<code>full_name="$first_name $last_name"</code>
</details>


5.	How do you perform the addition of num1 and num2 and store the result in a variable sum?
    1.	sum=$[num1 + num2]
    2.	sum=$(num1 + num2)
    3.	sum=num1 + num2
    4.	sum=$((num1 + num2))
<details closed>
<summary>Answer Key</summary>
<code> sum=$((num1 + num2))</code>
</details>

6.	What does the built-in Bash variable $USER store?
    1.	The current user's home directory
    2.	The current system’s uptime
    3.	The name of the user who is currently logged in
    4.	The system’s hostname
<details closed>
<summary>Answer Key</summary>
<code>The name of the user who is currently logged in</code>
</details>

7.	After running a command, you want to capture whether the command was successful or failed. Which variable can you use to get the exit status of the last executed command?
    1.	#!
    2.	$?
    3.	$0
    4.	$EXIT_STATUS
<details closed>
<summary>Answer Key</summary>
<code>$?</code>
</details>

8.	How would you find the length of the string stored in the variable name?
    1.	length=$name.length
    2.	length=$(name.length)
    3.	length="${#name}"
    4.	length=${#name}
<details closed>
<summary>Answer Key</summary>
<code>length="${#name}"</code>
</details>

9.	How would you store the current date and time in a variable called current_time using command substitution?
    1.	current_time=$(date)
    2.	current_time=$(date)
    3.	current_time="date"
    4.	current_time=$date
<details closed>
<summary>Answer Key</summary>
<code>current_time=$(date)</code>
</details>

10.	Which variable holds the name of the current shell in use?
    1.	$SHELL
    2.	$BASH
    3.	$HOME
    4.	$OS
<details closed>
<summary>Answer Key</summary>
<code>$SHELL</code>
</details>

11.	Which of the following correctly assigns the current time to a variable time_now and then prints it?
    1.	time_now=date; echo $time_now
    2.	time_now=$(date); echo $time_now
    3.	echo time_now=date
    4.	time_now=(date) echo $time_now
<details closed>
<summary>Answer Key</summary>
<code>time_now=$(date); echo $time_now</code>
</details>

12.	Which of the following correctly uses a variable dir to change to a directory?
    1.	cd dir
    2.	cd "$dir"
    3.	cd $dir
    4.	cd $(dir)
<details closed>
<summary>Answer Key</summary>
<code>cd $dir</code>
</details>

13.	What is num2 to the power of num1 and store the result in a variable power?
    1.	power=$[num1 - num2]
    2.	power=$((num2 ** num1))
    3.	power=$(num1 ** num2)
    4.	power=num1 ** num2
<details closed>
<summary>Answer Key</summary>
<code>power=$((num2 ** num1))</code>
</details>

14.	If you want a variable named "meeting_schedule" to include the values of two other variables (day and time), how would Bash know to include their values inside the sentence "The meeting is scheduled for Monday at 5:30pm"? Select all that apply.
    1.	set day="Monday"
    2.	set time="5:30pm"
    3.	set meeting_schedule="The meeting is scheduled for day at time"
    4.	set meeting_schedule="The meeting is scheduled for $day at $time"
<details closed>
<summary>Answer Key</summary>
1, 3, & 4
</details>

15.	Which of the following commands will print the value of the variable greeting?
    1.	echo $greeting
    2.	echo $(greeting)
    3.	print $greeting
    4.	echo "greeting"
<details closed>
<summary>Answer Key</summary>
<code>echo $greeting</code>
</details>

16.	What is an array in Bash, and how do you define an array?
    1.	An array is a type of string that can only hold one value at a time.
    2.	An array is a variable that can hold multiple values, and you define it with parentheses
    3.	An array is a special type of file
    4.	An array is a database
<details closed>
<summary>Answer Key</summary>
An array is a variable that can hold multiple values, and you define it with parentheses
</details>

17.	Given the following array numbers=(10 20 30 40), what is the correct syntax to print the third value in the array?
    1.	echo ${numbers[@]}
    2.	echo ${numbers[0]}
    3.	echo ${numbers[2]}
    4.	echo ${numbers[3]}
<details closed>
<summary>Answer Key</summary>
<code>echo ${numbers[2]}</code>
</details>

18.	What does the declare command do in Bash?
    1.	It assigns a value to a variable.
    2.	It creates an array and assigns values.
    3.	It marks a variable as read-only.
    4.	It declares a variable type and sets properties like arrays or read-only.
<details closed>
<summary>Answer Key</summary>
It declares a variable type and sets properties like arrays or read-only.
</details>

