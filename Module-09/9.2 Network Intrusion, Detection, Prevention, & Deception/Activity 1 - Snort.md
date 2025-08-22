## Activity Objective

Students will complete a quiz designed to assess their knowledge of network security monitoring. The quiz will include various scenarios and questions that cover key concepts, tools, and techniques in network security monitoring. Through this activity, students will enhance their ability to identify and respond to security incidents, improving their overall understanding and readiness in network security practices.

## Activity Instructions
Complete the following instructions:
1. Log into your Ubuntu Server and install snort using its default configuration by running `sudo apt install snort -y`. Afterwards, complete the knowledge check below first, before moving to step 2!!!
2. Once the knowledge check is completed, log into your Ubuntu Server VM and edit the configuration file for snort to include local custom rules.
3. Create the following custom rules to detect TCP and UDP network scans: `alert tcp any any -> any any (flags:S; msg:"Possible SYN Scan"; sid:1000001; rev:1;)` and `alert udp any any -> any any (msg:"Possible UDP Scan"; sid:1000002; rev:1;)`.
4. Run snort on the correct interface through executing `sudo snort -A console  -c /etc/snort/snort.conf -i eth0`, replacing eth0 with the network interface for the internal network.
5. Log into your Red Team VM, and simulate an attacker performing active network reconnaissance  by running `sudo nmap -p ssh,ftp,telnet,http,https -A <blueteam-VM-IP>` using NMAP targeting your Ubuntu VM.
6. Monitor your Blue Team VMs terminal output for the alert message " Possible SYN Scan" and "Possible UDP Scan".
7. Once completed stop snort from running on your Blue Team VM.

> Note: If your Blue Team VM does not alert you to the network scanning attempts, change your network interface.

### Knowledge Check
1. Log into your Ubuntu Server and install snort using its default configuration. Afterwards, complete the knowledge check below first!!!
<details closed> <summary>Answer</summary><code>sudo apt install snort -y</code>.</details>

2. Once the knowledge check is completed, log into your Ubuntu Server VM and edit the configuration file for snort to include local custom rules.
<details closed> <summary>Answer</summary>
  <p>Before editing the local.rules file to include custom rules:
  <code>sudo nano /etc/snort/snort.conf</code>.
Once inside the file, make sure that the following line is present so that Snort loads your local custom rule file: <code>include $RULE_PATH/local.rules</code>
</details>

3. Create the following custom rules to detect TCP and UDP network scans: `alert tcp any any -> any any (flags:S; msg:"Possible SYN Scan"; sid:1000001; rev:1;)` and `alert udp any any -> any any (msg:"Possible UDP Scan"; sid:1000002; rev:1;)`.
<details closed> <summary>Answer</summary>
  <p>Edit the local.rules file by executing:
  <code>sudo nano /etc/snort/rules/local.rules</code>.
Once inside the file, add the custom rule</code>
</details>

4. Run snort on the correct interface through executing `sudo snort -A console -c /etc/snort/snort.conf -i eth0`, replacing eth0 with the network interface for the internal network.
5. Log into your Red Team VM, and simulate an attacker performing active network reconnaissance  by running `sudo nmap -p ssh,ftp,telnet,http,https -A <blueteam-VM-IP>` using NMAP targeting your Ubuntu VM.
6. Monitor your Blue Team VMs terminal output for the alert message " Possible SYN Scan" and " Possible UDP Scan".
7. Once completed stop snort from running on your Blue Team VM.

> Note: If your Blue Team VM does not alert you to the network scanning attempts, change your network interface.

### Knowledge Check
1. What are the two main differences between a firewall and an IDS/ IPS system?
<details closed> <summary>Answer</summary>A firewall is designed to block or allow traffic based on defined rules. It actively prevents unauthorized access. While an IDS  is designed to monitor and detect suspicious or malicious activity and IPS is designed to monitor and prevent malicious activity. Furthermore, a firewall usually is placed on the network perimeter while an IDS/IPS is typically placed inside the network.</details>

2. What's the best physical placement for an IDS on a network: inline or mirrored port?
    1. Inlined
    2. Mirrored Ports
<details closed> <summary>Answer</summary>An IDS is a passive monitoring system, so placing it on a mirrored port allows it to observe and analyze traffic without interfering with the flow. This setup ensures the IDS can detect suspicious activity across the network without becoming a point of failure or slowing down traffic. In contrast, inline placement is used for an IPS (Intrusion Prevention System), which actively blocks threats.</details>

