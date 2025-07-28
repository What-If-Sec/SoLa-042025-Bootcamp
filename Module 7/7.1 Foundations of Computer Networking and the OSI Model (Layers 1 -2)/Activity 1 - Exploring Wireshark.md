## Activity Objective

Get hands-on experience with Wireshark by capturing and exploring real network traffic on your Ubuntu VM. This activity is designed to help you become familiar with the Wireshark interface, understand how to start and stop a capture, and begin recognizing basic network traffic using filters. You’ll also be introduced to key networking terms that will be explained in more detail in future lessons.



### Key Terms to Know
We will learn what these terms mean in more detail in future lessons, but for now it’s important to know what they are so you can begin exploring network traffic using Wireshark.

- Protocol: A protocol is a set of rules for how data is sent and received between devices. Examples include HTTP (used for websites), DNS (used to look up website names), and ICMP (used for tools like ping).
- Port: A port is like a doorway on a device that handles specific types of communication. For example, web traffic usually goes through port 80 (HTTP) or 443 (HTTPS  also known as TLS).
- IP Address: An IP address is a unique number assigned to each device on a network. It allows devices to find and communicate with each other — like a digital home address for your computer.

## Activity Instructions:

1. Open a terminal in your Ubuntu VM.
2. Run `sudo apt update && sudo apt install wireshark -y` to install Wireshark. If asked, allow non-superusers to capture packets by selecting “Yes.”
3. Run `sudo apt install net-tools -y` to install the ifconfig tool (used to view your network settings). Write down your IP address. It usually looks like 192.168.x.x or 10.x.x.x.
4. Run `ifconfig` in the terminal to view your network interfaces.
5. Find an interface like eth0, ens33, or enp0s3 that shows an IP address next to inet.
6. Run `sudo usermod -aG wireshark $USER` to give your user permission to use Wireshark.
7. Run `newgrp wireshark` to apply the group change without restarting.
8. Run `wireshark &` to launch Wireshark.
9. In Wireshark, select the interface you found in step 5 and click “Start Capturing Packets.”
10. Open Firefox and visit https://google.com, and wait about 30 to 45 seconds to let traffic build up.
11. Click the red Stop button in Wireshark to stop the capture.
12. In the filter bar at the top, type `dns` and press Enter. This shows DNS traffic — requests to look up website names.
13. In the filter bar at the top, type `http` and press Enter. This shows unencrypted web traffic (if any is present).
14. In the filter bar at the top, type `tls` and press Enter. This shows secure HTTPS traffic.
15. In the filter bar at the top, type `icmp` and press Enter. This shows ping traffic — but since you didn’t run a ping, it should be empty.
16. In the filter bar at the top, type `ip.addr == <your_ip_address>` and press Enter. Replace your_ip_address with the one you wrote down. This filter shows all traffic involving your device.
17. In the filter bar at the top, type `udp.port == 53` and press Enter. This shows DNS traffic based on the port it uses (53).
18. In the filter bar at the top, type `tcp.port == 443` and press Enter. This shows HTTPS traffic by port.
19. Go to File > Save As and save your capture as first-capture.pcapng.
