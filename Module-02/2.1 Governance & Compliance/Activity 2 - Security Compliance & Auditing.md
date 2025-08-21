## Activity Objective

In this activity students will look to understand the critical role of security governance and compliance in protecting sensitive data by analyzing a fictional organization’s policies, procedures, and systems against PCI DSS standards, identify compliance gaps, and propose actionable recommendations to enhance security and achieve compliance.

This activity will develop students’ analytical, collaborative, and problem-solving skills while reinforcing their understanding of regulatory requirements and the importance of aligning security practices with industry standards.



## Activity Instructions

Read the scenario, including PCI DSS reference guide as well as SecurePay's Compliance Documentation. Afterwards, answer the auditor's questions provided in the quiz.



### Activity Scenario

SecurePay Inc. is a financial technology startup specializing in online payment processing for small businesses. The company has rapidly grown over the past two years and is now preparing to demonstrate compliance with the Payment Card Industry Data Security Standard (PCI DSS) to gain the trust of clients and secure partnerships with major credit card providers.

SecurePay has around 50 employees, and hosts their infrastructure using Microsoft Azure hosted servers for payment processing and data storage. Also, within their offices they use Microsoft Office workstations that are running the latest version of Windows 11. Furthermore, their networks leverage a firewall and VPN for remote access. Due to their limited cybersecurity and IT staff, SecurePay relies heavily on their small IT team and an outsourced Managed Service Provider (MSP).

Despite these efforts, recently SecurePay was hit by a phishing attack targeting employee emails exposed sensitive internal communications but no customer data was compromised. So, to prepare for the upcoming audit, the team has uploaded all appropriate documentation to the drive located [here](https://drive.google.com/drive/folders/1I1TUnTKuowpIrFlJIsURcsJpu6CO0QMS?usp=sharing). 

## Activity:
### Auditor Questions
1. What are the 12 requirements for PCI DSS compliance?
<details closed>
<summary>Answer Key</summary>
<ol>
  <li>Install and maintain a firewall configuration to protect cardholder data</li>
  <li>Do not use vendor-supplied defaults for system passwords and other security parameters</li>
  <li>Protect stored cardholder data</li>
  <li>Encrypt transmission of cardholder data across open, public networks</li>
  <li>Use and regularly update anti-virus software or programs</li>
  <li>Develop and maintain secure systems and applications</li>
  <li>Restrict access to cardholder data by business need to know</li>
  <li>Assign a unique ID to each person with computer access</li>
  <li>Restrict physical access to cardholder data</li>
  <li>Track and monitor all access to network resources and cardholder data</li>
  <li>Regularly test security systems and processes</li>
  <li>Maintain a policy that addresses information security for all personnel</li>
</ol>
</details>

2. How is cardholder data encrypted at rest and in transit?
<details closed>
<summary>Answer Key</summary>
Cardholder data is encrypted in transit using TLS1.1 and at rest using AES-256. 
</details>

3. Is there a defined access control policy, and is it enforced? How do you enforce least privilege access?
<details closed>
<summary>Answer Key</summary>
Yes, least privilege is enforced through administrative or privvileged access being enabled for admin accounts.
</details>

4. Is the cardholder data environment (CDE) segmented from the corporate network?
<details closed>
<summary>Answer Key</summary>
Yes 
</details>

5. Can you demonstrate how encryption keys are stored and managed?
<details closed>
<summary>Answer Key</summary>
Yes
</details>

6. Can you demonstrate how encryption keys are stored and managed?
<details closed>
<summary>Answer Key</summary>
Hadware Security Module (HSM)
</details>

7. Can you demonstrate how encryption keys are stored and managed?
<details closed>
<summary>Answer Key</summary>
Hadware Security Module (HSM)
</details>

8. Has a penetration test been performed?
<details closed>
<summary>Answer Key</summary>
No
</details>

9. Is there evidence that the MSP is compliant to PCI DSS?
<details closed>
<summary>Answer Key</summary>
No
</details>

10. Are there any inconsistencies or gaps in policies like access control, encryption, and incident response?
<details closed>
<summary>Answer Key</summary>
<ol>
  <li>Access permissions are not reviewed regularly.</li>
  <li>Do not use vendor-supplied defaults for system passwords and other security parameters</li>
  <li>Protect stored cardholder data</li>
  <li>Outdated TLS version still in use for legacy systems.</li>
  <li>Training attendance was not mandatory for contractors.</li>
  <li>No evidence of PCI DSS-focused training for IT team.</li>
  <li>No formal agreement mandates PCI DSS compliance by the MSP.</li>
  <li>No audit or attestation report provided by the MSP.</li>
  <li>Non-compliance with PCI DSS requirement for annual penetration testing.</li>
  <li>Lack of internal oversight for log management and retention policies.</li>
  <li>No documented quarterly review of firewall and network configurations.</li>
</ol>
</details>   
