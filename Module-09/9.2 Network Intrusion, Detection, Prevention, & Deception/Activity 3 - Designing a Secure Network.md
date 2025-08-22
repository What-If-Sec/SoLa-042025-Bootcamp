## Activity Objectives:

The objective of this activity is to provide students with a practical and comprehensive understanding of network design principles by having you design a network for fictional companies of varying sizes. This activity aims to:
1. Enhance your ability to analyze requirements, select appropriate technologies, and address challenges related to network design, security, and scalability.
2. Help students gain experience in designing a network from scratch, incorporating various components such as internal networks, DMZs, firewalls, and more.



Activity Scenario

You’ve been hired by a mid-sized company to design their corporate network. The company requires a secure and scalable network architecture to support their day-to-day operations, while also protecting sensitive data from external threats. The network must serve 50 employees across two departments, support printers, and have secure web services accessible to the public.

Design Requirements:
- Internal Network: Employees should have access to internal services such as file servers, workstations, and printers. Departmental segmentation is needed to keep the IT and Finance teams separated.
- DMZ (Demilitarized Zone):  a network is a security zone that sits between an internal, trusted network and an external, untrusted network (such as the internet).
- Firewall: You need to place a firewall to protect the network by controlling inbound and outbound traffic between the internet, DMZ, and internal network.
- IDS/IPS: Implement an Intrusion Detection System (IDS) to monitor for suspicious activity and an Intrusion Prevention System (IPS) to block potential attacks.
- Routers & Switches: Include routers and switches to efficiently route traffic and connect devices within the network.Workstations: The internal network must support workstations for each employee and printers accessible by the department File Servers: Include a secure file server for internal use by each department. Ensure data is only accessible to authorized users
- Web Server:  A public-facing web server will host the company’s website and email services, and it must be accessible to the internet while maintaining security for internal resources.



## Activity Instructions:

Follow the instructions below, use tools like draw.io or Smart Draw to draw your network diagram.

#### Step 1: Network Topology Design
1. Build a network topology diagram that includes:
  - Internet: The external network where your public services will be accessible.
  - DMZ: Containing the web server and mail server which is accessible from the internet.
  - Internal Network: Segmented into VLANs for IT and Finance. Include at least one workstation, printer, and file server.
  - Router: Connecting the internal network to the internet through the external firewall.
  - Switches: Connecting devices within each network segment (both internal network and DMZ).
  - Network Security Mechanisms: Firewalls to segment DMZ from internet and internal network, an Intrusion Detection System (IDS), an Intrusion Prevention System (IPS), as well as honeypot.

#### Step 2: Label Network Components 
Clearly label each component on your network topology diagram (router, firewalls, DMZ, web server, file servers, workstations, printers, switches, etc.)

#### Step 3: Describe Traffic Flow 
Explain how data traffic flows within the scenarios using your network diagram:
1. An external user visiting the company’s website hosted on the web server in the DMZ.
2. An employee sending a print job to a department printer.

> Example Scenario: An IT employee sends an email to a vendor.
> 
> 1. The IT employee writes the message in the mail client on the IT VLAN. If an attachment is added from a shared folder, the workstation first pulls that file from the file server over the access switch inside the IT VLAN.
> 2. The mail client submits the message to the company mail server that lives in the DMZ
> 3. The path is workstation to access switch to the internal firewall. The internal firewall allows this flow, the inline IPS inspects it, and the traffic is forwarded through the DMZ switch to the DMZ mail server. The IDS sees a copy of this traffic from a span or tap and records it.
> 4. The DMZ mail server accepts the message, applies the local policy, then looks up the vendor domain mail exchanger in DNS. Afterwards, selecting a destination mail server over the internet.
> 5. The DMZ mail server opens an outbound connection to the vendor mail server on the internet. The packet path is DMZ mail server to DMZ switch to the external firewall and router. The inline IPS inspects the session.  The external firewall applies egress rules and usually performs network address translation.
> 6. The traffic then goes out to the internet and reaches the vendor mail server.

#### Step 3: Configuring Security
Describe the firewalld rules (ingress/ egress), snort IDS/IPS rules, and network segmentation strategies to secure:
- File servers from unauthorized access.
- Web server from DDoS attacks, and
- Internal network from malicious insider 

#### Step 4: Reflect
Answer the following questions:
1. Why did you place the router and firewalls in the locations you chose, and how does that placement control traffic between Internet, DMZ, and internal VLANs?
2. What risks are reduced by separating the DMZ from the internal network, and what risks remain?
3. Where did you place the honeypot(s), and what behavior do you expect it to capture in that location?
4. What visibility will the IDS have based on your tap or span choices, and what important traffic might it miss?
5. What traffic will the IPS be able to block without breaking normal business use, and why?
6. If one device failed in your design, which single failure would cause the most impact, and what is your plan to reduce that impact?
7. For an external user visiting the web server, which controls protect the server before the packet reaches the application, and which controls give you visibility after the packet reaches it?
8. For a print job from a workstation to a department printer, what prevents a device from another VLAN from sending to that printer, and how would you verify this with a simple test?
9. How could alerts from honeypot, IDS, and firewalls be correlated so that the team can move from signal to action, and who owns each action during an incident?
10. In each scenario from step 4, what evidence would appear first during an attack, and which system would produce that evidence?
   

