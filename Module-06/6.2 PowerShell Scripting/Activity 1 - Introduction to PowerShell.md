
## Activity Objective

Students will learn and practice using common PowerShell cmdlets that are frequently utilized by Windows System Administrators to manage and automate system tasks.  

By the end of the activity, students will be able to effectively use these cmdlets to perform various administrative tasks such as user and group management, system information retrieval, file and directory operations, and service management.

## Activity Instructions

Open PowerShell and execute the following cmdlets below.  
Remember to use the `Get-Help` cmdlet to retrieve more information about any PowerShell command and the parameters they accept.

#### PowerShell File & Directory Operations

1. Retrieve your current location within your PowerShell terminal using the `Get-Location` cmdlet.  
<details closed>
<summary>Answer</summary>

```powershell
Get-Location
```

**Observation:**  
This cmdlet shows the current working directory in your PowerShell session.
</details>

2. Navigate to your user's desktop using the `Set-Location` cmdlet.  
<details closed>
<summary>Answer</summary>

```powershell
Set-Location "$HOME\Desktop"
```

**Observation:**  
`$HOME` is equivalent to `$env:USERPROFILE` and is PowerShell-native.
</details>

3. Once in your user's desktop, create a new directory titled `"Activity-Files"` using the `New-Item` cmdlet. *(Hint: Use the `-ItemType` parameter).*  
<details closed>
<summary>Answer</summary>

```powershell
New-Item -Path "Activity-Files" -ItemType Directory
```

</details>

4. Create a file titled `"My1stPowerShellScript.txt"` on your user's Desktop using the `New-Item` cmdlet.  
<details closed>
<summary>Answer</summary>

```powershell
New-Item -Path "$HOME\Desktop\My1stPowerShellScript.txt" -ItemType File
```

</details>

5. Move the PowerShell script file you just created from your Desktop to the `"Activity-Files"` directory, using the `Move-Item` cmdlet.  
<details closed>
<summary>Answer</summary>

```powershell
Move-Item "$HOME\Desktop\My1stPowerShellScript.txt" "$HOME\Desktop\Activity-Files\"
```

</details>

6. Copy the `"Activity-Files"` directory to your Documents directory using the `Copy-Item` cmdlet.  
<details closed>
<summary>Answer</summary>

```powershell
Copy-Item "$HOME\Desktop\Activity-Files" "$HOME\Documents\" -Recurse
```

</details>

7. Delete the `"Activity-Files"` directory located on your desktop using the `Remove-Item` cmdlet.  
<details closed>
<summary>Answer</summary>

```powershell
Remove-Item "$HOME\Desktop\Activity-Files" -Recurse
```

</details>

8. Change to the new location of your `"Activity-Files"` directory using the `Set-Location` cmdlet. *(Hint: You just copied this directory to your documents folder.)*  
<details closed>
<summary>Answer</summary>

```powershell
Set-Location "$HOME\Documents\Activity-Files"
```

</details>

9. Rename `"My1stPowerShellScript.txt"` to `"My1stPowerShellScript.ps1"` using the `Rename-Item` cmdlet.  
<details closed>
<summary>Answer</summary>

```powershell
Rename-Item "My1stPowerShellScript.txt" "My1stPowerShellScript.ps1"
```

</details>

10. Use the `Set-Content` cmdlet to write to your PowerShell Script file `"# My 1st PowerShell script!!!"`.  
<details closed>
<summary>Answer</summary>

```powershell
Set-Content -Path "My1stPowerShellScript.ps1" -Value "# My 1st PowerShell script!!!"
```

</details>

11. Use the `Add-Content` cmdlet to append to your PowerShell script file `"# By: <insert your name here>"`.  
<details closed>
<summary>Answer</summary>

```powershell
Add-Content -Path "My1stPowerShellScript.ps1" -Value "# By: <insert your name here>"
```

</details>

12. Use the `Get-Content` cmdlet to view the content you've written and appended to your script file.  
<details closed>
<summary>Answer</summary>

```powershell
Get-Content -Path "My1stPowerShellScript.ps1"
```

</details>

---

#### PowerShell Identity Management

1. Use the `Get-LocalUser` cmdlet to retrieve information about the local user accounts that exist on your Windows workstation.  
<details closed>
<summary>Answer</summary>

```powershell
Get-LocalUser
```

</details>

2. Use the `-Name` parameter along with the `Get-LocalUser` cmdlet to filter for information about your user.  
<details closed>
<summary>Answer</summary>

```powershell
Get-LocalUser -Name "<YourUserName>"
```

</details>

3. Create a variable named "password", that will prompt the user to enter a password using the `Read-Host` cmdlet. Also, since the value entered will be the user's password, use the  `-AsSecureString` option to make sure the password is stored in a secure format and not shown while typing.
<details closed>
<summary>Answer</summary>