3. Define each part of the following Snort alert: `alert icmp any any -> any any (msg:"ICMP Detected"; sid:1000001; rev:1;)`
<details closed> <summary>Answer</summary>The Snort rule <code>alert icmp any any -> any any (msg:"ICMP Detected"; sid:1000001; rev:1;)</code> is designed to generate an alert when any ICMP traffic is detected, regardless of source or destination. <br>
<ul> <li>The rule starts with <code>alert</code> which specifies the action Snort should take in this case to trigger an alert</li> <li>The protocol <code>icmp</code> indicates that the rule applies specifically to ICMP traffic such as ping requests</li> <li>The <code>any any -&gt; any any</code> portion defines the source and destination IP addresses and ports with <code>any</code> meaning it matches all addresses and ports although ports are not applicable to ICMP this format is required</li> <li>The arrow <code>-&gt;</code> indicates the direction of traffic from source to destination</li> <li>Inside the parentheses are the rule options <code>(msg:"ICMP Detected"; sid:1000001; rev:1;)</code> sets the alert message assigns a unique Snort rule ID with custom rules typically starting at 1000000 and defines the rule revision number for tracking changes</li> <li>Altogether this rule alerts on any ICMP traffic observed on the network and logs it with a descriptive message and identifier</li> </ul></details>

4. What's the best physical placement for an IDS on a network: inline or mirrored port?
    1. Pattern-Based Detection
    2. Signature-Based Detection
    3. Anomaly-Based Detection
    4. Behavior-Based Detection
<details closed> <summary>Answer</summary><p>Intrusion detection systems mainly use two techniques. Signature based detection looks for known attack patterns, like an antivirus checking for viruses it already recognizes. Anomaly based detection looks for unusual activity that does not match normal behavior, which can help catch new or unknown threats.</p></details>

5. What type of IDS establishes its rules using a baseline?
<details closed> <summary>Answer</summary><p>An anomaly based intrusion detection system works by establishing a baseline of what is considered normal activity on a network or host. This baseline is created by monitoring typical traffic patterns, system processes, and user behavior over time. Once the baseline is established, the IDS continuously compares ongoing activity against it. If the activity aligns with the baseline, it is treated as normal, but if the activity deviates significantly, it is flagged as suspicious or potentially malicious. This approach differs from a signature based IDS, which relies on known attack patterns or signatures rather than a learned baseline.</p></details>

6. What's the best physical placement for an IDS on a network: inline or mirrored port?
    1. True
    2. False
<details closed> <summary>Answer</summary>
  <p>True, signature-based IDS systems rely on known attack patterns or signatures to detect threats. Because zero-day attacks are new and their signatures are not yet known, signature-based systems typically cannot detect them, making them ineffective against such threats.</p>
</details>

7. When used together, which should be placed farthest from the data: a firewall, an IDS, or an IPS?
    1. IDS
    2. IPS
    3. Firewall
<details closed> <summary>Answer</summary><p>When used together, the firewall should be placed farthest from the data, followed by the intrusion prevention system (IPS), and then the intrusion detection system (IDS).

The firewall acts as the first line of defense, sitting at the network perimeter to block or allow traffic based on predefined rules. This prevents obvious malicious or unwanted traffic from even entering deeper into the network. The IPS is positioned behind the firewall, closer to the protected systems, where it actively analyzes and blocks suspicious traffic that may have passed through the firewall. Finally, the IDS is typically placed parallel to the traffic flow (not inline like the IPS) and closer to the data or critical systems. Its job is to monitor, log, and alert administrators about potentially malicious activity.

By layering them this way, an IT team can maximize security.</p></details>

