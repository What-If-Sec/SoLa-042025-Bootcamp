## Activity Objective

In this activity, students will use Nmap to scan and test firewall configurations they set up using firewalld. They will explore how firewall rules impact network visibility and connectivity. This hands-on activity will reinforce their understanding of firewall behavior and network scanning techniques.



## Activity Instructions

Log into your Red Team VM (Kali Linux or ParrotOS) and Target VM (Ubuntu Server or Metasploitable VM), then follow the instructions below. You can use the NMAP cheat sheet located [here](https://www.stationx.net/nmap-cheat-sheet/) for assistance.

> Remember: Performing Nmap scans on systems you do not personally own or have explicit written permission to scan is ILLEGAL and may be considered unauthorized access under computer crime laws. 

>
> Only scan devices you control or that your instructor has approved for classroom activities.

### Knowledge Check

1. Perform a simple unprivileged nmap scan of your target VM and record the results. Are your firewall rules set correctly correctly? Why or why not?
<details closed> <summary>Answer</summary> <code>nmap [blueteam-VM-IP]</code>
  <br><br><p>Because Apache was previously installed and SSL was enabled during the pre-work, and in the last activity the public zone was set to allow HTTP and HTTPS, port 80 and port 443 are open. This shows that the firewall rules are set correctly to enable web traffic.</p>
</details>

2. Perform a privileged nmap scan (stealth SYN scan) of your target VM and record the results. Then compare these results to the unprivileged scan previously perfgormed. What differences do you notice? Why does this new information appear?
<details closed> <summary>Answer</summary> <code>sudo nmap [blueteam-VM-IP]</code>
  <br><br><p>When Nmap is ran in unprivileged mode (i.e not using sudo) Nmap cannot send raw packets (like SYN-only packets), so by default is uses the TCP Connect scan (-sT). This uses the regular operating system networking calls to complete the full TCP handshake, something any normal user process is allowed to do, which is why no root privileges were required. 
    
When Nmap, is ran in privileged mode (i.e. using sudo) Nmap by default performs a stealh SYN scan, which sends raw IP packets containing only the SYN flag set. This is a "half-open" scan that stops after receiving the SYN-ACK, never completing the handshake. Sending raw packets directly requires root privileges because it bypasses the OS’s standard networking stack, and packets are captured directly from the network interface (like wireshark) which means it can see ethernet frame headers which includes the MAC address.</p>
</details>

3. Perform a service version detection scan to attempt to identify the version of the services running on each of the open ports of your target VM and record the results. What differences in the information provided do you notice? How could this information be used by IT admin and misused by hackers?
<details closed> <summary>Answer</summary> <code>sudo nmap -sV [blueteam-VM-IP]</code>
  <br><br><p>Compared to a basic scan, the service version detection scan (-sV) not only shows the open ports and their associated services, but also attempts to determine the exact version of the service running on each port. In this case, both port 80 (HTTP) and port 443 (HTTPS) are running Apache httpd 2.4.58 on Ubuntu. The scan also confirms the MAC address and the host information.
    
IT administrators can use this information to maintain an accurate inventory of running services, verify configurations, and quickly identify outdated software so they can apply patches or updates. However, hackers can also use the same details to search for known vulnerabilities (CVEs) affecting the identified versions, tailor exploits to the target’s specific software stack, and plan targeted attacks during reconnaissance.</p>
</details>

4. Perform an OS detection scan of your target VM and record the results. What differences in the information provided do you notice? How could this information be used by IT admin and misused by hackers?
<details closed> <summary>Answer</summary> <code>sudo nmap -O [blueteam-VM-IP]</code>
  <br><br><p>Unlike a simple scan, OS detection attempts to identify the target system’s operating system, device type, and kernel version. Here, Nmap guessed several Linux kernel ranges with varying probabilities, flagged the device type, and noted the results may be unreliable due to insufficient open and closed ports.

For IT administrators, OS detection is useful for verifying the actual operating systems and kernel versions running on their devices, ensuring they match intended configurations, and identifying any outdated systems that may require patches. For hackers, however, this same information can help narrow down which exploits or attack methods are most likely to succeed, allowing them to focus their efforts on vulnerabilities known to affect specific OS versions or device types.</p>
</details>

5.  Perform a port scan for the common remote access and web services abused by hackers like ssh, telnet, ftp, http, https, etc. Are your firewall rules set correctly correctly? Why or why not? What information is provided by the Nmap scan? How could this information be used by IT admin and misused by hackers?
<details closed> <summary>Answer</summary> <code>sudo nmap -p ssh,,ftp,telnet,http,https [blueteam-VM-IP]</code>
<br><br><p>When scanning a system with Nmap, ports show as open or filtered based on how the firewall is configured, and in this case the firewall was managed with firewalld. An open port means a service such as Apache on port 80 or 443 is actively listening and the firewall zone assigned to the interface is allowing traffic to that port. A filtered port means the firewall is blocking the probe packets so Nmap cannot confirm whether a service is listening. Firewalld uses zones to define which services and ports are allowed for each network interface. In this situation HTTP and HTTPS appear open because they are permitted in the active zone for the scanned interface, while SSH, FTP, and Telnet appear filtered because the home zone rules are blocking them. 
  
IT administrators can use this information to verify that firewall rules are correctly applied, confirm that only intended services are reachable, and detect any misconfigurations. Hackers could misuse the same scan results to identify which services are accessible for exploitation and which ones may require additional reconnaissance to bypass firewall restrictions.</p>
</details>

6. Perform an aggressive scan of your target VM and record the results. What differences in the information provided do you notice? How could this information be used by IT admin and misused by hackers?
<details closed> <summary>Answer</summary> <code>sudo nmap -A [blueteam-VM-IP]</code>
  <br><br><p>The aggressive scan combines multiple Nmap features, including service version detection, OS fingerprinting, script scanning, and traceroute. Compared to basic or single-purpose scans, it provides deeper details such as web server banners (Apache/2.4.58), the default page title, detailed OS version guesses, network distance, and traceroute hops. This is more comprehensive than standard or SYN scans, which may only show open ports and basic service names.
    
IT administrators can use the results to verify server configurations, confirm correct versions of web services, identify outdated or vulnerable software, and map the network path to the host. They can also ensure that only intended services are running and verify whether firewall and segmentation rules are working as expected.

An attacker could use this detailed data to identify specific software versions and match them to known vulnerabilities, helping to craft targeted exploits. Knowing the OS type, version, and running services allows for more precise attack planning, while traceroute information reveals potential intermediate devices or network paths to target.</p>
</details>


