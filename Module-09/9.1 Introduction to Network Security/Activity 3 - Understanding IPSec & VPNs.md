## Activity Objective:

Develop the skills to configure, analyze, and verify IPsec VPN tunnels, while understanding their critical role in protecting data in transit, enabling secure remote connectivity, and recognizing how these technologies can be both essential security tools and potential vectors for abuse. This knowledge is vital for IT and security professionals to ensure secure network operations, detect unauthorized tunnels, and respond effectively to misuse.



## Activity Instructions

Follow the instructions below:
1. Log into your Blue Team VM (Ubuntu Server)  and Red Team VM (Kali or Parrot) and on both VMs download and install `strongswan`.
2. Use `ip a` on both VMs to obtain your VM's IPv4 address and identify the network interface.
3. On both VMs edit the IPsec configuration file `/etc/ipsec.conf` replacing its contents with the content provided below, inserting the actual IPv4 address for your VMs.
4. Set the Pre-Shared Key on both VMs by editing the `/etc/ipsec.secret`s file and adding `[blue-team-VM-IP] [red-team-VM-IP] : PSK "CreateAStrongPassword"`.
5. On both VMs restart strongSwan by executing `sudo ipsec restart`
6. On your Blue and Red Team VMs bring up the VPN tunnel by executing `sudo ipsec up myvpn`.
7. Verify that your VPN started successfully by running `sudo ipsec statusall` on both VMs.
8. On your Red Team VM open Wireshark.
9. From your Red Team VM, `ping` your Blue Team VM's IP address to test the VPN tunnel.
10. If successful, the ICMP packets will now be encrypted. To confirm this, within wireshark you will observe Encapsulating Security Payload (ESP) packets being transmitted.
11. On your Blue and Red Team VMs, bring down the VPN by running `sudo ipsec down myvpn`.
12. Now `ping `your Blue Team VM from your Red Team VM again.
13. Once completed stop capturing network traffic within Wireshark.
14. Analyze and observe what changed in packet visibility after disabling IPSec. Which fields remained visible in encrypted traffic? Why is this important for both protecting and potentially hiding malicious activity?



#### Blue Team VM IPSec Configuration:
```
config setup
    charondebug="all"

conn myvpn
    keyexchange=ikev2
    authby=psk
    left=[insert-blue-team-VM-IP]
    leftsubnet=0.0.0.0/0
    right=[insert-red-team-VM-IP]
    rightsubnet=0.0.0.0/0
    auto=add
```

#### Red Team VM IPSec Configuration:
```
config setup
    charondebug="all"

conn myvpn
    keyexchange=ikev2
    authby=psk
    left=[insert-red-team-VM-IP]
    leftsubnet=0.0.0.0/0
    right=[insert-blue-team-VM-IP]
    rightsubnet=0.0.0.0/0
    auto=add
```

