## Activity Objectives

Students will utilize Searchsploit and the Exploit Database to analyze vulnerabilities identified from the previous Nmap vulnerability scan  in order to continue to simulate the vulnerability assessment phase of a penetration test. By the end of the activity, students will be able to:
1. Articulate the importance of analyzing vulnerabilities as part of the penetration testing process.
2. Accurately interpret the results of the Nmap vulnerability scan to identify potential security issues present on the Ubuntu Server VM.
3. Demonstrate proficiency in using Searchsploit to search for known vulnerabilities corresponding to the identified services and software.
4. Access the Exploit Database: Navigate the Exploit Database to gather detailed information about vulnerabilities, including their descriptions, impact, and available exploits.
5. Analyze the severity and exploitability of identified vulnerabilities, considering their potential impact on the security posture of the server.



## Activity Instructions

Log into your Kali or Parrot VM and complete the following:
1. Verify that exploit-db is installed on your machine by running `searchsploit -help`. If exploit-db is not installed, install it by running `apt update && apt install -y exploitdb`.
2. Ensure that the exploit database is up to date by running `searchsploit -u`.
3. Using the findings from your Nessus scan, use searchsploit to identify potential exploits you can leverage. For example, you can search for linux exploits by running `searchsploit linux`. 

> Note:
> 
> `searchploit -w <search-term>` will show the URL to access the exploit information.
> 
> `searchploit -x <exploit/ paper path>` opens the exploit or paper file in less so you can read without copying files into a local folder.

