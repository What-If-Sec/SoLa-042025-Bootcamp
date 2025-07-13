## Activity Objective

By the end of this activity, students will be able to effectively use the Windows Task Scheduler to automate the execution of PowerShell scripts. They will learn how to create, configure, and manage scheduled tasks to run a PowerShell script at the specified time or intervals, and understand how to set up triggers, actions, and conditions to ensure their scripts run as intended.

## Activity Instructions
For this activity you will use the Windows Task Scheduler to schedule the PowerShell script from the previous activity to be executed daily at 12:00 AM.  Follow the instructions below:
1. Open the Windows Task Scheduler by going to the Window's search bar and typing in "Task Scheduler".
2. In the Actions pane select "Create Task" to create your 1st scheduled task.
3. Provide a name and description for your scheduled tasks.
4. Update the security options to run whether the user is logged on or not, and to run with highest privileges.
5. Go to the Triggers tab and create a new trigger, to execute the script daily at 12:00 AM.
6. Go to the Actions tab set the action to "Start a program" and set the program to `C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe"` as well as add the argument `-ExecutionPolicy Bypass -File "C:\Path\to\Script\ScriptName.ps1"` inserting your own script's name and file path.
7. Go to the Settings tab and ensure that the task is scheduled to run as soon as possible after a scheduled start is missed.
8. Click "ok" and then go to the Task Scheduler Library to find your task. Right-click your task and click "run" to execute your task now and verify that it works.







