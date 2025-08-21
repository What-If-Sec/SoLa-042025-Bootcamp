## Activity Objective

In this activity, students will students will enhance their understanding of both IPv4 and IPv6 addressing by converting addresses to binary and hexadecimal formats and exploring various IP address classes and CIDR notations. Students will apply subnetting techniques to calculate subnet masks and determine the number of available subnets and hosts.



This quiz will also provide practical experience in solving subnetting problems, using tools or manual calculations to identify network and broadcast addresses



## Activity Instructions

Use your notes, the lecture slides, as well as the CIDR to IPv4 Converter and CIDR to IPv6 Converter online tools.

### Knowledge Check

1. Convert the IP address 192.168.1.10 to its binary equivalent.
   1. 11000000.10101000.00000000.00001010
   2. 11000000.10101001.00000001.00001011
   3. 11000000.10101000.00000001.00001001
   4. 11000000.10101000.00000001.00001010
<details closed>
<summary>Answer</summary>
11000000.10101000.00000001.00001010
</details>

2. Convert the IPv6 address 2001:0db8:85a3:0000:0000:8a2e:0370:7334 to its binary equivalent.
   1. 00100000 00000001 00001101 10111000 00000101 00101011 00000000 00000000 00001000 10101010 00000111 00000000 01110011 00110011
   2. 00100000 00000001 00001101 10111000 00000101 00101011 00000000 00000000 00001000 10100010 00000111 00000000 01110011 00110011
   3. 00100000 00000001 00001101 10111000 00000100 00101011 00000000 00000000 00001000 10100010 00000111 00000000 01110011 00110100
   4. 00100000 00000001 00001101 10111000 00000100 00101011 00000000 00000000 00001000 10101010 00000111 00000000 01110011 00110100
<details closed>
<summary>Answer</summary>
00100000 00000001 00001101 10111000 00000100 00101011 00000000 00000000 00001000 10100010 00000111 00000000 01110011 00110100
</details>

3. True or False: Private IP addresses are routable over the global Internet.
   1. True
   2. False
<details closed>
<summary>Answer</summary>
False, private IP addresses are not routable over the global Internet. They are reserved for use within local networks (such as homes, schools, and businesses).

To communicate over the Internet, devices using private IP addresses must use a router with Network Address Translation (NAT), which translates the private IP to a public IP.
</details>

4. Calculate the total number of usable hosts in the subnet masks of /18.
   1. 256
   2. 65,534
   3. 16,382
   4. 16,777,216
<details closed>
<summary>Answer</summary>
Number of hosts = 2^14  - 2 = 16,384 − 2 = 16,382 usable host addresses
</details>


5. Convert the numeric IP representation of 11000000101010000100010110010001 to decimal notation and determine if the IP address is a public or private address. 
   1. Public IP Address
   2. Private IP Address
<details closed>
<summary>Answer</summary>
192.168.69.145 falls within the 192.168.x.x range, thus it is a Private IP Address.
</details>

6. Convert the numeric IP representation of 00101001001011011011011000100000 to decimal notation and determine if the IP address is a public or private address.
   1. Public IP Address
   2. Private IP Address
<details closed>
<summary>Answer</summary>
Since 41.45.182.32 is not within the reserved private IP ranges, it is a public IP address
</details>

7. Determine the type of network address provided through the binary address: 100010001111011111000111011001010001101000110110
   1. Public IP Address
   2. Private IP Address
   3. MAC Address
<details closed>
<summary>Answer</summary>
The binary string has 48 bits, which means this is likely a MAC address, not an IP address. IPv4 uses 32 bits, and IPv6 uses 128 bits.
</details>

8. What is the purpose of subnetting?
   1. To divide a network into smaller, manageable subnets
   2. To increase the number of available public IP addresses
   3. To create larger IP addresses
   4. To replace IPv4 with IPv6
<details closed>
<summary>Answer</summary>
To divide a network into smaller, manageable subnets
</details>

9. True or False: IPv6 uses a class-based addressing scheme similar to IPv4.
   1. True
   2. False
<details closed>
<summary>Answer</summary>
IPv6 does not use a class-based addressing scheme like IPv4 did (with Class A, B, C, etc.). Instead, IPv6 uses a classless addressing system where addresses are assigned based on prefix lengths, similar to CIDR notation in modern IPv4 networks.
</details>

10. If you are given the CIDR notation 192.168.1.0/28, determine the range of valid IP addresses and the broadcast address.
      1. IP Range of 192.168.1.0 - 192.168.1.14, with a broadcast address of 192.168.1
      2. IP Range of 192.168.1.1 - 192.168.1.14, with a broadcast address of 192.168.15
      3. IP Range of 192.168.1.1 - 192.168.1.15, with a network address of 192.168.1.0
      4. IP Range of 192.168.1.0 - 192.168.1.15, with a network address of 192.168.1.1
<details closed>
<summary>Answer</summary>
In a /28 subnet, 192.168.1.0 is the network address, 192.168.1.15 is the broadcast address, and the valid usable IPs are 192.168.1.1 through 192.168.1.14.
</details>

11. Why are VLANs and Subnets often used together? Select all that apply.
      1. Assigning a unique subnet to that VLAN ensures that all devices within it share the same IP address range
      2. VLANs isolate traffic at Layer 2 (switching), preventing devices from different VLANs from directly communicating
      3. Subnets further allow for firewall rules, access control lists (ACLs), and routing policies at Layer 3
      4. A router or Layer 3 switch can route traffic between subnets/VLANs.
      5. Tools like ping and traceroute clearly show network boundaries if each VLAN has its own subnet
      6. As networks grow, keeping VLANs and subnets aligned makes it easier to add new network segments without disrupting existing configurations. 
<details closed>
<summary>Answer</summary>
VLANs and subnets are often used together because they provide both Layer 2 and Layer 3 network segmentation. Using a unique subnet for each VLAN keeps devices organized by IP range and makes it easier to manage, secure, and scale the network. VLANs isolate traffic within a switch, while subnets allow for routing, firewall rules, and access controls between VLANs. This setup also makes tools like ping and traceroute more effective for troubleshooting, and as the network grows, it’s easier to add new segments without disrupting what's already in place.
</details>

12. Which of the following best describes the difference between a VLAN and a subnet?
      1. A VLAN segments a network based on IP addresses, while a subnet segments based on MAC addresses
      2. VLANs and subnets are the same; they both segment the network using switches
      3. A subnet prevents devices from broadcasting, while a VLAN controls routing between networks
      4. A VLAN operates at Layer 2 to separate broadcast domains, while a subnet operates at Layer 3 to organize IP address ranges
<details closed>
<summary>Answer</summary>
A VLAN operates at Layer 2 to separate broadcast domains, while a subnet operates at Layer 3 to organize IP address ranges
</details>
