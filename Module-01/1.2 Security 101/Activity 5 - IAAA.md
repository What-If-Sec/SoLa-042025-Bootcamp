## Activity Objective(s)
The objective of this activity is to help students understand the IAAA principle (Identification, Authentication, Authorization, and Accountability) in cybersecurity. Through this activity, students will gain insight into the importance of each component of the IAAA principle in securing information systems and protecting sensitive data.

## Activity Instruction(s)
Follow the instructions below:
1.	Analyze each scenario and identify:
    - The asset,
    - If access was granted or rejected,
    - The subject,
    - The authentication mechanism, and
    - The authorization model being used within each scenario.

**Example Scenario:** 

Jessica Pjones is a marketing intern at Stark Industries, she wants to access a project server which contains the R&D project files. The project server is configured to require users to provide their username, password, as well as an access token. Furthermore, the server is configured to only provide access to individuals with a job title of “Software Developer” and are in the “R&D” department.

**Example Analysis:**
- Asset: R&D project file
- Access: Rejected
- Subject: Jessica Pjones
- Authentication Mechanism: MFA
- Authorization Model: ABAC

### Activity Scenarios
1.	Virgil Hawkins is a Finance Manager at Omega Technologies, in order to access his company's financial report, he has to login to their internal portal which is configured to provide him access since he is in the company's Finance department, is accessing the report within normal business operation hours, and is located in office. Once he logs in, he is able to download the report.
<details closed>
<summary>Answer Key</summary>
<ul>
    <li>Asset: Financial Report</li>
    <li>Access: Granted</li>
    <li>Subject: Finacial Manager</li>
    <li>Authentication Mechanism: Password</li>
    <li>Authorization Model: ABAC because after authentication access is authorized using Virgil's department, the time of access, and his location.</li>
</ul>
</details>

2.	Dr. Sarah Patel is a patient at Arkham Asylum. In order to get access to the patient record room, she would need to use a Doctor's badge and pass biometric authentication. Furthermore, Arkham's systems are configured to restrict access to this room and any computers to only Doctors and Nurses.
<details closed>
<summary>Answer Key</summary>
<ul>
    <li>Asset: Patient Records</li>
    <li>Access: Rejected</li>
    <li>Subject: Patient</li>
    <li>Authentication Mechanism: MFA (Badge and Biometric Scan)</li>
    <li>Authorization Model: RBAC because access is only granted to Doctors and Nurses. </li>
</ul>
</details>

3.	David Lee is an IT Tech that works for the ACME, he has a secret security clearance and is trying to gain access to the governments secure document repository. In order to gain access David has to provide the correct credentials as well as a security token. However, the system requires individuals to hold a top secret clearance  to access.
<details closed>
<summary>Answer Key</summary>
<ul>
    <li>Asset: Document Repo</li>
    <li>Access: Rejected</li>
    <li>Subject: IT Tech</li>
    <li>Authentication Mechanism: MFA (Password and Security Token)</li>
    <li>Authorization Model: MAC because access is granted/ rejected based on security classification . </li>
</ul>
</details>


4.	At Wayne Enterprises, the HR Manager, Selena Kyle, is the authorized user responsible for accessing and managing employee performance review data via single-sign-on (SSO) to the HR portal. As the HR Manager, Selena has full control over who can read the employee performance review data stored within the portal, and as a result restricts access to herself and select HR employees. 
<details closed>
<summary>Answer Key</summary>
<ul>
    <li>Asset: Employee Performance Reviews</li>
    <li>Access: Granted</li>
    <li>Subject: HR Manager & Employees</li>
    <li>Authentication Mechanism: SSO</li>
    <li>Authorization Model: DAC because the HR Manager is able to grant or reject employee access at their discretion. </li>
</ul>
</details>
