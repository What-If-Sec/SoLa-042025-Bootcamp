## Activity Objectives

The objective of this exercise is to familiarize students with cyber threat modeling methodologies, specifically Microsoft's STRIDE framework, through the analysis of potential cyber threats facing a coffee company and its customers.

By the end of this activity, students should be able to:

Define the components of Microsoft's STRIDE threat modeling methodology.Identify potential threats to the confidentiality, integrity, and availability of data and systems within a company's infrastructure.Evaluate the impact of identified threats on both the company and its customers.

## Activity Instructions

1. Read the activity scenario.
2. Download the [coffee maker JSON file](https://drive.google.com/drive/folders/1uu_2z0zsHuHucA1yn9KInpTZg5dmlKKv?usp=sharing)  and open the threat model in Threat Dragon.
3. Click edit and put your first and last name as the owner.
4. Select the Coffee Maker element and begin identifying the threats for that element per STRIDE.


> #### Threat Descriptions should have the following format:
> An attacker can [describe how the attacker will exploit the potential security risk], resulting in the attacker being able [describe the results of the exploit]. If successful, the [list affected parties] will be [describe the impact to the consumer, system, or system owner].

## Activity Scenario

Welcome to the future of coffee! The Defense Contracting Company you work for has installed a fully automated coffee shop in the office where all orders are placed through a mobile app and brewed by "smart" coffee machines. These machines are connected to the store's Wi-Fi and controlled by the app, allowing you to place and customize your order with ease. As you enter the coffee shop, your mobile app connects to the store’s system, and the waiters (the coffee machines) start preparing your beverage according to your preferences.

While the experience is smooth and efficient, there are potential cybersecurity risks to consider. For example, the app and coffee machines communicate over the store’s Wi-Fi, which might be vulnerable to attacks like network eavesdropping or device spoofing. How secure are your coffee orders? Are the coffee machines immune to unauthorized access or manipulation? Could attackers disrupt the system by sending fraudulent orders, or worse, manipulate the machine to cause harm?

In this scenario, you will assess the security of the automated coffee shop using the STRIDE methodology to identify potential security threats to the Wi-Fi network, app, and coffee machines.

##### You can compare the threat descriptions you created, with the one's below.
Coffee Maker Spoofing Threat
<details closed>
<summary>Answer Key</summary>
An attacker could create a replica (spoofed) coffee machine, resulting in the attacker being able to gain unauthorized access to the Defense company's network, send malicious commands, or interfere with the coffee machine's normal operations. If successful, the Defensive Contractor and  its employees will be impacted by service disruptions, compromised equipment, loss of customer trust, and the potential for further attacks on the broader network.
</details>

Coffee Maker Tampering Threat
<details closed>
<summary>Answer Key</summary>
An attacker could gain unauthorized physical or remote access to the coffee machine and modify it, resulting in the attacker being able to alter the coffee brewing process, change machine settings, or inject malware. If successful, the Defensive Contractor and  its employees will be impacted due to potential health risks (e.g., contamination from altered settings or burns), disrupted service, and equipment damage.
</details>

Coffee Maker Repudiation Threat
<details closed>
<summary>Answer Key</summary>
An attacker could exploit a lack of proper logging or secure audit trails in the coffee machine's system, resulting in the attacker being able to erase or alter  records or logs of commands, making it difficult to trace unauthorized actions or interactions with the machine. If successful, if there is a security incident due to a breach, it will be difficult to recover from security incidents, or identify who was responsible.
</details>

Coffee Maker Information Disclosure Threat
<details closed>
<summary>Answer Key</summary>
An attacker could exploit a vulnerability in the coffee machine to gain unauthorized access to the machine's network connection, resultng in the attacker, gaining unauthorized access to sensitive data stored or transmitted by the machine, such as employee information, internal communications, or proprietary company data. If successful, the defense contractor, employees, and possibly government clients will be impacted by the exposure of classified or sensitive information, potentially leading to espionage, intellectual property theft, or compromise of national security.
</details>

Coffee Maker DoS Threat
<details closed>
<summary>Answer Key</summary>
An attacker could target the coffee machine or the Wi-Fi network, flooding it with excessive requests, resulting in the attacker being able to disrupt the coffee machine's ability to receive orders or perform brewing functions. If successful, the employees and government clients will be unable to have coffee in office.
</details>

Coffee Maker Elevation of Privilege Threat
<details closed>
<summary>Answer Key</summary>
An attacker can exploit vulnerabilities in the coffee machine’s network communication protocols, gaining unauthorized access to the device’s network functions, resulting in the attacker being able to interfere with or manipulate the machine’s interactions with other devices or systems on the same network, potentially bypassing security controls or gaining access to sensitive systems. If successful, the defense contractor, employees, and government clients will be impacted by the compromise of critical network infrastructure, unauthorized access to sensitive information, and potential disruption of operations or security breaches within the organization.
</details>

