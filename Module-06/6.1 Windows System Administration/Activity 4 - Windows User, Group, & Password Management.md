## Activity Objective

Students will learn to manage users, groups, and account settings in a Windows environment using the `net user`, `net localgroup`, and `net accounts` commands.  

By the end of the activity, students will be able to create and manage user accounts, assign users to groups, and configure password policies using these commands in the Command Prompt.

## Activity Scenario

You have been hired by Fudd Enterprises as a new Windows system admin on their IT support team.  
On your 1st day your manager asks you to help stand up two new teams, Mobile-Dev and Cloud-Dev, on the company's Windows server and add the hiring manager for each to their team's local group.  
After doing so, you are also instructed to set up a password policy on the server, setting a minimum length for passwords, the maximum age for passwords, and to force logoff after inactivity.

Six months later and you have been doing great at Fudd Enterprises; however, Sr. Leadership has decided to outsource the development of their cloud app.  
As a result, your team will have to remove the members of the Cloud-Dev team as well as delete the local group.

## Activity Instructions
Follow the instructions below:
1. Create two new users using `net user`.  
<details closed>
<summary>Answer</summary>

```cmd
net user devuser1 P@ssword1 /add
net user devuser2 P@ssword2 /add
```
</details>

2. Verify that each new user was created using `net user`.  
<details closed>
<summary>Answer</summary>

```cmd
net user
```
</details>

3. Query the current local groups on your Windows system using `net localgroup`.  
<details closed>
<summary>Answer</summary>

```cmd
net localgroup
```
</details>

4. View and record the members of each of the local groups on your system using `net localgroup`.  
<details closed>
<summary>Answer</summary>

```cmd
net localgroup "Administrators"
net localgroup "Users"
```
</details>

5. Create a new local group named "Mobile-Devs".  
<details closed>
<summary>Answer</summary>

```cmd
net localgroup "Mobile-Devs" /add
```
</details>

6. Create a new local group named "Cloud-Devs".  
<details closed>
<summary>Answer</summary>

```cmd
net localgroup "Cloud-Devs" /add
```
</details>

7. Add one of the users you created to the "Mobile-Devs" local group and the other to the "Cloud-Devs" local group.  
<details closed>
<summary>Answer</summary>

```cmd
net localgroup "Mobile-Devs" devuser1 /add
net localgroup "Cloud-Devs" devuser2 /add
```
</details>

8. Display the currently configured account policies on your machine using `net accounts`.  
<details closed>
<summary>Answer</summary>

```cmd
net accounts
```
</details>

9. Set the minimum length for passwords for user accounts to 8 using `net accounts`.  
<details closed>
<summary>Answer</summary>

```cmd
net accounts /minpwlen:8
```
</details>

10. Set the maximum password age for user accounts to 30 using `net accounts`.  
<details closed>
<summary>Answer</summary>

```cmd
net accounts /maxpwage:30
```
</details>

11. Set the system to force the user to log off after 5 minutes of inactivity using `net accounts`.  
<details closed>
<summary>Answer</summary>

```cmd
net accounts /forcelogoff:5
```
</details>

12. Verify that the password policy was set for the system using `net accounts`.  
<details closed>
<summary>Answer</summary>

```cmd
net accounts
```
</details>

13. Delete the user you added to the "Cloud-Devs" local group using `net user`.  
<details closed>
<summary>Answer</summary>

```cmd
net user devuser2 /delete
```
</details>

14. Verify that the user was deleted using `net user`.  
<details closed>
<summary>Answer</summary>

```cmd
net user
```
</details>

15. Delete the "Cloud-Devs" local group using `net localgroup`.  
<details closed>
<summary>Answer</summary>

```cmd
net localgroup "Cloud-Devs" /delete
```
</details>

16. Verify that the "Cloud-Devs" local group was deleted using `net localgroup`.  
<details closed>
<summary>Answer</summary>

```cmd
net localgroup
```
</details>

