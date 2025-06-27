## Activity Objective

The goal of this activity is to help students practice improving code structure and readability by refactoring an existing script to use arrays for better scalability and maintenance. Students will refactor a script that creates archives of user-selected directories by using an array to store directory paths and implementing a loop for the "All" option to archive all directories at once.

By the end of this activity, students should be able to:
1. Refactor a script to use arrays for storing multiple values.
2. Modify existing control structures (like `if/elif`) to be more efficient and scalable.
3. Implement a loop for processing multiple items in a collection (such as directories).
4. Improve the usability of the script by adding options for batch operations (e.g., archiving all directories at once).

## Activity Scenario
Your interactive backup script is almost perfect. It prompts the user to choose a directory, uses a function to avoid repetition, and includes clear archive output on the user’s Desktop. Your manager is impressed with the progress.

But now, they have another improvement request:
> “I love that the script lets users choose one directory to archive at a time — but it would be even more helpful if there was a fourth option that archives all three directories at once. You already have the logic in place. Now, let’s make the script smarter and more efficient.”

In essence, your manager doesn’t want to execute the script three different times to archive all three directories.


## Pre-Scripting Analysis: Adding a Loop
Before updating your script, answer the following questions to help you plan your scripts development.
1. What is the new feature your manager is asking you to add to the script?
2. Why is it better to use a for loop instead of repeating function calls for each directory?
3. What three directories will be included when the user selects the "All" option?
4. How can you store all three directory paths in a single variable (hint: what Bash structure would you use)?
5. Write out how your array will look using the full directory paths.
6. What kind of loop will you use to go through each item in the array?
7. What variable will you use inside the loop to represent each directory as it is being processed?
8. What function will you call inside the loop to process each directory?
9. What should the script do if the user chooses an invalid option?
10. How will your script respond if the user chooses option 4 (All)? Write the steps in order.

## Activity Instructions
Follow the instructions below to refactor your script:
1. Instead of having separate variables for each directory, store them in a single array called `directories`, to easily manage and reference multiple directories in one place.
2. Update the user menu by modifying your If/Else statement and adding an option for the user to select "All" to create an archive of all directories.
3. Modify the directory selection logic in your script such that when the "All" option is selected your script will loop through the array of directories and call the `display_and_archive` function for each directory.
4. Ensure that your script exits cleanly with a message as well as handles invalid input if the user selects an option outside of the valid range, and displays an error message.
5. Validate and verify that your script works as intended.

<details closed>
<summary>my_first_script_v4.sh </summary>

```bash
#!/bin/bash
# This script now includes an option to archive all directories using a for loop.
# It demonstrates use of arrays, conditional logic, and functions to keep the script clean and scalable.

# -------------------------------------------------------
# Function: display_and_archive
# Purpose: Display contents of a directory and create a compressed archive on the Desktop
# -------------------------------------------------------
display_and_archive() {
    local directory="$1"               # Takes one argument: the path of the directory to archive
    local desk_dir="$HOME/Desktop/"   # Archives will be saved to the user's Desktop

    echo "Contents of ${directory##*/}:"  # Show the contents of the directory (e.g., Documents, Desktop, etc.)
    ls -R "$directory"

    echo "Creating archive for ${directory##*/}"
    tar -cvvzf "${desk_dir}${directory##*/}.tar.gz" -C "$directory" .  
    # The -C option changes into the directory before archiving its contents
    # ${directory##*/} grabs just the directory name from the full path

    echo "Archive created: ${desk_dir}${directory##*/}.tar.gz"
    echo ""
}

# -------------------------------------------------------
# Function: main
# Purpose: Display a menu to the user and respond to their selection using conditionals
# -------------------------------------------------------
main(){
    # New Addition: An array to store the paths of all directories we want to offer as options
    local directories=("$HOME/Documents" "$HOME/Desktop" "$HOME/Downloads")

    # Display the menu of directory options, including the new "All" option
    echo -e "Which directory would you like to create an archive of?\n1. Documents\n2. Desktop\n3. Downloads\n4. All\n5. Exit"
    read -p "Selection: " dir  # Capture the user’s selection

    # Use if/elif/else to respond to the user’s input
    if [ "$dir" == "1" ]; then
        display_and_archive "${directories[0]}"  # Archive Documents
    elif [ "$dir" == "2" ]; then
        display_and_archive "${directories[1]}"  # Archive Desktop
    elif [ "$dir" == "3" ]; then
        display_and_archive "${directories[2]}"  # Archive Downloads
    elif [ "$dir" == "4" ]; then
        # NEW FEATURE: Use a for loop to iterate through all directories
        # This avoids writing multiple function calls manually
        for d in "${directories[@]}"; do
            display_and_archive "$d"             # Call the archive function for each directory in the array
        done
    elif [ "$dir" == "5" ]; then
        echo "Exiting Script"                    # Exit the script if the user selects option 5
        exit 0
    else
        echo "Error, Please select from one of the available options"  # Handle invalid input
    fi
}

# Call the main function to start the script
main

```

</details>




