## Activity Objectives

The objective of this activity is to enhance your understanding of functions in Bash scripting. You will refactor your existing script by identifying repetitive code and converting it into reusable functions. This exercise will help you practice:
1. Defining functions and understanding their structure.
2. Passing arguments to functions to make them more flexible.
3. Organizing code for better readability and reusability.
4. Minimizing redundancy by refactoring the script to use functions instead of repeating blocks of code.
By the end of this activity, you should be able to refactor scripts to reduce duplication and improve maintainability by implementing functions effectively.



## Activity Instructions

Refactor your previous script to use a function, by:
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
