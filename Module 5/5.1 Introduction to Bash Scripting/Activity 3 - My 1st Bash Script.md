## Activity Objective

Students will practice creating and running a basic Bash script to automate a simple task. This activity reinforces core scripting skills, command-line familiarity, and logic building, which are essential for roles such as IT Technician, SOC Analyst, or Help Desk Support.



## Activity Instructions

Create a bash script that will greet you and display the content and create an archive of your Desktop, Documents, and Downloads on your Desktop, by completing the following tasks:
1. Open your terminal in your Ubuntu VM.
2. Use a text editor to create a new script file named ```my_first_script```.sh.
3. Start by adding the shebang at the top of your script to indicate it’s a Bash script.
4. Create a variable called dt to store the output of the date command, which will give you the current date and time.
5. Use ```echo``` to print a greeting message to the user that includes their username.
6. Print another message that states "The script is now starting on [insert date and time] " by referencing the ```dt``` variable.
7.  Define variables for the paths to the Desktop, Documents, and Downloads directories. Note: You can use ```$HOME``` to reference the user's home directory.
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
