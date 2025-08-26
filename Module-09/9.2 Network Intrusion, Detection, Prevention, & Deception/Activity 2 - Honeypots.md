## Activity Objective
Students will install and configure masscanned on an Ubuntu server VM to simulate fake hosts and services, and use Kali Linux to interact with the honeypot using tools like nmap. This activity helps students understand how honeypots are used to detect reconnaissance and gather attacker behavior.

## Activity Scenario
An attacker slips into the campus during lunch and finds an unattended laptop that is unlocked and connected to the wireless network. They install and start a Kali virtual machine in bridged mode so it receives an address from the same router and sits on the same wireless network as employee devices. Inside Kali they run `ip a`, note the assigned address, the prefix such as slash twenty four, and the default gateway. This gives them the local subnet to target. They begin internal reconnaissance and launch a discovery scan against that subnet, planning to follow up with quick service probes.

What the attacker does not know is that the IT staff have reserved a small set of unused addresses and pointed them to a honeypot. The honeypot claims those decoy addresses on the local network and replies to basic probes. It answers address resolution and ping, and it responds to common service requests with safe, non sensitive replies. As the attacker scans, several decoys appear to be live hosts with open services, which draws attention away from production systems.

While the attacker interacts with these decoys, the honeypot records the source address, the targets, the ports and protocols, and the timing of activity. Alerts fire based on this pattern of probing from a new device on the wireless network. The security team investigates, removes the unauthorized device, and secures the unattended laptop. Students then review the honeypot log and any scan output to understand what the attacker discovered, which decoys were touched, what services were probed, how detection occurred, and which preventive controls would have reduced the likelihood of this scenario.

