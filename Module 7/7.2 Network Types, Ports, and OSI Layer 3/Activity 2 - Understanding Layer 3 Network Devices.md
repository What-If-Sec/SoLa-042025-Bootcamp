## Activity Objective
In this activity, students will demonstrate their understanding of Layer 3 devices, primarily routers and Layer 3 switches, including their role in IP-based networking, traffic routing, and segmentation. This quiz reinforces foundational concepts related to the OSI model and prepares students for future topics like VLANs, routing protocols, and firewalls.

## Activity Instructions
Use your notes, the lecture slides, as well as the internet to help you in completing the knowledge check below.

### Knowledge Check
1. At which OSI layer does a traditional router primarily operate?
   1. Layer 1
   2. Layer 2
   3. Layer 3
   4. Layer 4
<details closed>
<summary>Answer</summary>
Layer 3
</details>

2. What is the primary function of a router in a network?
   1. Boost wireless signals
   2. Route traffic between different IP networks
   3. Assign MAC addresses
   4. Translate domain names to IP addresses
<details closed>
<summary>Answer</summary>
Route traffic between different IP networks
</details>

3. True or False: Switches always operate at Layer 2 and cannot make IP-based forwarding decisions.
   1. True
   2. False
<details closed>
<summary>Answer</summary>
True, Layer 2 switches operate using MAC addresses, but Layer 3 switches can make decisions based on IP addresses, allowing for routing between VLANs.
</details>

4. What is the key difference between a Layer 2 switch and a Layer 3 switch?
   1. Layer 2 switches are wireless, Layer 3 switches are wired
   2. Layer 3 switches do not use MAC addresses, Layer 2 switches do
   3. Layer 2 switches are faster than Layer 3 switches
   4. Layer 3 switches can route traffic between different networks using IP addresses, Layer 2 switches need a router
<details closed>
<summary>Answer</summary>
Layer 3 switches can route traffic between different networks using IP addresses, Layer 2 switches need a router
</details>


5. Which device would you use to connect two different IP subnets together? Select all that apply.
   1. Layer 2 Switch
   2. Router
   3. Hub
   4. WAP
   5. Layer 3 Switch
<details closed>
<summary>Answer</summary>
A router can be used to connect and route traffic between different IP subnets, as well as a layer 3 switch which combines the functionality of a switch (Layer 2) and a router (Layer 3), allowing it to route traffic between subnets efficiently.
</details>

6. Which of the following can be used to segment a network into multiple broadcast domains? Select all that apply.
   1. Router
   2. Hub
   3. Wap
   4. Layer 2 Switch
   5. Layer 3 Switch
<details closed>
<summary>Answer</summary>
Each interface on a router creates a separate broadcast domain, and a layer 3 switch when configured with VLANs and routing capabilities, can segment broadcast domains like a router.
</details>

7. Explain why a network might use a Layer 3 switch instead of a router to route between VLANs.
<details closed>
<summary>Answer</summary>
A Layer 3 switch is able to route network traffic between VLANs just like a router, and  it is often faster and more efficient than using a router because L3 switches are optimized for high-speed internal switching, which can reduce network latency in large internal networks.
</details>

8. Match each function or behavior to the appropriate network device.
   
| Description                                                 | Device            |
|-------------------------------------------------------------|-------------------|
| Makes forwarding decisions based on MAC addresses           | Layer 3 Switch    |
| Routes traffic between different networks using IPs         | Layer 2 Switch    |
| Performs switching and routing functions in one device      | Router            |
<details closed>
<summary>Answer</summary>
<table>
  <thead>
    <tr>
      <th>Description</th>
      <th>Device</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Makes forwarding decisions based on MAC addresses</td>
      <td>Layer 2 Switch</td>
    </tr>
    <tr>
      <td>Routes traffic between different networks using IPs</td>
      <td>Router</td>
    </tr>
    <tr>
      <td>Performs switching and routing functions in one device</td>
      <td>Layer 3 Switch</td>
    </tr>
  </tbody>
</table>

<p>
  A Layer 2 switch operates at the Data Link layer and uses MAC addresses to forward traffic within a local network segment. 
  Routers operate at Layer 3 (Network layer) and use IP addresses to make decisions about forwarding traffic between different networks. 
  A Layer 3 switch combines the functions of a switch and a router, forwarding traffic within and between networks using both MAC and IP addresses.
</p>

</details>
