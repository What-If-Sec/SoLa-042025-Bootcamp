## Activity Objective

The objective of this activity is to help students understand and implement control flow in Bash scripts using while loops, along with the use of `break` and `continue` statements. By the end of this activity, students will be able to:
1. Write and refactor Bash scripts using `while` loops for continuous user interaction.
2. Utilize `break` to exit loops gracefully based on specific conditions (e.g., user input).
3. Apply `continue` to skip certain iterations of a loop and prompt the user again when invalid input is detected.
4. Understand the importance of proper flow control in interactive scripts to handle user inputs, errors, and exits effectively.
5. Refactor existing scripts to improve readability, efficiency, and user experience using `while`, `break`, and `continue`.
Through this activity, students will gain hands-on experience with Bash loops and control flow, which are fundamental skills for writing more dynamic and user-friendly scripts.

## Activity Scenario
You've built a solid, interactive backup script that lets users choose which directory they want to archive or select all of them. After reviewing it again, your manager gives you one last refinement request:
> “Right now, if the user types something invalid, the script exits and they have to run it again from scratch. That’s not ideal — especially if it’s used by people who aren’t very technical.”

Your manager wants the script to be more user-friendly and fault-tolerant, especially when used in shared environments like support desks or onboarding stations.

## Pre-Scripting Analysis: Improving Script Flow
Before updating your script, answer the following questions to plan your logic and understand how to keep the script running until the user provides a valid selection.
1. What problem is your manager asking you to fix in the current version of your script?
2. Why is it not ideal for the script to exit when a user enters invalid input?
3. What type of loop can you use to keep the script running until the user chooses to exit?
4. What condition should be used to keep the loop going?
5. Where should the user prompt and read command go in the loop?
6. What should happen inside the loop when the user: Enters a valid option (1–4)? Enters option 5? Enters anything else?
7. What command can you use to immediately stop the loop when the user selects “Exit”?
8. What command will allow the loop to skip the current invalid input and move to the next prompt?

## Activity Instructions
Refactor the code to use a while true loop that will repeatedly ask the user for input until they explicitly choose to exit, following the instructions below:
1. Wrap the entire logic for prompting and handling user input inside a `while` loop and set the condition to true in order to continuously ask for the user’s choice.
2. Inside the `while` loop, update the exit logic to include a `break` to exit the loop. This will allow the script to exit the infinite loop and finish the execution cleanly.
3. Inside the `while` loop, update the logic that handles invalid inputs to include a `continue`. This will ensure that after receiving an invalid input, the script will go back to the beginning of the loop and ask for the user's input again.
4. Validate and verify that your script will continue looping, asking the user for input, until the user selects the option to exit, and if the user selects an invalid option, the script will display an error message and prompt them again without performing any other operations.
5. Submit version 4 of your script.

<details closed>
<summary>my_first_script_v5.sh</summary>

```bash
#!/bin/bash

# Function to display directory contents and create archive
display_and_archive() {
    local directory="$1"
    local desk_dir="$HOME/Desktop/"

    echo "Contents of ${directory##*/}:"
    ls -R "$directory"
    
    echo "Creating archive for ${directory##*/}"
    tar -cvvzf "${desk_dir}${directory##*/}.tar.gz" -C "$directory" . 
    
    echo "Archive created: ${desk_dir}${directory##*/}.tar.gz"
    echo ""
}

main(){
    local directories=("$HOME/Documents" "$HOME/Desktop" "$HOME/Downloads")

    # NEW FEATURE: A while loop has been added to keep the menu running until the user explicitly chooses to exit.
    # In the previous version, the script ran only once and exited after a single input.
    # This change improves usability by letting the user archive multiple directories without rerunning the script.
    while true; do
        # Display the menu options and prompt for user input each time through the loop
        echo -e "Which directory would you like to create an archive of?\n1. Documents\n2. Desktop\n3. Downloads\n4. All\n5. Exit"
        read -p "Selection: " dir

        # Use if/elif/else to respond to the user’s input
        if [ "$dir" == "1" ]; then
            display_and_archive "${directories[0]}"  # Archive Documents
        elif [ "$dir" == "2" ]; then
            display_and_archive "${directories[1]}"  # Archive Desktop
        elif [ "$dir" == "3" ]; then
            display_and_archive "${directories[2]}"  # Archive Downloads
        elif [ "$dir" == "4" ]; then
            # Previously added feature: for loop to archive all directories
            # This was introduced to reduce repetition and handle multiple backups cleanly
            for d in "${directories[@]}"; do
                display_and_archive "$d"
            done
        elif [ "$dir" == "5" ]; then
            # NEW BEHAVIOR: This is now the only way to exit the script
            echo "Exiting Script"
            exit 0
        else
            # NEW FEATURE: Handles invalid input and re-prompts the user instead of exiting the script
            echo "Error, Please select from one of the available options"
            # The while loop ensures the script does not exit here and restarts the menu prompt
        fi
    done

    # This message would only display if the loop ends another way (not expected with exit 0 in place)
    echo "Goodbye!!!"
}

# Call the main function to start the script
main

```

</details>

