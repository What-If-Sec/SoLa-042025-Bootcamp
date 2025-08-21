## Activity Objective

Students will learn how to use the Windows Management Instrumentation Command-line (WMIC) tool and understand its purpose in managing and querying Windows system information and configurations.  
By the end of the activity, students will be able to navigate WMIC, execute basic commands, and utilize it for various administrative tasks effectively.

## Activity Instructions
Follow the instructions below and make sure that Chrome, Spotify, and Skype are still running:
1. Assess the system's performance by retrieving CPU and memory information.  
<details closed>
<summary>Answer</summary>

```cmd
wmic cpu get name,NumberOfCores,NumberOfLogicalProcessors
wmic memorychip get capacity,speed
```
</details>

2. Identify resource-intensive processes and gather information about these processes.  
<details closed>
<summary>Answer</summary>

```cmd
wmic process get name,ProcessId,WorkingSetSize | sort
```
</details>

3. Query the system for the currently running processes and filter the results for Microsoft Edge and Chrome.  
<details closed>
<summary>Answer</summary>

```cmd
wmic process where "name='edge.exe'" get name,ProcessId,WorkingSetSize
wmic process where "name='chrome.exe'" get name,ProcessId,WorkingSetSize
```
</details>

4. Retrieve and analyze information about system services.  
<details closed>
<summary>Answer</summary>

```cmd
wmic service list brief
```
</details>

5. Query information about the Windows Update service (wuauserv).  
<details closed>
<summary>Answer</summary>

```cmd
wmic service where name="wuauserv" get /format:list
```
</details>

6. Review and verify configurations of user accounts on the system.  
<details closed>
<summary>Answer</summary>

```cmd
wmic useraccount list full
```
</details>
