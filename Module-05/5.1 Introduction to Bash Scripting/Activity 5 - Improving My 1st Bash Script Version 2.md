## Activity Objectives

The objective of this activity is to enhance your understanding of functions in Bash scripting. You will refactor your existing script by identifying repetitive code and converting it into reusable functions. This exercise will help you practice:
1. Defining functions and understanding their structure.
2. Passing arguments to functions to make them more flexible.
3. Organizing code for better readability and reusability.
4. Minimizing redundancy by refactoring the script to use functions instead of repeating blocks of code.
By the end of this activity, you should be able to refactor scripts to reduce duplication and improve maintainability by implementing functions effectively.

## Activity Scenario
You just completed a backup automation script for three common directories: Desktop, Documents, and Downloads. Your script works perfectly...it displays the contents of each folder and creates compressed archive backups in a Backups directory in the user's home folder.

After reviewing your script, your manager compliments your work but points out that it's repeating the same blocks of code three times — once for each directory. She explains that in IT environments, especially in scripting and automation, minimizing repetition makes scripts easier to maintain, update, and scale. Also, to improve readability and structure, wrap your overall script logic in a main function. That way, all setup and calls to your archive function are grouped together, which is how you should standardize scripts in your environment.

Your new task is to refactor the script using a function to create an archive. This function should:
1. Take the name of a directory as an input.
2. Display its contents.
3. Create a .tar.gz archive using the directory name.
4. Save the archive in the ~/Backups directory.

You also, need to refactor your script to use a `main` function that:
1. Defines the paths to the directories of interest.
2. Calls the "archive" function for each of those paths

## Pre-Scripting Analysis: Refactoring Your Script
Before you begin rewriting your backup script, take a few minutes to answer the following questions. These will help you plan your approach and understand the why behind the refactoring process.
1. Why does your manager want you to refactor your script?
2. What problems could occur in the future if you keep repeating the same blocks of code for each directory?
3. What parts of your original script are repeated multiple times?
4. What information changes each time those repeated commands are used?
5. What stays the same in those repeated commands?
6. What is the name of the function you plan to write?
7. What parameter(s) should your function accept?
8. What should your function do with that input? List the steps in order.
9. What specific tasks or setup steps should go inside your main function?
10. How will you test your refactored script to make sure it works the same as the original?

## Activity Instructions
Refactor your previous script to use functions, by:
1. Open your existing ```my_first_script.sh```.
2. At the top of your script, just below the shebang  line, remove the current section that displays the date and greeting message. You can keep it if you’d like, but it’s optional for this version.
3. Create a new function named ```display_and_archive```.
4. Inside the ```display_and_archive function```, define a variable named directory to accept the path that will be passed when the function is called.
5. Inside the ```display_and_archive``` function, define a second variable inside the function named ```backup_dir``` and set it to ```$HOME/Backups/```.
6. Inside the ```display_and_archive``` function, use the echo command to display the name of the directory. Note: Use the ```${directory##*/}``` syntax to extract the last part of the path (like "Desktop").
7. Inside the ```display_and_archive``` function, use the ```ls -R``` command to list the contents of the directory recursively.
8.  Inside the ```display_and_archive``` function, use the ```tar``` command to create an archive. The archive name should include the ${directory##*/} to make the filename match the directory name.
9. Inside the ```display_and_archive``` function, after creating the archive, print a message confirming that the archive was created.
10. After the ```display_and_archive``` function, create a new function named ```main```.
11. Inside the ```main``` function, define the variables for the paths to your Desktop, Documents, and Downloads directories.
12. Inside the ```main``` function, call the ```display_and_archive``` function three times — once for each of the directory paths, and pass each variable as an argument to the function.
13. After the ```main``` function, call main at the bottom of the script so it runs when executed.
14. Save the script and exit the editor.
15. Run the script and confirm it still lists contents and creates .tar.gz files in the Backups directory.

<details closed>
<summary>My_First_Script.sh v2</summary>
  
```bash
#!/bin/bash
# This script has been refactored to reduce repetition and improve structure
# based on feedback from your manager.

# ------------------------------------------
# Function: display_and_archive
# Purpose: To display the contents of a directory and archive it
# This replaces repeated code blocks for each folder (Desktop, Documents, Downloads)
# ------------------------------------------
display_and_archive() {
    local directory="$1"                    # Accepts a directory path as input
    local backup_dir="$HOME/Backups/"       # Sets the destination for backup files

    # Display contents of the directory
    echo "Contents of ${directory##*/}:"     # ${directory##*/} extracts just the folder name (e.g., Desktop)
    ls -R "$directory"                       # Lists contents recursively

    # Create the archive
    echo "Creating archive for ${directory##*/}"
    tar -cvvzf "${backup_dir}${directory##*/}.tar.gz" -C "$directory" .  
    # ^ This compresses everything inside the target folder into a tar.gz archive
    # The -C flag changes into that folder before archiving, so paths stay clean

    # Confirm archive was created
    echo "Archive created: ${backup_dir}${directory##*/}.tar.gz"
    echo ""
}

# ------------------------------------------
# Function: main
# Purpose: Organizes script setup and logic
# This wraps the main script steps into one place for better readability and structure
# ------------------------------------------
main(){
    # Define paths to directories that need to be backed up
    local desktop_dir="$HOME/Desktop"
    local documents_dir="$HOME/Documents"
    local downloads_dir="$HOME/Downloads"

    # Call the display_and_archive function for each directory
    # This eliminates repetitive code and makes future updates easy
    display_and_archive "$desktop_dir"
    display_and_archive "$documents_dir"
    display_and_archive "$downloads_dir"

    # You could add more folders here with just one more line
}

# Run the main function
# Entry point of the script — keeps everything organized
main
```
</details>
