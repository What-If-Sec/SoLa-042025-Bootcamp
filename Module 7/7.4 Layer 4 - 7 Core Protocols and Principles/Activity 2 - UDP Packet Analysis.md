## Activity Objective

This activity helps students build a foundational understanding of the User Datagram Protocol (UDP) by analyzing packet-level data in Wireshark. Understanding how UDP works is critical for roles in IT support, networking, and cybersecurity. By completing this activity, students will gain hands-on experience with real network traffic and develop practical skills in protocol analysis. This supports career-readiness for roles such as help desk technician, SOC analyst, or system administrator, where recognizing and interpreting transport-layer traffic is essential for troubleshooting and securing networks.



## Activity Instructions

Download the [pcapang](https://drive.google.com/file/d/1Dh_MnEqiOUBTU7t4FcrhgS_VPkzQKGyn/view) file and then complete the knowledge check.

## Knowledge Check
1. What is the main purpose of the UDP protocol?
   1. To break data into encrypted chunks
   2. To route packets through the internet
   3. To guarantee delivery of data and maintain connections
   4. To transmit data quickly without requiring a connection
<details closed>
<summary>Answer</summary>
UDP is a connectionless protocol that sends data without establishing a session or ensuring delivery, which makes it fast but less reliable.
</details>

2. What makes UDP a “connectionless” protocol?
<details closed>
<summary>Answer</summary>
UDP's lack of a  handshake or connection setup defines it as connectionless protocol, as UDP sends data without establishing a session or waiting for acknowledgments from the receiver.
</details>

3. Which of the following best describes how UDP delivers data?
   1. It waits for the receiver to acknowledge each packet
   2. It sends data immediately without checking for delivery
   3. It establishes a session before sending data
   4. It uses handshakes to keep the connection open
<details closed>
<summary>Answer</summary>
UDP transmits data without waiting for confirmation, which speeds up communication.
</details>

4. Open wireshark and load the provided .pcapang file.  Locate the first UDP packet and record the following: source IP, destination IP, source port, destination port.
<details closed>
<summary>Answer</summary>
Source IP: 139.133.204.176, Destination IP: 139.133.204.183, Source Port: 32768, Destination Port: 1234
</details>

5. Does UDP include any flags like TCP (SYN, ACK, FIN)?
   1. Yes, but they are hidden in the payload
   2. Yes, but only for retransmissions
   3. Only for special protocols/ applications
   4. No, UDP does not use flags
<details closed>
<summary>Answer</summary>
No, UDP does not use flags
</details>

6. Why might some applications choose to use UDP instead of TCP?
<details closed>
<summary>Answer</summary>
Because UDP is faster and simpler, applications that can tolerate some data loss often prefer it to avoid the delays introduced by TCP’s connection setup and retransmission mechanisms.
</details>

7. What information does UDP provide at Layer 4 to help the receiver know where to send the data once it arrives?
   1. Source IP Address
   2. Source Port
   3. Destination IP Address
   4. Destination Port
<details closed>
<summary>Answer</summary>
Source and Destination Port numbers are used by the receiving system to deliver the data to the correct application or service.
</details>

8. Which of the following characteristics BEST describes the User Datagram Protocol (UDP)?
   1. A connectionless protocol that ensures reliable delivery using sequencing and acknowledgments
   2. A connection-orientated protocol that transmits data without guaranteeing delivery or order
   3. A connectionless protocol that offers low-latency communication by sending data without connection establishment
   4. A connection-orientated protocol that transmits data  using sequence numbers and acknowledgments
<details closed>
<summary>Answer</summary>
UDP is a connectionless protocol that does not use handshakes, acknowledgments, or retransmissions. It is faster and has lower overhead than TCP, making it ideal for real-time applications like VoIP or streaming, where some data loss is acceptable.
</details>
