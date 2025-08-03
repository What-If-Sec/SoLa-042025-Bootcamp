## Activity Objectives

 Students will learn to use the ping and traceroute commands to diagnose and analyze network connectivity and performance. By performing hands-on exercises with these commands, students will:
- Understand how traceroute  is used to reveal how many routers your traffic passes through to reach a destination.
- Gain packet-level visibility into the ping and traceroute tools.
- Gain network troubleshooting skills by learning how to use traceroute and ping to identify where packets are dropped or delayed to diagnose latency, routing errors, or other network issues.



## Pre-Activity Instructions

For this activity you will need to have the instruction open in another browser outside of your VM. 
1. Within your VM close any open browser (Firefox, Chrome, etc.) prior to continuing.
2. Open your terminal, and install traceroute using `sudo apt install traceroute`. 

## Activity Instructions

Complete the following tasks below:
1. Launch a new session of Wireshark and start packet capture.
2. Use ping to ping the SOLA Foundation's website (https://www.thesolafoundation.org/) four times.
<details closed>
<summary>Answer</summary>
<code>ping -c 4 thesolafoundation.org</code>
</details>

3. Filter for icmp traffic in order to filter for the echo request and echo reply messages sent between your VM and Sola's web server.
4. Record your IP address (the source) and the IP address of Sola's web server (the destination).
5. Filter and isolate for echo request messages by applying the filter: `icmp.type == 8`.
6. Filter and isolate for echo reply messages by applying the filter: `icmp.type == 0`.
7. Execute traceroute to trace the network path to https://www.thesolafoundation.org.
<details closed>
<summary>Answer</summary>
<code>traceroute thesolafoundation.org</code>
</details>

8. Once completed, stop wireshark from capturing your network trarffic.
9. Locate each ICMP time exceeded message used by traceroute (each represents a hop in the route), by filtering for `icmp.type == 11 && icmp.code == 0`.
10. For each Time Exceeded message sent back by the routers when a packet's TTL expires, expand the IP layer to see the source IP (the router that sent the message), and compare it to the output of your traceroute, line by line.
11. Locate the packet containing the destination's reply by filtering for `icmp.type == 3 && icmp.code == 3` as by default traceroute uses UDP (a protocol we will learn about in the next Module) to trace network paths. As a result, this ICMP type and code confirms that the destination host was reached and traceroute was completed.
12. Open the browser in your VM, and use this online [Traceroute Mapping Tool](https://stefansundin.github.io/traceroute-mapper/),  by copying and pasting the results (from your terminal) of your traceroute into the website.
13. Click Map It.


Example traceroute results:
```
traceroute to 41.19.96.234 (41.19.96.234), 30 hops max, 60 byte packets
 1  _gateway (10.0.2.2)  0.117 ms  0.088 ms  0.081 ms
 2  192.168.1.1 (192.168.1.1)  1.764 ms  1.677 ms  1.623 ms
 3  * * *
 4  096-034-073-234.res.spectrum.com (12.34.56.234)  16.090 ms  16.960 ms  17.053 ms
 5  cts01nwnnga-tge-3-0-0.nwnn.ga.charter.com (12.34.78.239)  16.843 ms  16.852 ms  16.899 ms
 6  dtr01nwnnga-tge-0-1-0-6.nwnn.ga.charter.com (12.34.78.238)  16.933 ms  9.163 ms  14.229 ms
```
