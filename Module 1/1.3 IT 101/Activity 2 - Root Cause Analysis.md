## Activity Objectives
The objective of this activity is to equip students with essential skills and techniques for effectively troubleshooting technical issues across various devices and systems. By the end of the activity, students should be able to identify common technical problems, employ systematic troubleshooting methods, and apply critical thinking to resolve issues efficiently.

## Activity Instructions
After reading each scenario, read the information provided, analyze the root cause of the issue and provide a solution.

### Activity
#### Scenario #1:
**You are an IT support intern tasked with responding to IT help desk support tickets. You receive your 1st ticket.**

1. Go to the [help desk ticket](https://docs.google.com/document/d/1zauEigKnsgGybNV4AKWcSDZy7cR1-CcXcy2tI14-b8M/edit?usp=drive_link) and define the problem. Was the information provided by within the help desk support ticket useful? Why or why not?
<details closed>
<summary>Answer Key</summary>
The employee is experiencing a problem with Virtual Box, a hypervisor, when trying to set up a virtual machine. However, because of the vagueness of the title, lack of details about the error or circumstances that led to the issue, as well as  no log file, screenshots. etc. As a member of the IT support team the information provided in the ticket makes it hard to diagnose the issue.
</details>

2. After contacting the employee, you're able to get more information about the issue they are experiencing, [provided here](https://drive.google.com/drive/folders/1O9OmAb8HfgcrVxJk8uInp0MkTQeGNgG_?usp=drive_link).
3. Analyze the information you were able to collect. From where was information collected/ gathered? Choose all that apply.
    1.	Help Desk Ticket
    2.	Application Log File
    3.	Intrusion Detection System (IDS) Alert
    4.	Application Error Message
<details closed>
<summary>Answer Key</summary>
Help Desk Ticket, Application Log File, Application Error Message
</details>

4. Analyze the information that was collected. Re-define the problem the employee is experiencing.
<details closed>
<summary>Answer Key</summary>
The employee is experiencing a problem with Virtual Box due to trying to install deploy a Ubunto ISO file formatted for Windows x86-64 emulation, instead of amd64 ISO meant for a Mac User
</details>

5. Perform research using google to identify a solution for the employee.
<details closed>
<summary>Answer Key</summary>
The employee should download the correct ISO file from the Ubunto website meant for their Macbook, and retry.
</details>

#### Scenario #2: 
**EVO Enterprises, a promising startup, is eagerly preparing to launch its new website, showcasing innovative products and services to potential customers. However, on the day of the website launch, the company experiences a sudden and devastating network outage, disrupting operations and preventing users from accessing the website. As the IT support team at EVO Enterprises, it's your responsibility to investigate the root cause of the network outage, notify the incident response and security operations teams if necessary, and restore normal operations as quickly as possible.**

1. Go to the [help desk ticket & IT security signals](https://drive.google.com/drive/folders/1TpOQ9zpbaXjKuAMoupR8bGlV4jdYIIiN?usp=drive_link) and define the problem. Was the information provided by within the help desk support ticket useful? Why or why not?
<details closed>
<summary>Answer Key</summary>
The company is experiencing a concerning amount of traffic to the website coming from IP addresses that are apart of a known botnet. This information is very important as it also includes the IP addresses the used in the attack.
</details>

2. Analyse the information [provided here](https://drive.google.com/drive/folders/1O9OmAb8HfgcrVxJk8uInp0MkTQeGNgG_?usp=drive_link).
3. From where was information collected/ gathered? Choose all that apply.
    1.	Help Desk Ticket
    2.	Intrusion Detection System (IDS) Alert
    3.	Firewall Log File
    4.	Application Log File
<details closed>
<summary>Answer Key</summary>
Help Desk Ticket, Intrusion Detection System (IDS) Alert, Firewall Log File, Application Log File
</details>

4. What type of attack is being conducted?
    1.	Botnet
    2.	DoS Attack
    3.	DDoS Attack
    4.	Remote Access Trojan
<details closed>
<summary>Answer Key</summary>
DDoS Attack
</details>

5. After stopping the attack, your Senior Leadership want to review any lessons that can be learned from the attack. What are the best practices for reducing the risk of a DDoS attack.
<details closed>
<summary>Answer Key</summary>
Implement an incident response plan, network and endpoint security monitoring, load balancing, and rate limiting using firewalls, HTTP headers, etc.
</details>


