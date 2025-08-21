## Activity Objective

Students will practice creating and running a basic Bash script to automate a simple task. This activity reinforces core scripting skills, command-line familiarity, and logic building, which are essential for roles such as IT Technician, SOC Analyst, or Help Desk Support.

## Activity Scenario
You are a junior IT technician at a small company that doesn’t yet have centralized backups. The Systems Administrator has asked you to create a simple backup script that can be used by staff who are working remotely or on personally issued laptops.

An employee wants to make a local backup of important files before:
- Reimaging their system
- Traveling for a conference
- Handing the laptop to IT for repairs
  
#### Task Requirements
Your script should:
1. Greet the user and show when the backup process started.
2. List the contents of the user’s Desktop, Documents, and Downloads directories so they can confirm what will be backed up.
3. Compress the contents of each directory into separate .tar.gz archive files.
4. Save those archive files in a Backups folder in the user’s home directory.

## Pre-Scripting Analysis: Breakdown the Scenario
Read the scenario provided. Then, answer the following questions before beginning the task. Your goal is to think like a developer: identify the problem, define the goal, and figure out what inputs and outputs are needed.
1. What is the main purpose of this script?
2. Who is the user or audience for this script?
3. What are the key directories that this script will work with?
4. How can we refer to the current user's directories in a way that works on any machine?
5. What variables may be needed in the script? what should each one store?
6. What kind of files may the script need to create? What will be inside those files?
7. What should the script do before creating those files?
8. Where should the script save the files? Why is that a good choice?
9. List what the script needs to do before it creates any backups.
10. What should the script display to the user along the way?
11. What Linux command(s) do you think might be useful for: Showing directory contents? Creating compressed backups? Displaying messages?
12. (Out of Scope for Module 5.1) What could go wrong when running this script? How should a good script handle that?

> Now that you've broken down the scenario, compare your answers to the instructions you're about to follow. What steps did you predict correctly? Which ones surprised you?

## Activity Instructions
Create a bash script that will greet you and display the content and create an archive of your Desktop, Documents, and Downloads on your Desktop, by completing the following tasks:
1. Open your terminal in your Ubuntu VM.
2. Use a text editor to create a new script file named ```my_first_script```.sh.
3. Start by adding the shebang at the top of your script to indicate it’s a Bash script.
4. Create a variable called dt to store the output of the date command, which will give you the current date and time.
5. Use ```echo``` to print a greeting message to the user that includes their username.
6. Print another message that states "The script is now starting on [insert date and time] " by referencing the ```dt``` variable.
7. Define variables for the paths to the Desktop, Documents, and Downloads directories. Note: You can use ```$HOME``` to reference the user's home directory.
8. Add a command to display the message "The contents of the Desktop Directory is: " and then display the contents of the desktop variable using ```ls```.
9. Add a command to display the message "The contents of the Documents Directory is: ". and then display the contents of the docs variable using ```ls```.
10. Add a command to display the message "The contents of the Downloads Directory is: " and then display the contents of the downloads variable using ```ls```.
11. Add a line to print the message: "Creating archive for Desktop..."
12. Create a gzipped tarball for each of the directories, and save the files to the Backups directory.
13. Add a line to print the message: "Archive created: "  and include the location of the gzipped tarball.
14. Add a line to print the message: "Script execution completed."
15. Make the script executable using the ```chmod u+x``` command to make your bash file executable.
16. Run the script using ```./my_first_script.sh```. Note: If your script fails to execute, examine the error messaging to identify the root cause, debug, and then fix.
17. Submit a screenshot of the output or copy/paste the terminal result.

<details closed>
<summary>My_First_Script.sh</summary>
  
```bash
#!/bin/bash
# This shebang tells the system to run this script using the Bash shell.

# -------------------------------
# Personal Backup Script
# Scenario: You are tasked with creating a script that displays key directory contents
# and backs them up to compressed archives for safekeeping.
# -------------------------------

# Store the current date and time in a variable (for logging or future use)
dt=$(date)

# Greet the current user and note when the script started
echo "Greetings $USER"
echo "The script is now starting on $dt"

# Step 1: Define the paths to common user directories
desktop_dir="$HOME/Desktop/"
documents_dir="$HOME/Documents/"
downloads_dir="$HOME/Downloads/"
backups_dir="$HOME/Backups/"  # Where the backups will be stored

# Step 2: Show the contents of each directory before backing them up
echo "Contents of Desktop:"
ls "$desktop_dir"
echo ""

echo "Contents of Documents:"
ls "$documents_dir"
echo ""

echo "Contents of Downloads:"
ls "$downloads_dir"
echo ""

# Step 3: Create compressed archives of each directory
# The -C flag lets us change into the directory before archiving its contents
# The "." means "archive everything in this directory"

echo "Creating archive for Desktop..."
tar -cvvzf "${backups_dir}Desktop.tar.gz" -C "$desktop_dir" .
echo "Archive created: ${backups_dir}Desktop.tar.gz"
echo ""

echo "Creating archive for Documents..."
tar -cvvzf "${backups_dir}Documents.tar.gz" -C "$documents_dir" .
echo "Archive created: ${backups_dir}Documents.tar.gz"
echo ""

echo "Creating archive for Downloads..."
tar -cvvzf "${backups_dir}Downloads.tar.gz" -C "$downloads_dir" .
echo "Archive created: ${backups_dir}Downloads.tar.gz"
echo ""

# Step 4: Notify that the script has completed
echo "Script execution completed."
```
</details>