## Activity Instructions
1. Log into your Blue Team and run `sudo apt update` to refresh the package index so the system knows about the latest available packages.
2. Execute `mkdir honeypot && cd honeypot` to create a working folder named honeypot and move into it so all work stays in one place.
3. Run `git clone https://github.com/ivre/masscanned\` to download the Masscanned source code into the current folder.
4. Run `cd masscanned` to enter the project directory you just cloned.
5. Run `sudo apt install -y git cargo` to install Git and the Rust build tool Cargo so you can compile the program.
6. Run `cargo build -Znext-lockfile-bump` to compile Masscanned with a lock file compatibility flag that helps on some systems. If Cargo suggests it after the build, run `cargo fix -Znext-lockfile-bump --bin masscanned` to apply automatic fixes and then build again if needed.
7. Go to the folder that holds the compiled debug binary using `cd ~/honeypot/masscanned/target/debug`.
8. Run `for i in $(seq 200 219); do echo 192.168.50.$i; done > ips.txt` to create a file named "ips.txt" that lists twenty unused decoy addresses in your subnet. Replace 192.168.50 with your own subnet and choose numbers that are outside your DHCP scope and not in use. (Note: This implements a defensive security technique referred to as "dark space monitoring" in which an unused slice of the subnet is reserved to catch broadcast or sweep activity.)
9. Run `sudo ./masscanned --iface enp0s3 --self-ip-file ips.txt -v > honeypot.log` to start the responder on your network interface and make it answer for the decoy addresses listed in ips.txt. Replace "enp0s3" with your real interface name. The "-v" option increases log detail and the output is written to honeypot.log for later review.
10. Simulating the attacker from the scenario, on your Red Team VM, run `ip a` to confirm you are on the same local network as the honeypot and to note your IPv4 address, the prefix for example slash twenty four, and the default gateway.
11. On your Red Team VM, run an initial discovery scan with Nmap using the subnet you noted in step 10, for example `sudo nmap -sn 192.168.50.0/24`; replace the example with your actual subnet.
12. On your Red Team VM, using one of the identified IP addresses perform a Nmap service and version detection scan using `sudo nmap -sV -T4 -F 192.168.50.220`, replacing the example with an address used by your honeypot.
13. After the Nmap scan completes, stop Masscanned using `ctrl-c` in your terminals, then view the log with `more honeypot.log`.
14. Analyze the log to see which decoy IPs were probed and which protocols responded, then record your findings and complete the knowledge check.

### Knowledge Check
1. What's the best physical placement for an IDS on a network: inline or mirrored port?
    1. IDS
    2. Honeypot
    3. IPS
    4. Firewall
<details closed> <summary>Answer</summary>
  <p>A honeypot is a decoy host or service that lures activity for detection and research. IDS monitors, IPS blocks, and a firewall enforces traffic rules.</p>
</details>

2. A collection of coordinated honeypots that work together is called a...
    1. Honeypot
    2. Honeynet
    3. Honeytoken
    4. Honeywall
<details closed> <summary>Answer</summary>
  <p>A honeynet is multiple honeypots working as a system to provide richer telemetry.</p>
</details>

3. What is a honeytoken?
    1. A fake user account that provides admin access
    2. A decoy firewall that attackers can scan
    3. A sandbox used for malware detonation
    4. Bogus credentials planted to trigger an alert when used
<details closed> <summary>Answer</summary>
  <p>Honeytokens are planted data such as credentials or records that should never be used. Any use indicates misuse.</p>
</details>

4. Where is a common and safer place to position a honeypot?
    1. On the core switch of the production network
    2. On the domain controller
    3. Inside a segmented zone such as a DMZ or a dedicated VLAN
    4. On the internet gateway in inline mode
<details closed> <summary>Answer</summary>
  <p>Segmentation limits risk if the honeypot is compromised and reduces accidental impact on production.</p>
</details>

5. What is a primary risk of running a honeypot?
    1. It generates too few logs to be useful
    2. It prevents network segmentation
    3. It can become a pivot point if compromised
    4. It blocks legitimate traffic by default
<details closed> <summary>Answer</summary>
  <p>If an attacker gains control of the honeypot they may use it to move laterally.</p>
</details>

6. Match each term to the correct definition.

| Term       | Description                                                                 |
|------------|-----------------------------------------------------------------------------|
| Honeypot   | Several honeypots linked to look like a small network for broader observation |
| Honeynet   | A gateway that monitors and analyzes network interactions with honeypots     |
| Honeytoken | A decoy host or service that lures attackers and records their actions for analysis |
| Honeywall  | A planted data item such as a fake record or credential that alerts you if it is viewed or used |

<details closed> <summary>Answer</summary>
  <table border="1" cellpadding="6" cellspacing="0">
  <tr>
    <th>Term</th>
    <th>Description</th>
  </tr>
  <tr>
    <td>Honeypot</td>
    <td>A decoy host or service that lures attackers and records their actions for analysis</td>
  </tr>
  <tr>
    <td>Honeynet</td>
    <td>Several honeypots linked to look like a small network for broader observation</td>
  </tr>
  <tr>
    <td>Honeytoken</td>
    <td>A planted data item such as a fake record or credential that alerts you if it is viewed or used</td>
  </tr>
  <tr>
    <td>Honeywall</td>
    <td>A gateway that monitors and analyzes network interactions with honeypots</td>
  </tr>
</table>
</details>

7. In this activity, what is the main purpose of assigning unused addresses to the honeypot
    1. Reduce broadcast traffic on the subnet
    2. Expand the subnet without readdressing
    3. To detect sweeping scans and probes
    4. Speed up DHCP for client devices
<details closed> <summary>Answer</summary>
  <p>Reserving unused space for the honeypot lets you see who is sweeping or probing addresses.</p>
</details>

8. Why should the decoy addresses be outside the DHCP scope and confirmed unused before you run the honeypot?
    1. To avoid address conflicts and confusing ARP behavior with real hosts
    2. To make scans finish faster
    3. To allow the honeypot to route to the internet
    4. To hide the decoys from the attacker
<details closed> <summary>Answer</summary>
  <p>Using truly unused addresses prevents collisions and keeps the network stable while you collect clean telemetry.</p>
</details>

9. Within the scenario, once the attacker gained access to the employee's laptop, their 1st step was to perform a host discovery scan. What artifact(s) within your honeypot.log file would indicate this behavior?
<details closed> <summary>Answer</summary>
  <p>Within the log file you should see probes from a single source across many decoy addresses within a short window. In practice this appears as repeated ARP who has requests from the attacker MAC for each decoy address with matching ARP is at replies from the honeypot.</p>
</details>

10. Within the scenario, once the attacker gained access to the employee's laptop, their 1st step was to perform a host discovery scan. What artifact(s) within your honeypot.log file would indicate this behavior?
<details closed> <summary>Answer</summary>
  <p>The log shows traffic from a source IP targeting multiple common service ports on the honeypot,  which is a pattern characteristic of service enumeration or version probing. </p>
</details>
