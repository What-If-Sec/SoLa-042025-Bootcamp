## Activity Objectives

Students will use Wireshark to analyze PCAP (Packet Capture) data files to gain a deeper understanding of the IP (Internet Protocol) and TCP (Transmission Control Protocol) protocols. By examining various aspects of IP and TCP traffic, students will learn how these protocols operate, how they manage data transmission, and how to interpret their interactions within network communications.



## Activity Instructions

Complete the following tasks:
1. Open the [pcapng](https://drive.google.com/file/d/1JFKjLKvmtNPy2TS7wK8NMJhgWGBLk873/view) file from the Wireshark activity.
2. Apply the conversation between your computer and SOLA's web server as the filter (Hint: `Go to Statistics -> Conversations`, then `Apply as Filter -> Selected -> A <-> B`).
3. Then go to the "packet list pane", and sort the "time" in descending order.
4. Start the knowledge check below.

## Knowledge Check
1. At which layer of the OSI model are source and destination IP addresses defined and used for routing?
   1. Layer 1
   2. Layer 2
   3. Layer 3
   4. Layer 4
   5. Layer 5
   6. Layer 6
   7. Layer 7
<details closed>
<summary>Answer</summary>
Source and destination IP addresses are handled at Layer 3 of the OSI model, which is called the Network Layer.
</details>

2. What is the purpose of the TCP protocol in a network?
<details closed>
<summary>Answer</summary>
To provide reliable, ordered, and error-checked delivery of data between applications
</details>

3. At which layer of the OSI model are source and destination IP addresses defined and used for routing?
   1. To acknowledge the receipt of data from the other host
   2. To initiate a TCP connection by synchronizing sequence numbers
   3. To acknowledge the receipt of a connection request
   4. To gracefully terminate a TCP connection
<details closed>
<summary>Answer</summary>
To initiate a TCP connection by synchronizing sequence numbers
</details>

4. Which filter can be used to identify TCP connection requests?
   1. tcp.flags.syn == 1
   2. tcp.flags.fin == 1
   3. tcp.flags.ack == 1
   4. tcp.flags.rst == 1
<details closed>
<summary>Answer</summary>
tcp.flags.syn == 1
</details>

5. During the TCP 3-way handshake, which flag is used by the server to respond to the client’s initial SYN request?
   1. PSH
   2. SYN, ACK
   3. RST
   4. FIN
<details closed>
<summary>Answer</summary>
SYN, ACK
</details>

6. Which filter(s) can be joined together using '&&' to identify the server's response during a TCP connection handshake?
   1. tcp.flags.syn == 1
   2. tcp.flags.urg == 1	
   3. tcp.flags.ecn == 1
   4. tcp.flags.ack == 1
   5. tcp.flags.rst == 1
   6. tcp.flags.fin == 1	
<details closed>
<summary>Answer</summary>
<code> tcp.flags.syn == 1 && tcp.flags.ack == 1</code>
</details>

7. What is the purpose of the ACK flag in a TCP packet?
<details closed>
<summary>Answer</summary>
To acknowledge the receipt of data or connection-related packets
</details>

8. Which TCP flag is used to identify a TCP connection that has been gracefully terminated?
   1. FIN
   2. ACK
   3. RST
   4. PSH
<details closed>
<summary>Answer</summary>
FIN is used to gracefully terminate a connection.
</details>

9. Which TCP flag can be used to identify a TCP connection that has been abruptly terminated?
   1. PSH
   2. URG
   3. ECE
   4. RST
<details closed>
<summary>Answer</summary>
RST, is used to abruptly terminate a connection.
</details>

10. Why is the 3-way handshake important for reliable communication?
<details closed>
<summary>Answer</summary>
The 3-way handshake is crucial because it synchronizes communication between two endpoints, ensuring that both computers are ready to talk to each other. It does this by having the machines agree that they are ready to communicate as well as decide on the order in which data will be sent and received, so that nothing will get lost. This sets the stage for reliable, connection-oriented data communication.
</details>

11. How does TCP ensure that data is received in order and without loss?
<details closed>
<summary>Answer</summary>
TCP breaks data into small pieces called segments and puts a number on each one called a sequence number. The receiving computer uses those numbers to put the data back in the right order and if any pieces are missing or out of order, TCP will ask for them again by sending an acknowledgment (ACK) or waiting for a retransmission.
</details>

11. In your own words, how might understanding TCP help in a security, help desk, or sysadmin role?
<details closed>
<summary>Answer</summary>
Understanding how TCP works gives you a solid foundation for diagnosing and resolving many types of network issues. For example, by recognizing the normal behavior and traffic patterns of a TCP connection, you'll be better equipped to spot when something is off; such as when attacker tries to spoof a user, evade detection, or launch a DoS attack. This knowledge helps you distinguish legitimate network traffic from suspicious activity.
</details>
