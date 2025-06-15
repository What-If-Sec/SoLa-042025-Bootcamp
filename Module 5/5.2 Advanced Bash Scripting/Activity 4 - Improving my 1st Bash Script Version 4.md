## Activity Objective

The goal of this activity is to help students practice improving code structure and readability by refactoring an existing script to use arrays for better scalability and maintenance. Students will refactor a script that creates archives of user-selected directories by using an array to store directory paths and implementing a loop for the "All" option to archive all directories at once.

By the end of this activity, students should be able to:
1. Refactor a script to use arrays for storing multiple values.
2. Modify existing control structures (like `if/elif`) to be more efficient and scalable.
3. Implement a loop for processing multiple items in a collection (such as directories).
4. Improve the usability of the script by adding options for batch operations (e.g., archiving all directories at once).

## Activity Instructions

Follow the instructions below to refactor your script:
1. Instead of having separate variables for each directory, store them in a single array called `directories`, to easily manage and reference multiple directories in one place.
2. Update the user menu by modifying your If/Else statement and adding an option for the user to select "All" to create an archive of all directories.
3. Modify the directory selection logic in your script such that when the All option is selected your script willloop through the array of directories and call the `display_and_archive` function for each directory.
4. Ensure that your script exits cleanly with a message as well as handles invalid input if the user selects an option outside of the valid range, and displays an error message.
5. Validate and verify that your script works as intended.
