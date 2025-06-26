## Activity Objectives

By the end of this activity, students will be able to understand how bash variables can be used within the terminal shell by:

- Accessing and modifying variables within the terminal.Using command substitution to assign the output of commands to variables.
- Performing arithmetic expansion and operations with variables.
- Using  variable expansion to retrieve values.



## Activity Instructions
1. In the terminal, assign your nickname to a variable named ```var```.
<details closed> 
   <summary>Answer Key</summary>
   <code>var="MJTheCyberGuy"</code>
</details>

2. Display the value of the ```var``` variable using the ```echo``` command.
<details closed> 
   <summary>Answer Key</summary>
   <code>echo $var</code>
</details>

3. Reassign the ```var``` variable a different value (e.g., your favorite color, pet's name, etc.).
<details closed> 
   <summary>Answer Key</summary>
   <code>var="Grurple a.k.a Green and Purple"</code>
</details>

4. Display the new value of the ```var``` variable using the echo command to demonstrate how a variable can be assigned a new value within the same terminal session.
<details closed> 
   <summary>Answer Key</summary>
   <code>echo $var</code>
</details>

5. Assign the current date and time to a variable named ```current_date``` using the ```date``` command.
<details closed> 
   <summary>Answer Key</summary>
   <code>current_date=$(date)</code>
</details>

6. Print the value of the ```current_date```  variable with the following text "The current date and time is: ", using the ```echo``` command.
<details closed> 
   <summary>Answer Key</summary>
   <code>echo "The current date and time is: $current_date"</code>
</details>

7. Create two separate variables, one named ```num1``` and assign it a value of 15, and the other named ```num2``` and assign it a value of 20.
<details closed> 
   <summary>Answer Key</summary>
   <code>num1=15</code><br><code>num2=20</code>
</details>

8. Create a  read-only variable named ```sum``` using the ```declare``` command, and then assign it the value of ```num1 + num2``` using arithmetic expansion.
<details closed> 
   <summary>Answer Key</summary>
   <code>declare -r sum=$((num1 + num2))</code>
</details>

9. Print the value of the sum variable with the following text, "The sum is: ".
<details closed> 
   <summary>Answer Key</summary>
   <code>echo "The sum is: $sum"</code>
</details>

10. Create a read-only variable named ```difference``` using the declare command, and then assign it the value of ```num2 - num1``` using arithmetic expansion.
<details closed> 
   <summary>Answer Key</summary>
   <code>declare -r difference=$((num2 - num1))</code>
</details>

11. Print the value of the difference variable with the following text, "
The difference is: ".
<details closed> 
   <summary>Answer Key</summary>
   <code>echo "The sum is: $difference"</code>
</details>

12. Both sum and difference variables were created using ```declare -r```. Attempt to assign the value of the difference variable to the sum variable. Record the error message and why do you think this reassignment failed?
<details closed> 
   <summary>Answer Key</summary>
   <code>sum=$difference</code><br>
  The error message that was displayed stated "sum: readonly variable". This indicates that the operation failed due to the sum variable being set to readonly. This means that once the sum variable was assigned a value, the variable's value could not and cannot be changed. 
</details>

13. Re-assign the variable ```var```  your full name as its value.
<details closed> 
   <summary>Answer Key</summary>
   <code>var="AJ Wright"</code>
</details>

14. Afterwards, use the ```echo``` command to display the following text "Greetings [Your Full Name Here]!!!".
<details closed> 
   <summary>Answer Key</summary>
   <code>echo "Greetings $var!"</code>
</details>

15. Extract the 1st 3 sub-strings stored within the var variable, using parameter expansion.
<details closed> 
   <summary>Answer Key</summary>
   <code>echo "${var:0:3}"</code>
</details>

16. Extract the last 2 sub-strings stored within the var variable.
<details closed> 
   <summary>Answer Key</summary>
  Since the variable var is storing the value "AJ Wright" which consists of 8 characters (including whitespace). To get the last 2 sub-strings the value 7 is used for the offset and the default value of 8 is used for the length. <br>
   <code>echo "${var:7}"</code>
</details>

17. Create an array named ```fruits``` that contains the values ```"apples"```, ```"kiwi"```, ```"berries"```.
<details closed> 
   <summary>Answer Key</summary>
   <code>fruits=("apples" "kiwi" "berries")</code>
</details>

18. Access and display the 1st element of the array.
<details closed> 
   <summary>Answer Key</summary>
   <code>echo ${fruits[0]}</code>
</details>

19. Access and display all of the elements of the array.
<details closed> 
   <summary>Answer Key</summary>
   <code>echo ${fruits[@]}</code>
</details>

20. Print the exit status of the last command that was executed.
<details closed> 
   <summary>Answer Key</summary>
   <code>echo $?</code>
</details>