```powershell
$Password = Read-Host -AsSecureString "Enter password"

```
</details>

4. Use the `New-LocalUser` cmdlet to create a new local user account on your workstation and provide a description of the user account (e.g., test account). *(Hint: Use the `-Name`, `-FullName`, `-Password $Password`, and `-Description` parameters.)*  
<details closed>
<summary>Answer</summary>

```powershell
New-LocalUser -Name "TestUser" -FullName "Test User" -Password $Password -Description "Test account"
```

</details>

5. Confirm that the new local user account was created using the `Get-LocalUser` cmdlet.  
<details closed>
<summary>Answer</summary>

```powershell
Get-LocalUser -Name "TestUser"
```

</details>

6. Retrieve information about the local groups that exist on your workstation using the `Get-LocalGroup` cmdlet.  
<details closed>
<summary>Answer</summary>

```powershell
Get-LocalGroup
```

</details>

7. Use the `-Name` parameter along with the `Get-LocalGroup` cmdlet to filter for information about the `"Administrators"` local group.  
<details closed>
<summary>Answer</summary>

```powershell
Get-LocalGroup -Name "Administrators"
```

</details>

8. Use the `New-LocalGroup` cmdlet to re-create the `"Cloud-Devs"` local group and provide a description.  
*(Hint: Use the `-Name` and `-Description` parameters.)*  
<details closed>
<summary>Answer</summary>

```powershell
New-LocalGroup -Name "Cloud-Devs" -Description "Cloud development group"
```

</details>

9. Confirm that the new local group was created using the `Get-LocalGroup` cmdlet.  
<details closed>
<summary>Answer</summary>

```powershell
Get-LocalGroup -Name "Cloud-Devs"
```

</details>

10. Use the `Add-LocalGroupMember` cmdlet to add a user to the `"Cloud-Devs"` local group. *(Hint: Use the `-Group` and `-Member` parameters.)*  
<details closed>
<summary>Answer</summary>

```powershell
Add-LocalGroupMember -Group "Cloud-Devs" -Member "TestUser"
```

</details>

11. Confirm that the user has been added to the `"Cloud-Devs"` local group using the `Get-LocalGroupMember` cmdlet. *(Hint: Use the `-Group` parameter.)*  
<details closed>
<summary>Answer</summary>

```powershell
Get-LocalGroupMember -Group "Cloud-Devs"
```

</details>

12. Delete the local group you created using the `Remove-LocalGroup` cmdlet. *(Hint: Use the `-Name` parameter.)*  
<details closed>
<summary>Answer</summary>

```powershell
Remove-LocalGroup -Name "Cloud-Devs"
```

</details>

13. Confirm that the local group has been deleted using the `Get-LocalGroup` cmdlet.  
<details closed>
<summary>Answer</summary>

```powershell
Get-LocalGroup
```

</details>

14. Delete the local user account you created using the `Remove-LocalUser` cmdlet. *(Hint: Use the `-Name` parameter.)*  
<details closed>
<summary>Answer</summary>

```powershell
Remove-LocalUser -Name "TestUser"
```

</details>

15. Confirm that the local user account was deleted using the `Get-LocalUser` cmdlet.  
<details closed>
<summary>Answer</summary>

```powershell
Get-LocalUser
```

</details>

---

#### PowerShell System & Software Management

1. Retrieve detailed information about your Windows workstation using the `Get-ComputerInfo` cmdlet.  
<details closed>
<summary>Answer</summary>

```powershell
Get-ComputerInfo
```

</details>

2. Retrieve detailed information about the processes running on your system using the `Get-Process` cmdlet.  
<details closed>
<summary>Answer</summary>

```powershell
Get-Process
```

</details>

3. Use the `-Name` parameter with the `Get-Process` cmdlet to filter for and retrieve information about any processes of interest.  
<details closed>
<summary>Answer</summary>

```powershell
Get-Process -Name "explorer"
```

</details>

4. Retrieve detailed information about services on your workstation using the `Get-Service` cmdlet.  
<details closed>
<summary>Answer</summary>

```powershell
Get-Service
```

</details>

5. Retrieve information about the software applications that have been installed on your workstation using the `Get-AppxPackage` cmdlet.  
*(Remember you can use wildcards `*<App-Name>*` to filter for specific apps.)*  
<details closed>
<summary>Answer</summary>

```powershell
Get-AppxPackage
```

</details>

6. Use the `Select` cmdlet and a pipe to filter for the Name, PackageFullName, and Description of Skype & Spotify.  
*(Hint: `Get-AppxPackage *<App-Name>* | Select <property_names>`)*  
<details closed>
<summary>Answer</summary>

```powershell
Get-AppxPackage *Skype* | Select Name, PackageFullName, Description
Get-AppxPackage *Spotify* | Select Name, PackageFullName, Description
```

</details>
