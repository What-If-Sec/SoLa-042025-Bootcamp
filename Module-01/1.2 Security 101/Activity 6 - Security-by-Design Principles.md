## Activity Objective(s)
The objective of this activity is to familiarize students with principles to design secure systems, products, etc. By analyzing a simulated cyber attack scenario, students identify which security design principle should be implemented to reduce the risk of the identified exploit.


## Activity Instruction(s)
Follow the instructions below:
1. Answer the knowledge check questions by identifying which security-by-design principle(s) would help reduce the risk of the cyber attack from occurring. 

### Knowledge Check
1. Alice, a project manager, shares a folder containing sensitive financial reports and strategic plans with her team members. Bob, a disgruntled employee who recently resigned, still has access to the shared folder. Bob maliciously decides to leak the sensitive documents to a competitor for personal gain. Despite leaving the company, Bob retains access to the shared folder due to the lack of stringent access controls.
    1. Least Common Mechanism, access should be restricted to shared resource
    2. Least Privilege, access to shared resource should be limited
    3. Economy of Mechanism, a more simple process should be implemented
    4. Fail-Safe Defaults, employee account should be locked after termination
<details closed>
<summary>Answer Key</summary>
Least Privilege & Fail-Safe Defaults
</details>
       
2. An attacker was able to subvert the bank's firewall and gain access to a banking employee's workstation by sending them a phishing email containing malicious attachments.Leveraging the compromised workstation, the attacker installs keylogging malware to capture the teller's login credentials and monitor their activities. The attacker then remotely accesses the institution's internal banking system, which lacks proper authentication and authorization mechanisms. The attacker then initiates an unauthorized fund transfers from multiple customer accounts to offshore accounts controlled by the attacker. As the transactions bypass traditional security controls due to compromised employee credentials, they go undetected until customers report suspicious activity.
    1. Separation of Duties, transferring funds should be a banker or account managers responsibility
    2. Complete Mediation, access to the customer's account should be authenticated and authorized
    3. Fail-Safe Defaults, the server should shutdown once a breach is detected.
    4. Psychological Acceptability, the employee should be aware of the risk of phishing attacks
<details closed>
<summary>Answer Key</summary>
Seperation of Duties & Fail-Safe Defaults
</details>
       
3. An attacker researches the target organization and identifies key employees responsible for financial transactions and system access. The attacker impersonates a senior executive or IT support technician and sends convincing emails to the selected employees, requesting urgent action (e.g., resetting passwords, disclosing sensitive information) to address a supposed security threat or system issue. Leveraging social engineering techniques the attacker manipulates targeted employees into complying with their requests without questioning their legitimacy. Two of the employees unwittingly provide the attacker with credentials and sensitive corporate data, believing they are following legitimate instructions from the Executive.The attacker is then able to gain unauthorized access to critical systems, exfiltrates sensitive data causing financial loss and reputational damage to the organization.
    1. Defense in Depth, multi-factor authentication, and network security monitoring should be implemented to reduce the risk of this attack.
    2. Psychological Acceptability, security training should be provided to bring awareness to the risk of phishing attacks
    3. Fail-Safe Defaults, Fail-Safe Defaults, the systems should shutdown once a breach is detected.
    4. Least Common Mechanism,  separate accounts for different system processes to prevent privilege escalation.
<details closed>
<summary>Answer Key</summary>
DiD, Psychological Acceptability, Least Common Mechanism
</details>
       
4. A company runs an online e-commerce platform with a custom-built web application. Over time, as new features were added, the application became increasingly complex with multiple layers of code, third-party integrations, and internal services interacting with the platform. The application relies on several outdated and unnecessary components that were no longer actively maintained. Additionally, the web app used multiple libraries and frameworks, some of which had known vulnerabilities, but developers found it challenging to keep track of and patch all components because of the system’s complexity. An attacker performs open source intelligence gathering (OSINT) and discovers an authentication key for a forgotten and deprecated API endpoint vulnerable to remote code execution. Exploiting this vulnerability, the attacker gains unauthorized access to the application’s backend. Once inside, the attacker escalated privileges and managed to extract sensitive customer information, including credit card details and user passwords.
    1. Economy of Mechanism, remove deprecated and unused services as well as remove unnecessary code
    2. Separation of Duties, reduce developer access to code
    3. Fail-Safe Defaults, default denial of access to deprecated API endpoints
    4. Least Privilege, limit API access to specific roles or services
<details closed>
<summary>Answer Key</summary>
Economy of Mechanism, Fail-Safe Defaults, & Least Privilege 
</details>

