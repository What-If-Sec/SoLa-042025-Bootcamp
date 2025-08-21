
## Activity Objectives

Students will learn and practice essential Windows PowerShell commands to navigate and manage the Windows filesystem effectively.  
Through hands-on practice and scenario-based exercises, students will learn to create, move, copy, and delete files and directories, enhancing their command-line interface (CLI) skills essential for system administration and everyday computing tasks.



## Activity Instructions

1. Open **Command Prompt**. You can search for "cmd" in the Start Menu and open "Command Prompt".

2. Navigate to the system's root directory and list its contents.  
<details closed>
<summary>Answer</summary>

```cmd
cd C:\ && dir
```

**Observation:**  
Windows uses drive letters (e.g., `C:\`) unlike Linux which uses a single root `/`. `dir` is used in CMD to list directory contents.
</details>

3. Navigate to the Users directory and list its contents.  
<details closed>
<summary>Answer</summary>

```cmd
cd C:\Users && dir
```

**Observation:**  
Similar to `/home` in Linux, but includes system profiles like `Default` and `Public`.
</details>

4. Navigate to your Desktop directory and list its contents.  
<details closed>
<summary>Answer</summary>

```cmd
cd %USERPROFILE%\Desktop && dir
```

**Observation:**  
CMD uses `%USERPROFILE%` instead of `$HOME` in PowerShell or `~` in Linux.
</details>

5. Create a directory called "Class-Files" on the Desktop.  
<details closed>
<summary>Answer</summary>

```cmd
mkdir Class-Files
```
</details>

6. Display your name and redirect the output to a file named "MyFirstFile.txt".  
<details closed>
<summary>Answer</summary>

```cmd
echo Your Name > MyFirstFile.txt
```
</details>

7. View the contents of "MyFirstFile.txt".  
<details closed>
<summary>Answer</summary>

```cmd
type MyFirstFile.txt
```
</details>

8. Move "MyFirstFile.txt" to your Documents directory.  
<details closed>
<summary>Answer</summary>

```cmd
move MyFirstFile.txt %USERPROFILE%\Documents
```
</details>

9. Copy "MyFirstFile.txt" back to the "Class-Files" directory.  
<details closed>
<summary>Answer</summary>

```cmd
copy %USERPROFILE%\Documents\MyFirstFile.txt %USERPROFILE%\Desktop\Class-Files
```
</details>

10. Delete the copy of "MyFirstFile.txt" from the "Class-Files" directory.  
<details closed>
<summary>Answer</summary>

```cmd
del %USERPROFILE%\Desktop\Class-Files\MyFirstFile.txt
```
</details>

11. Delete the "Class-Files" directory.  
<details closed>
<summary>Answer</summary>

```cmd
rmdir %USERPROFILE%\Desktop\Class-Files
```
</details>

Let your instructor know once you have completed the activity.
