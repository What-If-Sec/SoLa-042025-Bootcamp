## Activity Objective
Students will successfully configure and deploy Git and Visual Studio Code within their Ubuntu virtual machines. This includes installing the required packages, setting up Git with their personal credentials, and preparing Visual Studio Code as their default code editor for managing version-controlled projects. By the end of this activity, students will be able to use Git and VS Code to track changes, commit code, and push files to a public GitHub repository as part of their workflow.

## Activity Instructions

Follow the instructions below:
1. Open a terminal in your Ubuntu VM and run sudo apt update followed by `sudo apt install git -y` to install Git.
2. In your terminal, navigate to your Documents directory and create a directory named GitHub.
3. Verify that Git installed correctly by running `git --version`.
4. Open VS code by running code in your terminal. Then go to the side menu bar and select Source Control.
5. Login to GitHub and create a new public repository named SoLa-Bootcamp-Portfolio. Do not initialize it with a README or .gitignore file.
6. Copy your GitHub repo's URL `https://github.com/your-username/SoLa-Bootcamp-Portfolio.git`.
7. Go to VS Code and select "Initialize Repository" to create a new Git local repository on your VM, allowing you to start tracking code changes. 
> Note: This is the equivalent of going to your VM's terminal and navigating to ~/Documents/GitHub/ and then executing `git init`.
8. Go  to the integrated terminal within VS Code and confirm that your current location is your local repo.
9. Create a README.md file using `touch`.
10. Open the README.md file in VS Code by going to the Source Control menu and under the changes dropdown menu selecting the README.md file.
11. In the README file, include the following sections: Project Title, Author Name, Date Created, Portfolio Overview, Technologies Used, and a list of the projects that will be included. A template README.md file can be found [here](https://github.com/othneildrew/Best-README-Template/blob/main/README.md), and an example of a README file that is used for a bash script can be found [here](https://github.com/nisiddharth/Christmas-Bash-Script).
12. Save the file and return to the integrated terminal in VS Code.
13. Run `git add README.md` to stage the file.
14. Run `git commit -m "Initial commit with portfolio README.md"` to commit the file.
15. Run `git push origin main` to upload the README file to GitHub.
16. Authorize VS Code to access your GitHub account and authenticate.
17. In the same local repo directory, create a new directory named Bash-Scripting-Project using `mkdir`.
18. Navigate to the new project folder on your VM using `cd`.
19. Create your Bash script using `touch` with the following naming convention:  `firstname_lastname_bash-scripting-project.sh`.
20. Open your script file within VS Code by going to the Source Control menu and under the changes dropdown menu selecting the file.
21. At the top of the script, add a file header comment that includes your full name and the date.
22. Save the script and return to the integrated terminal within VS Code.
23. Navigate back to the root of your local repo by running `cd ..`.
24. Run `git add Bash-Scripting-Project` to stage the entire folder and its contents.
25.  Run `git commit -m "Added Bash Scripting Project with initial script"`.
26.  Run `git push origin main` to upload the folder and script to your GitHub portfolio repo.
27.  Open your GitHub repository in a browser and confirm that the README.md and Bash-Scripting-Project folder with your script have been uploaded.
28.  Submit the URL of your public GitHub repository for review.
