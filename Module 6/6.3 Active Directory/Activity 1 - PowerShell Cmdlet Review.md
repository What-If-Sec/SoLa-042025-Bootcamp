## Activity Objectives

Students will demonstrate their understanding of fundamental PowerShell cmdlets and their usage by completing a quiz. The quiz will assess their ability to identify and use common cmdlets, understand their functions, and apply their knowledge to practical scenarios. By the end of the activity, students will:
1. Identify Cmdlets: Recognize and recall the purpose of various PowerShell cmdlets used for system management, file manipulation, and data handling.
2. Understand Cmdlet Functions: Understand the specific functions and parameters of each cmdlet, and know when and how to use them effectively.
3. Apply Knowledge: Apply their knowledge to practical situations by answering questions related to cmdlet usage and functionality.
4. Review and Reflect: Review their answers to understand any mistakes, reinforce correct knowledge, and clarify any misconceptions about PowerShell cmdlets.

## Activity Instructions
1. Complete the quiz individually, answering the questions related to the user and funciton of PowerShell cmdlets.
2. Use PowerShell documentation or help commands (Get-Help) if you need assistance.

### Knowledge Check
1. Which PowerShell cmdlet is used to list all the commands that are installed on the computer?
   1. `Get-Help`  
   2. `List-Command`  
   3. `Show-Command`  
   4. `Get-Command`  
<details closed>
<summary>Answer</summary>
<code>Get-Command</code>
</details>

2. What cmdlet allows you to move an item from one place to another?
   1. `Move-Item -Path "C:\path\to\File" -Destination "C:\newLocation\"`  
   2. `Transfer-Item  -Path "C:\path\to\File" -Destination "C:\newLocation\"`  
   3. `Copy-Item  -Path "C:\path\to\File" -Destination "C:\newLocation\"`  
   4. `Pull-Item  -Path "C:\path\to\File" -Destination "C:\newLocation\"`  
<details closed>
<summary>Answer</summary>
<code>Move-Item -Path "C:\path\to\File" -Destination "C:\newLocation\"</code>
</details>

3. Which cmdlet allows you to remove an item?
   1. `Drop-Item -Name "ItemName"`  
   2. `Remove-Item -Name "ItemName"`  
   3. `Delete-Item -Name "ItemName"`  
   4. `Erase-Item -Name "ItemName"`  
<details closed>
<summary>Answer</summary>
<code>Remove-Item -Name "ItemName"</code>
</details>

4. What cmdlets are used to manage processes in PowerShell? Select all that apply.
   1. `Get-Process`  
   2. `Stop-Process -Name "ProcessName"`  
   3. `Start-Process -Name "ProcessName"`  
   4. `Disable-Process -Name "ProcessName""`  
<details closed>
<summary>Answer</summary>
<code>Get-Process</code><br><code>Stop-Process -Name "ProcessName"</code><br><code>Start-Process -Name "ProcessName"</code>
</details>

5. What cmdlets are used to manage services in PowerShell? Select all that apply.
   1. `Service-Status -Name "ServiceName"`  
   2. `Get-Service`  
   3. `Start-Service -Name "ServiceName"`  
   4. `Stop-Service -Name "ServiceName"`  
<details closed>
<summary>Answer</summary>
<code>Get-Service</code><br><code>Start-Service -Name "ServiceName"</code><br><code>Stop-Service -Name "ServiceName"</code>
</details>

6. Which cmdlet is used to list all the items in a directory?
   1. `Get-Item`  
   2. `List-Item`  
   3. `Get-ChildItem`  
   4. `Get-Directory`  
<details closed>
<summary>Answer</summary>
<code>Get-ChildItem</code>
</details>

7. To create a new directory or file which cmdlet would you use?
   1. `Create-Item`  
   2. `New-Item`  
   3. `Make-Item`  
   4. `Add-Item`  
<details closed>
<summary>Answer</summary>
<code>New-Item</code>
</details>

8. What does the Get-Disk cmdlet do?
   1. Retrieve information about  your system. 
   2. Retrieve information about  the processes and services currently running on your system.
   3. Retrieve information about the applications installed on your system.
   4. `Retrieve information about the physical disks on your system.
<details closed>
<summary>Answer</summary>
Retrieve information about the physical disks on your system.
</details>

9. Which cmdlet can be used to retrieve and display events from the Windows event logs?
   1. `Get-WmiObject`  
   2. `Get-History`  
   3. `Get-WinEvent`  
   4. `Get-Logs`  
<details closed>
<summary>Answer</summary>
<code>Get-WinEvent</code>
</details>

10. Write a PowerShell cmdlet to get recent events from the system log.
<details closed>
<summary>Answer</summary>
<code>Get-EventLog</code> can be used, to be exact you can execute <code>Get-EventLog -LogName System -Newest 50</code>
</details>