8. What part of this Snort alert is the "rule header"? And what is its purpse? And what is its purpose?
alert tcp any any -> any any (flags:S; msg:"Possible Nmap SYN Scan"; sid:1000002; rev:1;)`
<details closed> <summary>Answer</summary>
  <p>The rule header is the part of the Snort rule that comes before the parentheses and defines the matching criteria, which is <code>alert tcp any any -> any any".</code></p>
</details>

9. Analyze the following Snort rule designed to detect an Nmap TCP SYN scan: `alert tcp any any -> any any (flags:S; msg:"Possible Nmap SYN Scan"; sid:1000002; rev:1;)` Breakdown and explain the purpose of each part of the rule.
<details closed> <summary>Answer</summary>
  <p>The Snort rule <code>alert tcp any any -> any any (flags:S; msg:"Possible Nmap SYN Scan"; sid:1000002; rev:1;)</code> is designed to detect possible Nmap SYN scans. 
    
<ul> 
  <li>The action <code>alert</code> tells Snort to generate an alert when the rule conditions are met.</li> 
  <li>The protocol being monitored is <code>tcp</code> meaning the rule applies to TCP traffic.</li>
  <li>The portion <code>any any -&gt; any any</code> indicates that the rule will match traffic from any source IP and port to any destination IP and port in a forward direction.</li>
  <li>The <code>flags:S;</code> option specifies that the rule should match TCP packets with only the SYN flag set which is typical of an Nmap SYN scan also known as a &quot;half-open&quot; scan.</li>
  <li>The <code>msg</code> field provides the alert message in this case <code>Possible Nmap SYN Scan</code> which helps the analyst quickly identify the nature of the alert.</li> 
  <li>The <code>sid:1000002;</code> is a unique Snort rule ID for identifying this specific rule with values over one million typically reserved for custom or local rules.</li> 
  <li>Finally <code>rev:1;</code> indicates the revision number of the rule which is used to track changes over time.</li> </ul>
  </p>
</details>

10. What's the best physical placement for an IDS on a network: inline or mirrored port?
      1. Packet Logger
      2. Inline
      3. Network IDS
      4. Sniffer
<details closed> <summary>Answer</summary><p>Snort can operate in several modes depending on the goal of the deployment. In sniffer mode, it simply captures and displays packets in real time, which is useful for quickly observing network traffic. In packet logger mode, Snort records packets to disk for later analysis, providing a way to study traffic patterns or suspicious activity after the fact. When configured as a network intrusion detection system (NIDS), Snort passively monitors copies of traffic on the network and raises alerts if malicious patterns are detected, but it does not interfere with the flow of traffic. In contrast, in inline mode, Snort acts as an intrusion prevention system (IPS) by being placed directly in the traffic path, allowing it not only to detect but also to actively block or drop malicious packets in real time.</p></details>

11. What are the key differences between an Intrusion Detection System (IDS) and an Intrusion Prevention System (IPS)?
      1. An IDS is passive, while an IPS is active monitoring
      2. An IDS is deployed inline with network traffic, while an IPS is out-of-band
      3. An IPS can prevent attacks in real time, while an IDS only alerts administrators
      4. An IPS can prevent attacks in real time, while an IDS only alerts administrators
<details closed> <summary>Answer</summary><p>An IDS is considered a passive system as it detects and reports, while an IPS is proactive, as it detects and reacts. Thus, when a threat is detected an IPS can respond to the threats in real time by dropping packets or blocking traffic; while the IDS will only generate an alert. For this reason,  an IPS is deployed inline (directly in the traffic path) to stop threats, while an IDS is out-of-band, to monitor a copy of the traffic passively. And since an IPS is inline, it can introduce some latency, while an IDS will not typically affect network performance because it’s not in the direct traffic path.</p></details>

12. True or False: An IOA is "proactive" and an IOC is "reactive."
      1. True
      2. False
<details closed> <summary>Answer</summary><p>True, na Indicator of Attack (IOA) represents the behavior or intent of an attacker—actions that occur in real time or leading up to an attack. IOAs help detect and stop an attack while it's happening.

An Indicator of Compromise (IOC) refers to evidence that an attack has already occurred, such as malicious files, registry changes, or unusual network traffic. IOCs are used after the fact during investigation or incident response.</p></details>

13. True or False: An IPS is physically connected "inline" with the flow of traffic, processes entire subnets of data, and requires more robust hardware.
      1. True
      2. False
<details closed> <summary>Answer</summary><p>True, na Indicator of Attack (IOA) represents the behavior or intent of an attacker—actions that occur in real time or leading up to an attack. IOAs help detect and stop an attack while it's happening.

An Indicator of Compromise (IOC) refers to evidence that an attack has already occurred, such as malicious files, registry changes, or unusual network traffic. IOCs are used after the fact during investigation or incident response.</p></details>

14. In a default Snort installation on Ubuntu, which directory and file are custom Snort rules typically added to?
      1. `/usr/local/snort/snort.rules`
      2. `/etc/snort/rules/custom.rules`
      3. `/opt/snort/snort.conf`
      4. `/etc/snort/rules/local.rules`
<details closed> <summary>Answer</summary><p>In a default Snort installation on Ubuntu, custom rules are typically added to the file: <code>/etc/snort/rules/local.rules</code>

The local.rules file is specifically intended for administrators to place their own custom rules so they are not overwritten during Snort updates.</p></details>

15. Which line must be present in the snort.conf file to ensure your custom rules in local.rules are used?
      1. `include /etc/snort/local.rules`
      2. `include $RULE_PATH/local.rules`
      3. `include /etc/snort/snort.rules`
      4. `include $RULE_PATH/snort.rules`
<details closed> <summary>Answer</summary><p>In the /etc/snort/snort.conf file, you must include the following line to ensure that Snort loads and applies your custom rules from local.rules: <code>include $RULE_PATH/local.rules</code>
</p></details>

16. What does the following snort command do?
<code>sudo snort -c /etc/snort/snort.conf -i eth0 -A console</code>
<details closed> <summary>Answer</summary><p>This snort command executes snort in Network Intrusion Detection System (NIDS) mode, which is its alerting mode. In this mode, Snort uses the configuration file (snort.conf), loads the local.rules file, and evaluates traffic against detection rules.

By running Snort in NIDS mode with a command such as <code>sudo snort -c /etc/snort/snort.conf -i eth0 -A console</code> (substituting the correct network interface for eth0), ensures that any defined rules, whether targeting scans, exploits, or protocol anomalies, are evaluated against incoming packets so alerts are triggered and logged whenever matching traffic is detected.</p></details>
