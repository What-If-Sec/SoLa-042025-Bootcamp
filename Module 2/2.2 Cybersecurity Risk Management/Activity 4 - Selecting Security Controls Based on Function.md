## Activity Objective

The objective of this exercise is to enable students to identify and recommend effective security controls to mitigate the STRIDE threats identified in the coffeemaker DFD (Data Flow Diagram) element. Students will identify security controls to address the specific threats student's have identified and strengthen the system's security. 

This activity will help students develop critical skills in threat modeling, control selection, and security strategy, which are essential for their future careers in cybersecurity. By learning to analyze threats and recommend appropriate security measures, students will be better prepared for roles that require risk assessment, system hardening, and effective security design, positioning them as valuable assets in any cybersecurity team.



## Activity Instructions

Open Threat Dragon and for the coffee maker element you performed your threat analysis of identify any administrative, technical, or physical security controls you believe will help mitigate the identified security risks for both the Coffee Machine Manufacturer and the Defense Contractor

> Note: If you're having trouble brainstorming or identifying security controls look up best practices for securing IoT devices, such as the one's created by the IoT Security Foundation, NIST, etc.

##### You can compare the threat descriptions you created, with the one's below.

Coffee Maker Spoofing Threat Security Mitigations
<details closed>
<summary>Answer Key</summary>
Technical security controls would be best for mitigating against the spoofing threat; for example the machine maunfactuer should implement PKI certificates for mutual authentication and the TLS 1.3 protocol for sending data, while the defense contractor could put the machine in a dedeciated VLAN or subnet for IoT devices.
</details>

Coffee Maker Tampering Threat Security Mitigations
<details closed>
<summary>Answer Key</summary>
Physical security controls like tamper-evident seals should be implemented by the machine manufactuerer, while physical security controls like placing the coffee machines in employee-only areas where badge access is required or placing the coffee machines in locations where CCTV cameras can monitor them should be implemented by the defense contractor. 
  
<br>Furthermore, the defense contractor should implement administrative controls such as security training to educate their employees on the importance of securing IoT devices, recognizing tampering signs, and reporting suspicious activity; as well as develop a plan for responding to security incidents involving IoT devices, including containment, investigation, and recovery procedures.

</details>

Coffee Maker Repudiation Threat Security Mitigations
<details closed>
<summary>Answer Key</summary>
If the machine manufacturer should implement logging functinality that has the ability for the defense contractor to forward logs to a centralized logging server like a SIEM tool.
</details>

Coffee Maker Information Disclosure Threat Security Mitigations
<details closed>
<summary>Answer Key</summary>
The machine manufactuer should make suure that their device only uses secure network protocols that ensure the confidentiality, integrity, and availability of the data being stored and sent/ received by the device.
The Defense Contractor should implement firewall rules to restrict traffic to and from the coffee maker and deploy an Intrusion Detection and/or Prevention System to monitor network traffic.
</details>

Coffee Maker DoS Threat Security Mitigations
<details closed>
<summary>Answer Key</summary>
Since the machine is deployed within the contractor's network, it is their responsibility to ensure the machine is secure from DoS threats, so the Defense Contractor should implement technical security controls like a firewall in order to restrict traffic to and from the coffee maker. 
</details>

Coffee Maker Elevation of Privilege Threat Security Mitigations
<details closed>
<summary>Answer Key</summary>
If there are admininstrative privileges, the machine manufactuer should ensure that these privileges are restricted by the principle of least privilege and the account used to gain admin privileges uses a secure password.
The Defense Contractor should also use technical security controls like isolating the coffee machine on its own VLAN or dedicated subnet for IoT devices, and/or implement an admininstrative controls where the company follows a zero trust model as well as develops an incident response plan invovling breaches due to IoT devices.
</details>

