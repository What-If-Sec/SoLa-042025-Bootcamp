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
  <br><br><blockquote>
    This is a strong spoofing threat description under the STRIDE methodology because it clearly identifies the spoofed entity—a coffee machine—which represents a trusted device within a secure network. By stating that an attacker could create a replica of the machine to gain unauthorized access, the description directly addresses the core concept of spoofing: impersonation to bypass trust boundaries. It also outlines the consequences of this unauthorized access, including sending malicious commands and disrupting normal operations, which demonstrates the potential impact of the spoofing attack. Furthermore, the description connects the technical threat to broader business risks such as compromised equipment, service disruptions, and reputational damage, illustrating how a spoofed device could be a gateway to further exploitation within a sensitive environment like a defense contractor’s network.
  </blockquote>

</details>

Coffee Maker Tampering Threat
<details closed>
<summary>Answer Key</summary>
An attacker could gain unauthorized physical or remote access to the coffee machine and modify it, resulting in the attacker being able to alter the coffee brewing process, change machine settings, or inject malware. If successful, the Defensive Contractor and  its employees will be impacted due to potential health risks (e.g., contamination from altered settings or burns), disrupted service, and equipment damage.
  <br><br><blockquote>
This is a strong Tampering threat description under the STRIDE model because it clearly illustrates the unauthorized modification of a system or its data, which is the essence of Tampering. The threat explains that an attacker could gain either physical or remote access to the coffee machine and alter its functionality—such as changing brewing settings, introducing unsafe behavior, or even injecting malware. This directly maps to tampering, which involves unauthorized changes to code, configuration, or operations. The description also provides concrete examples of what could be modified and the consequences, including health risks, service disruption, and hardware damage, which emphasize the real-world impact of a successful tampering attack. By linking the technical exploit to both safety and operational risks in a high-stakes environment like a defense contractor's facility, it effectively highlights the seriousness and relevance of the threat.
  </blockquote>
  
</details>

Coffee Maker Repudiation Threat
<details closed>
<summary>Answer Key</summary>
An attacker could exploit a lack of proper logging or secure audit trails in the coffee machine's system, resulting in the attacker being able to erase or alter  records or logs of commands, making it difficult to trace unauthorized actions or interactions with the machine. If successful, if there is a security incident due to a breach, it will be difficult to recover from security incidents, or identify who was responsible.
    <br><br><blockquote>
This is a strong Repudiation threat description under the STRIDE model because it directly addresses the core of what repudiation means: the ability to deny performing an action without accountability due to a lack of reliable records. The threat highlights that the attacker takes advantage of insufficient or insecure logging/audit mechanisms in the coffee machine’s system. This aligns perfectly with repudiation, which focuses on the failure to prove who did what in a system. It also explains the impact—logs could be erased or altered, making it hard to investigate incidents or attribute actions, which is critical in both security response and accountability. By showing how this can obstruct incident recovery and responsibility tracking, especially in a sensitive environment like a defense contractor, the threat effectively illustrates why repudiation vulnerabilities are dangerous and how they can be exploited.
  </blockquote>
</details>

Coffee Maker Information Disclosure Threat
<details closed>
<summary>Answer Key</summary>
An attacker could exploit a vulnerability in the coffee machine to gain unauthorized access to the machine's network connection, resultng in the attacker, gaining unauthorized access to sensitive data stored or transmitted by the machine, such as employee information, internal communications, or proprietary company data. If successful, the defense contractor, employees, and possibly government clients will be impacted by the exposure of classified or sensitive information, potentially leading to espionage, intellectual property theft, or compromise of national security.
    <br><br><blockquote>
This is a strong Information Disclosure threat description under the STRIDE framework because it directly addresses the risk of unauthorized access to sensitive data, which is the core of this threat category. The description explains that an attacker could exploit a vulnerability in the coffee machine to gain access to its network connection—a common attack vector for extracting information. It clearly outlines the types of data at risk, such as employee information, internal communications, and proprietary company data, which emphasizes the sensitivity and value of the exposed information. Additionally, the description effectively connects the breach to real-world consequences, including espionage, intellectual property theft, and even national security risks—especially relevant in the context of a defense contractor. This not only shows the technical exposure but also the operational and geopolitical impact, making it a comprehensive and impactful example of an information disclosure threat.
  </blockquote>
</details>

Coffee Maker DoS Threat
<details closed>
<summary>Answer Key</summary>
An attacker could target the coffee machine or the Wi-Fi network, flooding it with excessive requests, resulting in the attacker being able to disrupt the coffee machine's ability to receive orders or perform brewing functions. If successful, the employees and government clients will be unable to have coffee in office.
  <br><br><blockquote>
This is a good Denial of Service (DoS) threat description under the STRIDE framework because it clearly illustrates how an attacker can intentionally disrupt the availability of a system—a core aspect of DoS. The description identifies the target (the coffee machine or the Wi-Fi network it relies on) and the method (flooding it with excessive requests), which aligns with common DoS attack techniques. It also highlights the resulting impact: the coffee machine becomes unresponsive or unable to function, effectively denying service to its users. While the example is framed humorously—“employees and government clients will be unable to have coffee”—it still underscores a serious underlying issue: if a critical or widely used IoT device can be taken offline by simple network abuse, it reflects broader vulnerabilities in system availability, especially in high-security or high-dependence environments like a government facility. The threat also subtly hints at operational disruption and morale issues, which can cascade into larger organizational impacts.
  </blockquote>
</details>

Coffee Maker Elevation of Privilege Threat
<details closed>
<summary>Answer Key</summary>
An attacker can exploit vulnerabilities in the coffee machine’s network communication protocols, gaining unauthorized access to the device’s network functions, resulting in the attacker being able to interfere with or manipulate the machine’s interactions with other devices or systems on the same network, potentially bypassing security controls or gaining access to sensitive systems. If successful, the defense contractor, employees, and government clients will be impacted by the compromise of critical network infrastructure, unauthorized access to sensitive information, and potential disruption of operations or security breaches within the organization.
    <br><br><blockquote>
This is a strong Elevation of Privilege threat description under the STRIDE model because it clearly illustrates how an attacker could escalate from limited or no access to higher-level control within a system or network. It begins by identifying a realistic technical vector—vulnerabilities in the coffee machine’s network communication protocols—and shows how that can be exploited to gain unauthorized access to privileged network functions. This aligns directly with the essence of Elevation of Privilege: moving beyond intended permissions to perform actions reserved for more trusted users or systems.

The description also explains how this elevated access could be used to interfere with other systems, bypass security controls, or access sensitive systems, which highlights both the technical risk and the breadth of impact. Finally, it connects the threat to real-world consequences, including compromised network infrastructure, unauthorized access to sensitive data, and operational or security disruptions—critical concerns for a defense contractor handling sensitive or classified environments. Overall, it effectively shows how a low-privilege device like a coffee machine can become a pivot point for more serious intrusions, which is a classic and compelling example of Elevation of Privilege.
  </blockquote>
</details>
</details>

