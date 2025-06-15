## Activity Objective

Students will enhance their first Bash script by incorporating if and else statements to introduce basic decision-making logic. This activity will help students understand how conditional statements can be used to control the flow of a script based on different inputs, system states, or conditions. 

By the end of this activity, students should be able to write Bash scripts that respond dynamically to various scenarios using conditional logic.  



## Activity Instructions

Refactor your script to do the following:
1. Open your original script file in ```nano```.
2. Update the ```main``` function so that the script does not automatically archive all directories by adding a prompt using ```echo -e``` to ask the user which directory they would like to archive. Include options for Documents, Desktop, Downloads, and Exit.
3. Use the ```read``` command to store the user's choice in a variable called ```dir```.
4. Add ```if```, ```elif```, and ```else``` statements to check the value of ```dir```, and  based on the input, call the ```display_and_archive``` function with the correct directory path.
5. If the user selects "1", call the function with the Documents directory.
6. If the user selects "2", call the function with the Desktop directory.
7. If  the user selects "3", call the function with the Downloads directory.
8. If the user selects "4", print a message and exit the script.
9. If the input is not valid, print an error message asking the user to select from the available options.
10. Save your script and run it in the terminal to test each option.



