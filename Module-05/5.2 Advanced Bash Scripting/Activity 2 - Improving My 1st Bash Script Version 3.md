## Activity Objective

Students will enhance their first Bash script by incorporating if and else statements to introduce basic decision-making logic. This activity will help students understand how conditional statements can be used to control the flow of a script based on different inputs, system states, or conditions. 

By the end of this activity, students should be able to write Bash scripts that respond dynamically to various scenarios using conditional logic.  

## Activity Scenario
Your refactored backup script is working well — it uses functions, avoids code repetition, and follows best practices by organizing everything under a main function.
After testing it with a few teammates, your manager gives you new feedback:
> “Right now, the script automatically backs up all three directories every time it runs. But not every user wants that. Let’s give users control. Some might only want to archive Desktop or Documents on a given day.”

Thus, you decide to update the script so that it prompts the user to choose which folder they want to archive. This means you’ll need to use `if/else` statements to respond to the user’s input.

## Pre-Scripting Analysis: Adding User Choice with Conditional Logic
Before updating your script, answer the following questions to help you plan the logic and structure for handling user input with conditionals.
1. Which function(s) will you need to make the update to?
2. What command will you use to collect input from the user?
3. What variable will store the user’s choice?
4. What type of values will the user be expected to enter (numbers, words, etc.)?
5. How many valid input options should the script recognize? List them.
6. What message should the script display before asking the user for input?
7. What should happen when the user selects a valid option?
8. What  should the script display if the user enters an invalid input?
9. Which command will you use to exit the script early (e.g., after selecting the option to quit the script or entering an invalid input)?
10. How will your script connect the user's choice to the correct directory path when calling the display_and_archive function?
11. How will using if, elif, and else help your script respond to different user inputs?

## Activity Instructions
Refactor your script by doing the following:
1. Open your original script file in ```nano```.
2. Update the ```main``` function and add a prompt to the user using ```echo -e``` to ask the user which directory they would like to archive. Include options for Documents, Desktop, Downloads, and Exit.
3. Use the ```read``` command to store the user's choice in a variable called ```dir```.
4. Add ```if```, ```elif```, and ```else``` statements to check the value of ```dir```, and  based on the input, call the ```display_and_archive``` function with the correct directory path. If the user selects "1", call the function with the Documents directory, if the user selects "2", call the function with the Desktop directory, if  the user selects "3", call the function with the Downloads directory, if the user selects "4", print a message and exit the script, and if the input is not valid, print an error message asking the user to select from the available options.
5. Save your script and run it in the terminal to test each option.

<details closed>
<summary>My_first_Script_v3.sh</summary>

```bash
#!/bin/bash
# This script now includes user interaction with conditional logic (if/elif/else)
# to allow the user to choose which directory to archive.

# ------------------------------------------
# Function: display_and_archive
# Purpose: Takes a directory path, displays its contents, and creates a compressed archive
# This function reduces code repetition and supports any directory path passed to it.
# ------------------------------------------
display_and_archive() {
    local directory="$1"               # Accepts the directory path as input
    local desk_dir="$HOME/Desktop/"   # Archives will be saved to the Desktop for visibility

    echo "Contents of ${directory##*/}:"  # ${directory##*/} gets just the folder name (e.g., Documents)
    ls -R "$directory"                   # Shows contents of the chosen directory

    echo "Creating archive for ${directory##*/}"
    tar -cvvzf "${desk_dir}${directory##*/}.tar.gz" -C "$directory" .  
    # Creates a .tar.gz archive of the directory contents
    # The -C flag switches into the folder so full paths aren’t included in the archive

    echo "Archive created: ${desk_dir}${directory##*/}.tar.gz"
    echo ""
}

# ------------------------------------------
# Function: main
# Purpose: Handles user input and determines which directory to archive
# Encapsulating the script logic in a main function keeps the code organized
# ------------------------------------------
main(){
    # Define paths to each of the target directories
    local desktop_dir="$HOME/Desktop"
    local documents_dir="$HOME/Documents"
    local downloads_dir="$HOME/Downloads"

    # Display a menu with options for the user
    echo -e "Which directory would you like to create an archive of?\n1. Documents\n2. Desktop\n3. Downloads\n4. Exit"
    
    # Use read to collect the user’s selection and store it in 'dir'
    read -p "Selection: " dir

    # Conditional logic to respond to user input
    if [ "$dir" == "1" ]; then
        display_and_archive $documents_dir         # If the user selects 1, archive Documents
    elif [ "$dir" == "2" ]; then
        display_and_archive $desktop_dir           # If the user selects 2, archive Desktop
    elif [ "$dir" == "3" ]; then
        display_and_archive $downloads_dir         # If the user selects 3, archive Downloads
    elif [ "$dir" == "4" ]; then
        echo "Exiting Script"                      # User chose to exit
        exit 0
    else
        echo "Error, Please select from one of the available options"  # Input was not valid
    fi
}

# Call the main function to begin execution
main

```

</details>



