## Activity Objective
Activity Objective

Students will learn how to create a PowerShell script that automates the process of importing data from a CSV file to manage installed applications. The script will perform the following tasks:
1. Import Data: Load a CSV file containing columns for Name, PackageName, and Justification into PowerShell.
2. Check Installation: For each entry in the CSV, check if the application specified by PackageName is installed on the system.
3. Remove Application: If the application is installed, proceed to uninstall it.
4. Logging and Validation: Provide output indicating whether each application was found and removed, and log any issues or errors encountered.

## Activity Scenario

You work in a mid-sized company with strict software policies. IT has discovered that employees are installing apps like Spotify, Skype, or Zoom — software not authorized for work machines. Leadership wants a script that:
- Checks if any blacklisted applications are installed.
- If found, notifies the user via a message.
- Then uninstalls the prohibited software.

The script to complete this assignment will need to do the following based off the above requirements:

1. Verify that the CSV file exists.Load the list of blacklisted applications from the CSV file.
2. Loop through each item in the prohibited/blacklisted app list.
3. Check if the app is installed via Chocolatey.
4. Uninstall the app via Chocolatey.
5. If not found in Chocolatey, check via PS CmdLets.

## Activity Instructions
Follow the instructions below to create the PS script that is able to read a CSV file and uninstall the applications within.
1. Create a CSV file named "prohibited-applications.csv" that contains the software "PackageName", "ApplicationName", and a "Justification".
2. Within the "package name" column provide the package name for Zoom, Spotify, and Skype, within the "application name" column list Zoom, Spotify, or Skype for the corresponding application, and for the "justification" column provide why the application poses a security risk to your Windows Workstation. (Hint: Use the `Get-AppxPackage` cmdlet to retrieve the Package Name of the installed prohibited software applications).
3. Download and install VS code using `choco`.
4. Open the PowerShell script from the previous activity in VS code, and erase any code within the file.
5. At the top of the file, define a variable named 'csvPath' that will hold the path to your CSV file, assuming the file is located on the user’s desktop. Hint: Use `$HOME` or `$env:USERPROFILE` instead of hardcoding the path to make this portable across different user profiles.
6. Bring in the contents of that CSV file using the `Import-Csv` cmdlet and storing its value in a variable named appList. Note: Each row in the CSV should represent one application with fields like PackageName, ApplicationName, and Justification.
7. Iterate through each application in the application list by using a foreach loop. Inside the loop, extract the relevant object properties from the current row of the CSV file, by assigning `$app.PackageName` to `$processName`, which helps identify the app in process lists or installs.
8. Also inside the loop,  assign `$app.ApplicationName` to `$displayName` and assign `$app.Justification` to `$reason`.
9. Add a blank line for readability using `Write-Host`.
10. Next,  print the application name and the justification you provided for why the app is being uninstalled to the screen so that whoever is running the script will know why the app is being flagged.
11. Use `Choc`o to verify whether the app is installed using `choco list --local-only` and piping its output to filter for the current app's name, storing the value inside a variable named "chocoList".
12. Create an `if-else` block, to check if a match is found in `$chocoList`.
13. Inside the `if` block run a try to uninstall the app cleanly using `choco`, and if the uninstall succeeds, let the user know.
14. Also inside the `if` block run a `catch` to catch any errors during the app install process and print an error message to the screen.
15. Inside the `else` block, if Choco didn’t manage the app, let the user know to perform a manual check.
16. (Optional) Before importing the CSV, it's a good idea to check if the file exists. Create an if statement to add a check using Test-Path to verify if the file at $csvPath exists. If it does not, display a message using Write-Host and stop the script with exit.
17. (Optional) Instead of informing the user to perform a manual check,  after confirming that Choco did not install the app, within a variable named "installed", use `Get-Package` pipped into `Where-Object` to check if the app is installed by other means. Match either `$displayName` or `$processName`.
18. (Optional) If `$installed` returns results, inform the user it’s still present, else if `$installed` is empty, inform the user that the app is not installed at all.

> While printing to the screen helps during testing, production scripts often write output to a log file to retain proof of actions taken—especially when responding to compliance issues.

#### Syntax for `foreach`, `if/else` and `try/catch`
```powershell
  
foreach ($variable_name in $iterable) {
    # insert code that will be execute for each iteration of the foreach loop
   
}

if (condition) {
        # insert code to be executed if condition is true here...
    }
    else {
       # insert code here that will be executed if the condition fails...
}

try {
    # insert code you want to try to execute here...
}
catch {
    # insert code you want to run if the "try" code fails...
}
```

<details closed>
<summary>my_first_PS_script.ps1</summary>

```powershell
# -------------------------------
# Prohibited Apps Removal Script
# Scenario: Corporate IT policy requires detection and removal of blacklisted software.
# This script reads a CSV list of prohibited applications, checks if they are installed,
# notifies the user, and attempts to uninstall them.
# -------------------------------

# Define path to the CSV file on the user's desktop
# CSV expected to have columns: PackageName, ApplicationName, Justification
$csvPath = "$HOME\Desktop\prohibited-apps.csv"

# Step 1: Verify the CSV exists before continuing
if (-Not (Test-Path -Path $csvPath)) {
    Write-Host "CSV file not found at $csvPath"
    exit
}

# Step 2: Load the list of blacklisted applications from the CSV file
$appList = Import-Csv -Path $csvPath

# Step 3: Loop through each entry in the prohibited app list
foreach ($app in $appList) {
    $processName = $app.PackageName      # Internal name used by the OS or package manager
    $displayName = $app.ApplicationName  # Human-readable name
    $reason = $app.Justification         # Why it's prohibited (for user awareness)

    Write-Host ""
    Write-Host "Checking for prohibited application: $displayName ($processName)"
    Write-Host "Justification: $reason"

    # Step 4: Check if the app is installed via Chocolatey
    # Chocolatey is a common package manager for Windows
    $chocoList = choco list --local-only | Select-String -Pattern "^$displayName"

    if ($chocoList) {
        # Step 5: Try to uninstall via Chocolatey if found
        try {
            Write-Host "Attempting to uninstall $displayName using Chocolatey..."
            choco uninstall $displayName -y
            Write-Host "$displayName uninstalled successfully via Chocolatey."
        } catch {
            Write-Host "Failed to uninstall $displayName via Chocolatey. Error: $_"
        }
    } else {
        # Step 6: If not found in Chocolatey, check via Get-Package
        Write-Host "$displayName is not managed by Chocolatey. Checking other installed packages..."

        $installed = Get-Package | Where-Object {
            $_.Name -like "*$displayName*" -or $_.Name -like "*$processName*"
        }

        if ($installed) {
            Write-Host "$displayName appears to be installed on the system, but was not installed via Chocolatey."
        } else {
            Write-Host "$displayName does not appear to be installed on this system."
        }
    }
}

```

</details>
