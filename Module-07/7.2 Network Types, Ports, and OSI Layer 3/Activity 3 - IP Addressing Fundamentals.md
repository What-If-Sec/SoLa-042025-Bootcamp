## Activity Objective
This knowledge check will assess your understanding of the Internet Protocol (IP), including the purpose of IP addresses, differences between IPv4 and IPv6, and the structural formats of each version. 

Understanding IP addressing is a critical foundation for future networking topics such as subnetting, CIDR (Classless Inter-Domain Routing) notation, routing, and firewall configuration. A strong grasp of these basics will help you confidently apply more advanced concepts and troubleshoot real-world networking issues.



## Activity Instructions
Use your notes, the lecture slides, as well as the internet to help you in completing the knowledge check.

### Knowledge Check
1. What is the main purpose of the Internet Protocol (IP)?
   1. Encrypt data during transmission
   2. Provide a unique identity and routing method for devices on a network
   3. Monitor network traffic for threats
   4. Assign MAC addresses to devices
<details closed>
<summary>Answer</summary>
Provide a unique identity and routing method for devices on a network
</details>

2. Which of the following is a primary characteristic of a WLAN?
   1. 8 groups of 4 hexadecimal digits separated by colons
   2. 4 groups of alphanumeric characters separated by dots
   3. 4 octets written in decimal  separated by dots
   4. 4 groups of hexadecimal numbers between 0–255 separated by dots
<details closed>
<summary>Answer</summary>
4 octets written in decimal separated by dots
</details>

3. How many bits are in an IPv4 address?
   1. 16 bits
   2. 32 bits
   3. 64 bits
   4. 128 bits
<details closed>
<summary>Answer</summary>
An IPv4 address is made up of 4 octets (8 bits each) which equals 32 bits.
</details>

4. Which of the following is a valid example of an IPv4 address? Select all that apply.
   1. 192.168.1
   2. 300.45.22.10
   3. 122.168.256.1
   4. 162.168.1.1
<details closed>
<summary>Answer</summary>
Option "A" is invalid because IPv4 addresses must have four octets (e.g., x.x.x.x). This one only has three, so it is not valid. "B" because each octet in an IPv4 address must be in the range 0–255. 300 is out of range, so this is not valid.  "C" because similar to option B, 256 is out of range for an octet (max value is 255), making it invalid. This leaves "D" which has four octets, and all are within the 0–255 range, making it a correctly formatted IPv4 address.
</details>


5. What is the primary difference between IPv4 and IPv6?
   1. IPv6 is used only for wireless networks, while IPv4 is used for wired.
   2. IPv4 uses hexadecimal, while IPv6 uses binary
   3. IPv6 allows for many more unique addresses than IPv4
   4. IPv4 addresses are longer than IPv6 addresses
<details closed>
<summary>Answer</summary>
IPv6 allows for many more unique addresses than IPv4
</details>

6. Which of the following best describes the primary purpose of a MAN (Metropolitan Area Network)?
   1. 4 octets of decimal numbers separated by dots
   2. 8 octets of hexadecimal digits separated by colons
   3. 8 groups of 4 hexadecimal digits separated by colons
   4. 8 groups of 4 decimal numbers separated by colons
<details closed>
<summary>Answer</summary>
To connect users and devices within a city or metropolitan area.
</details>

7. How many bits are in an IPv6 address?
   1. 16 bits
   2. 32 bits
   3. 64 bits
   4. 128 bits
<details closed>
<summary>Answer</summary>
In IPv6, each of the 8 groups is 16 bits long, making the full IPv6 address 128 bits in total.
</details>

8. Which of these is a valid IPv6 address?
   1. 2001:db8:85a3::8a2e:370:7334
   2. 2001:85a3:0000:0000:8a2e:0370:7334:192.168.1.1
   3. 2001:0db8:85a3:0000:0000:8a2e:0370
   4. 2001:0db8:85a3:0000:0000:8a2e:0370:7334:abcd
<details closed>
<summary>Answer</summary>
Option "A" is valid and uses double colons (::) correctly to compress consecutive zero blocks. "B" mixes IPv6 and IPv4 formats improperly. "C" is incomplete (only 7 groups instead of 8 or an allowable :: abbreviation). "D" contains 9 groups, which exceeds the maximum allowed for IPv6.
</details>

9. Why was IPv6 introduced?
<details closed>
<summary>Answer</summary>
IPv6 was introduced to due to the fact that IPv4 addresses are limited and at risk of being exhausted. IPv6 solves this problem by providing a larger pool of IP addresses, which enables more devices to connect to the internet. Also, IPv6 includes features like simplified header formats and improved support for security and mobility.
</details>

10. True or False: Both IPv4 and IPv6 cannot exist on the same network.
    1. True
    2. False
<details closed>
<summary>Answer</summary>
IPv4 and IPv6 can coexist on the same network using a method called dual stack. In a dual stack configuration, devices are configured with both an IPv4 address and an IPv6 address. This allows them to communicate with both IPv4 and IPv6 systems, ensuring compatibility during the ongoing transition from IPv4 to IPv6.
</details>
