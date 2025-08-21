# Activity Objectives

Students will use Wireshark to analyze DHCP operations within a provided PCAP file to identify network events and potential security incidents. Specifically, they will determine the type of attack occurring, such as DHCP starvation or rogue DHCP server attacks, and provide justification for their identification based on packet analysis.

Understanding how to analyze network traffic and identify DHCP-related attacks is crucial for cybersecurity professionals and network administrators. In real-world job scenarios, the ability to detect and mitigate such attacks helps ensure the integrity and availability of network services, preventing unauthorized access or denial of service to legitimate users. Proficiency with tools like Wireshark and the ability to recognize attack patterns are valuable skills for safeguarding organizational infrastructure.



## Activity Instructions

Complete the tasks below:
1. Open the pcap file located [here](https://drive.google.com/file/d/1oXSi7er4DaCNjnLsKUhn20pb96iZZqwF/view).
2. Begin the knowledge check.

## Knowledge Check

## Knowledge Check
1. What is the purpose of the DHCP protocol on a network?
   1. Translate IP addresses to MAC addresses
   2. Assign IP addresses to clients automatically
   3. Route traffic between VLANs
   4. Encrypt network traffic
<details closed>
<summary>Answer</summary>
DHCP dynamically assigns IP addresses and network configuration to clients, eliminating the need for manual configuration.
</details>

2. Which port numbers are commonly used for DHCP communication?
   1. 67
   2. 68
   3. 69
   4. 70
<details closed>
<summary>Answer</summary>
DHCP uses UDP port 67 for server-side communication and port 68 for client-side communication.
</details>

3. Match the following DHCP message types with their function:

| DHCP Message Type | Function |
|-------------------|----------|
| DHCP Discover     | Server responds with an available IP              |
| DHCP Offer        | Server acknowledges and finalizes the lease       |
| DHCP Request      | Client announces that it is looking for a server  |
| DHCP ACK          | Client asks for an IP address                     |

<details closed>
<summary>Answer</summary>
  <table border="1">
  <thead>
    <tr>
      <th>DHCP Message Type</th>
      <th>Correct Function</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>DHCP Discover</td>
      <td>Client announces that it is looking for a DHCP server</td>
    </tr>
    <tr>
      <td>DHCP Offer</td>
      <td>Server responds with an available IP address</td>
    </tr>
    <tr>
      <td>DHCP Request</td>
      <td>Client asks to use the offered IP address</td>
    </tr>
    <tr>
      <td>DHCP ACK</td>
      <td>Server acknowledges the request and assigns the IP</td>
    </tr>
  </tbody>
</table>
<p>
DHCP uses the DORA process (Discover, Offer, Request, Acknowledge) to assign IP addresses. It begins with the Discover message, where the client broadcasts a request to find available DHCP servers. The server then replies with an Offer message, proposing an IP address and lease details. The client responds with a Request message, indicating it wants to use the offered IP. Finally, the server sends an Acknowledge (ACK) message to confirm and complete the assignment of the IP address. This process ensures that devices can join the network without manual configuration.</p>
</details>

4. Which Wireshark display filter will display only DHCP packets.
   1. udp
   2. arp
   3. dhcp
   4. bootp
<details closed>
<summary>Answer</summary>
DHCP is a protocol extension of BOOTP, and Wireshark identifies both using the bootp filter.
</details>

5. Which filters need to be joined to display only DHCP Discover packets?
   1. bootp.option.type == 53 
   2. bootp.option.type == 54
   3. bootp.option.value == 1
   4. bootp.option.value == 3
<details closed>
<summary>Answer</summary>
<code>bootp.option.type == 53 && bootp.option.value == 1</code><br>
  <p>DHCP Discover messages are identified in Wireshark by DHCP option 53 (message type) with a value of 1.  So the filter is applied bootp.option.type == 53 && bootp.option.value == 1.</p>
</details>

6. How many DHCP Discover messages are shown in the PCAP?
   1. 10
   2. 11
   3. 12
   4. 13
<details closed>
<summary>Answer</summary>
10
</details>

7. Which filters need to be joined to show all DHCP packets where the source MAC address is a group address?
   1. dhcp
   2. eth.src[0] & 1 == 1
   3. bootp.option.value == 1
   4. bootp
<details closed>
<summary>Answer</summary>
<p>The filter <code>eth.src[0] & 1 == 1 && bootp</code> is used in Wireshark to find DHCP packets that were sent from group MAC addresses. The part eth.src[0] refers to the first byte of the source MAC address. The & 1 == 1 part is a bitwise operation that checks if the last bit in that byte is set to 1. In MAC addressing, if that last bit is 1, it means the address is a group address, like a multicast or broadcast address. Adding && bootp makes sure the results are only showing DHCP traffic, since DHCP messages are labeled as bootp in Wireshark.</p>
</details>

8. How many unique DHCP Discover messages are shown in the PCAP?
<details closed>
<summary>Answer</summary>
The PCAP file contains DHCP Discover messages from 6 unique spoofed MAC addresses.
</details>

9. Which filters need to be joined to show all DHCP packets where the source MAC address is a group address?
   1. 3b:09:60:5c:5e:eb
   2. d7:2f:cc:45:94:84
   3. 23:50:ce:7d:2c:c6
   4. 00:0c:29:ab:cd:ef
   5. 05:3e:fe:29:fb:80
   6. c1:95:ed:3d:91:18
   7. 15:d0:3e:3f:6a:af
   8. 10:0c:29:ab:cd:ef
<details closed>
<summary>Answer</summary>
3b:09:60:5c:5e:eb, d7:2f:cc:45:94:84, 23:50:ce:7d:2c:c6, 05:3e:fe:29:fb:80, c1:95:ed:3d:91:18, and 15:d0:3e:3f:6a:af the spoofed ones present in the DHCP Discover traffic.
</details>

10. How many DHCP Discover messages are shown in the PCAP?
     1. To hide from firewalls
     2. To consume all available IP leases on the DHCP server
     3. To encrypt DHCP traffic
     4. To scan for open ports
<details closed>
<summary>Answer</summary>
Spoofing many MAC addresses tricks the DHCP server into assigning all available IPs, leaving none for legitimate users.
</details>

11. How many DHCP Discover messages are shown in the PCAP?
     1. Rogue DHCP Server Attack
     2. DHCP Spoofing Attack
     3. DHCP Starvation Attack
     4. DHCP Flood Attack
<details closed>
<summary>Answer</summary>
In a DHCP starvation attack, an attacker sends a flood of DHCP Discover messages using many spoofed or group MAC addresses to quickly exhaust the available IP address pool. This prevents legitimate devices from obtaining an IP address. The use of invalid or group MAC addresses in Discover packets is a strong indicator of this type of attack.</details>

12. How many DHCP Discover messages are shown in the PCAP?
     1. IP addresses are reassigned to the wrong network
     2. The DHCP server switches to static IP assignment
     3. All devices automatically switch to IPv6
     4. Critical services may go offline
     5. New devices cannot connect to the network
<details closed>
<summary>Answer</summary>
Critical services may go offline and new devices cannot connect to the network due to a successful DHCP starvation attack
</details>

13. Which of the following is a common method to defend against DHCP starvation attacks?
     1. Use port mirroring on all switch interfaces
     2. Increase the DHCP lease time to one year
     3. All devices automatically switch to IPv6
     4. Disable all broadcast traffic on the network
     5.  Enable DHCP snooping on network switches
<details closed>
<summary>Answer</summary>
DHCP snooping helps protect the network by allowing only trusted ports to send DHCP server traffic and by filtering out rogue or excessive DHCP requests from unknown devices.
</details>