### Deliverables
A report containing your network topology diagram that including all required components (web server in the DMZ, file servers, workstations, printers), an explanation detailing the network design, traffic flow, and security strategy, rules, etc., as well as a b brief outline of how the network can be expanded or improved to accommodate future growth based off reflection questions.

<details closed> <summary>Example Report</summary>
  <h4>Network Diagram</h4>
  <img width="1376" height="887" alt="image" src="https://github.com/user-attachments/assets/beaa91e3-bb51-40d7-abb2-0316565a0088" />
  <br>
  <h4>Describing Data Flow Scenarios</h4>
  <h5>Scenario 1: External User Visiting the Company Website in the DMZ</h5>
    <ol>
      <li>The external user’s browser resolves the company URL to the public IP of the site.</li>
      <li>Traffic arrives from the Internet at the edge router and is forwarded to the external firewall.</li>
      <li>The external firewall allows only published web ports (80/443) and performs destination NAT to the DMZ web server’s private address.</li>
      <li>The inline IPS behind the external firewall inspects the HTTP/HTTPS session and blocks clear exploits or protocol abuse before traffic enters the DMZ.</li>
      <li>The DMZ switch forwards the allowed traffic to the web server; server responses follow the reverse path.</li>
      <li>The IDS, tapped from the DMZ or core switch, receives a copy for visibility and alerting; the DMZ honeypot is not in the normal path but will capture scanners and bots probing unused addresses.</li>
    </ol>
  </li>
  <h5>Scenario 2: Employee Sending a Print Job to a Department Printer</h5>
  <ol>
      <li>The workstation sends the print job using the department’s print protocol (for example, IPP 631 or RAW 9100) to the printer’s IP.</li>
      <li>If the printer is in the same VLAN, the access switch forwards frames locally and the job stays within that VLAN.</li>
      <li>If the printer is in a different VLAN, traffic goes to the core switch and then to the internal firewall, which permits only authorized VLANs to reach the printer and denies others to prevent cross-VLAN printing.</li>
    </ol>
  </li>
</ol>
  <br>
  <h4>Answers to Reflection Questions Based off Diagram</h4>
<ol>
  <li>The router sits at the edge next to the internet so it handles the wide area handoff. The external firewall sits between the router and the DMZ to allow only public services in and to control what the DMZ can send out. The internal firewall sits between the internal switch and the DMZ so only approved flows can pass between the IT and Finance VLANs and the DMZ or the internet. This placement creates two choke points and keeps direct internet access away from the internal VLANs.</li>

  <li>Separating the DMZ from the internal network reduces the chance that a compromise of a public server leads straight into file servers and workstations. It limits lateral movement and limits exposure of internal services. Risks that remain include mistakes in firewall policy, stolen credentials used over allowed paths, application layer flaws on the web or mail server, and denial of service that can still take those public services down.</li>

  <li>The honeypot is in the DMZ. There it can capture internet scans, bot probing, and misdirected connection attempts that should never reach production servers. It can also reveal internal reconnaissance if an insider or an infected host touches the decoy from the inside toward the DMZ.</li>

  <li>The IDS receives a copy of traffic on the link between the internal firewall and the DMZ switch. It can see flows from the internal VLANs to the DMZ and back, including visits to the web and mail servers. It may miss traffic that stays inside a single VLAN, traffic on the internet edge that does not pass the tap, and the contents of encrypted sessions beyond basic metadata.</li>

  <li>The IPS is inline on the path between the DMZ and the external firewall. It can block clear exploit signatures against HTTP and SMTP, obvious protocol violations, and known bad destinations on the way out, without touching normal business flows. It should be tuned to the services in the DMZ so that valid web and mail traffic continues to pass.</li>

  <li>The single failure with the widest impact would be the internal firewall because it sits between both VLANs and everything outside. A practical plan to reduce impact is a high availability pair with fail over, redundant power, and redundant links to the internal switch and the DMZ switch, with regular failover tests.</li>

  <li>For an external user visiting the web server, the packet first meets the external firewall which allows only the required ports, then the IPS which inspects and can block known attacks, and only then reaches the web server in the DMZ. After the packet reaches the application, visibility comes from the IDS that sees the DMZ link and from the web server logs.</li>

  <li>The print job stays inside the VLAN and the internal firewall rules prevent devices from other VLANs from reaching that printer. To verify, attempt a simple connection test from a workstation in the other VLAN to the printer address and confirm that the firewall denies it while the same test from the correct VLAN succeeds.</li>

  <li>Send honeypot alerts, IDS alerts, and firewall logs to one place for correlation, for example a central log platform. Create playbooks so that the security operations team owns triage of honeypot and IDS alerts, the network team owns firewall rule review and containment actions, and the system owners receive tickets when a host appears involved. Use shared time stamps and common fields such as source address, destination address, and port to stitch events together.</li>

  <li>File server protection will first show as an IDS alert for scans to file sharing ports or as a firewall deny log for an unauthorized attempt. Web server protection will first show as an IPS alert on the edge or as a web server log that records unusual requests. A malicious insider or an infected host will often first trigger the honeypot with probes to unused addresses, followed by IDS alerts for sweeping across the VLANs.</li>
</ol>
<br>
  <h4>Network Improvements</h4>

  
</details>

