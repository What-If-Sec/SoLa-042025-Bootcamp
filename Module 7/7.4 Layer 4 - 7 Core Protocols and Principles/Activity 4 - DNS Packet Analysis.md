## Activity Objectives

In this activity, students will demonstrate a comprehensive understanding of various types of DNS records, including A, MX, CNAME, PTR, NS, SOA, AAAA, TXT, and SRV records, and their respective functions within the DNS system. Ensuring that students not only learn the theoretical aspects of DNS records but also acquire hands-on experience with querying and analyzing DNS data.

## Activity Instructions

Complete the knowledge check below.

## Knowledge Check
1. What is the main purpose of the Domain Name System (DNS)?
   1. To assign IP addresses to devices
   2. To route packets between networks
   3. To translate domain names into IP addresses
   4. To encrypt internet traffic
<details closed>
<summary>Answer</summary>
DNS converts human-readable domain names (like google.com) into numerical IP addresses used for communication.
</details>

2. Which protocol and port does DNS typically use for name resolution?
   1. TCP on port 22
   2. UDP on port 53
   3. UDP on port 80
   4. TCP on port 53
<details closed>
<summary>Answer</summary>
DNS typically uses UDP on port 53 for queries. TCP may be used for larger responses such as zone transfers.
</details>

3. Match the following DHCP message types with their function:

| DHCP Message Type | Function |
|-------------------|----------|
| A            | Maps a domain name to a mail server IP address  |
| CNAME        | Points one domain name to another domain name     |
| MX           | Maps a domain name to an IPv6 address             |
| AAAA         | Maps a domain name to an IPv4 address             |

<details closed>
<summary>Answer</summary>
 <table border="1">
  <thead>
    <tr>
      <th>DNS Record Type</th>
      <th>Correct Function</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>A</td>
      <td>Maps a domain name to an IPv4 address</td>
    </tr>
    <tr>
      <td>CNAME</td>
      <td>Points one domain name to another domain name</td>
    </tr>
    <tr>
      <td>MX</td>
      <td>Maps a domain name to a mail server IP address</td>
    </tr>
    <tr>
      <td>AAAA</td>
      <td>Maps a domain name to an IPv6 address</td>
    </tr>
  </tbody>
</table>
<p>
Each DNS record type has a specific role in helping domain names resolve to useful information. An A record maps a domain name to an IPv4 address, which is the most common type used to connect users to websites. A CNAME, or Canonical Name record, points one domain name to another, allowing for domain aliasing (like pointing www.example.com to example.com). An MX record identifies mail servers that handle email for the domain, ensuring that messages are properly routed. An AAAA record is similar to an A record but maps the domain name to an IPv6 address instead of IPv4. These record types form the foundation of how DNS directs traffic across the internet.</p>
</details>

4. What command would you use to look up only the IPv6 address (AAAA record) for cloudflare.com using nslookup?
   1. nslookup cloudflare.com
   2. nslookup -query=aaaa cloudflare.com
   3. nslookup -query=a cloudflare.com
   4. nslookup -type=mx cloudflare.com
<details closed>
<summary>Answer</summary>
To find IPv6 addresses, the query type must be explicitly set to AAAA.
</details>

5. When using the nslookup command, what does the "Non-authoritative answer" section show?
   1. An answer retrieved directly from the domain's authoritative name server 
   2. An answer retrieved from a cached record on a recursive DNS server
   3. An error indicating the domain does not exist
   4. An answer retrieved from a cached record on a recursive DNS server
<details closed>
<summary>Answer</summary>
A "Non-authoritative answer" in nslookup means the DNS response did not come directly from the domain's official (authoritative) DNS server, but from another DNS server—typically a recursive resolver—that had the answer cached from a previous query. The information is still valid, but it was not fetched in real time from the source. Authoritative answers come from the DNS servers listed in the domain's NS records.
</details>

6. What is the purpose of a TXT record in DNS?
   1. To store text-based information for various purposes, such as domain verification or SPF (Sender Policy Framework) records
   2. To provide the canonical name for a domain
   3. To specify the mail servers for a domain
   4. To list the authoritative DNS servers for a domain
<details closed>
<summary>Answer</summary>
To store text-based information for various purposes, such as domain verification or SPF (Sender Policy Framework) records
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

8. What is the primary purpose of a CNAME (Canonical Name) record in DNS?
   1. To specify the IP address of a domain name
   2. To define the mail server responsible for handling emails for a domain
   3. To store text-based information, such as SPF records or domain verification details
   4. To provide an alias for a domain name, pointing to another domain name
<details closed>
<summary>Answer</summary>
To provide an alias for a domain name, pointing to another domain name
</details>

9. If a DNS response includes multiple IP addresses for the same domain, what type of DNS record is being queried?
   1. CNAME
   2. NS
   3. PTR
   4. A
<details closed>
<summary>Answer</summary>
A domain can have multiple A records for load balancing or redundancy.
</details>

10. What is the goal of a DNS spoofing attack?
     1. To trick a client into accepting a false IP address for a domain
     2. To redirect DNS traffic through a VPN
     3. To force a DNS server offline
     4. To overload a DNS server with queries
<details closed>
<summary>Answer</summary>
DNS spoofing aims to return a fake DNS response with the wrong IP address, redirecting users to malicious websites. 
</details>

11. Which DNS record type is commonly targeted in a DNS spoofing attack?
     1. MX
     2. PTR
     3. A
     4. NS
<details closed>
<summary>Answer</summary>
A records map domain names to IP addresses, making them the primary target in spoofing attempts.</details>

12. What is a DNS amplification attack?
     1. An attack that duplicates DNS queries to overload the client
     2. An attack that uses small queries to generate large DNS responses directed at a victim
     3. A method to increase the DNS caching time
     4. A way to speed up DNS resolution using multiple servers
<details closed>
<summary>Answer</summary>
DNS amplification is a type of DDoS attack where the attacker sends forged DNS requests with the victim's IP, causing DNS servers to flood the victim with large responses.
</details>

13. What role does a recursive DNS server play in a DNS amplification attack?
     1. It filters out invalid responses
     2. It forwards traffic to a firewall
     3. It unknowingly sends amplified responses to the victim
     4. It prevents the attack from succeeding
<details closed>
<summary>Answer</summary>
In a DNS amplification attack, the attacker spoofs the victim’s IP in a small query; and then the recursive server sends a large response to the victim resulting in DoS.
</details>

14. What is DNS cache poisoning?
     1. A type of DNS spoofing attack that involves an attacker injecting false DNS responses into a resolver’s cache to redirect users
     2. A type of DNS spoofing attack that involves an attacker redirecting traffic by overwhelming a DNS server with queries
     3. A type of DNS spoofing attack that involves an attacker replacing DNS records with encrypted data
     4. A type of DNS spoofing attack that involves an attacker blocking all DNS responses from reaching the client
<details closed>
<summary>Answer</summary>
An attack that involves an attacker blocking all DNS responses from reaching the client
</details>

15. What is a DNS query flood attack?
     1. An attack that involves an attacker sending fake DNS responses to redirect users to malicious sites
     2. An attack that involves an attacker injecting false records into a DNS cache
     3. An attack that involves an attacker sending a high volume of DNS queries to overwhelm a DNS server
     4. An attack that involves an attacker stealing DNS records from a zone transfer
<details closed>
<summary>Answer</summary>
A DNS query flood attack is a type of denial of service attack where the attacker sends a large number of DNS queries to a DNS server. These queries are often sent in rapid succession or with random domain names to force the server to spend resources processing them. This can slow down the server or make it unresponsive to legitimate users. The goal is to disrupt normal DNS service by exhausting the server's capacity.
</details>

16. Open the pcap file located [here](https://drive.google.com/file/d/1A-4hA3CY1rgPpCkggmfVvgmfYU9SfFoT/view?usp=drive_link), and locate the packet with the DNS response below. What does the DNS response from the local DNS server indicate?
     1. A rogue DNS server is returning a loopback address to interfere with traffic
     2. The legitimate IP address of Google has changed
     3. The DNS server is offline and falling back to a default IP
     4. Google is blocking DNS queries from that server
<details closed>
<summary>Answer</summary>
A DNS query flood attack is a type of denial of service attack where the attacker sends a large number of DNS queries to a DNS server. These queries are often sent in rapid succession or with random domain names to force the server to spend resources processing them. This can slow down the server or make it unresponsive to legitimate users. The goal is to disrupt normal DNS service by exhausting the server's capacity.
</details>

17. Which packets within the previous pcap file contain DNS responses with private or loopback address "127.0.1.1"? (Select all that apply)
     1. Packet 6
     2. Packet 12
     3. Packet 18
     4. Packet 21
     5. Packet 33
     6. Packet 36
     7. Packet 39
<details closed>
<summary>Answer</summary>
Packets 6 (www.google.com), 33 and 36 (www.yahoo.com), and 39 (www.youtube.com) all contain DNS responses with the loopback IP address 127.0.1.1, indicating suspicious or spoofed DNS activity. The other options include packets with valid public IPs or CNAME chains.
</details>

18. What type of attack is being executed within the pcap file? Provide your answer as well as a justification why.
<details closed>
<summary>Answer</summary>
DNS spoofing attack (specifically, a response forgery using a rogue DNS server). The reason why is that within the pcap file, we can observe DNS responses from two different sources: a trusted DNS server (8.8.8.8) and a local IP address (192.168.88.2). While 8.8.8.8 returns valid public IP addresses for domains like www.google.com and www.facebook.com, the local server (192.168.88.2) returns the loopback address 127.0.1.1 for popular public domains such as www.google.com, www.yahoo.com, and www.youtube.com. This is not legitimate behavior. It indicates that the local DNS server is spoofing responses, redirecting users back to their own machines or blocking access entirely. This pattern of behavior is consistent with a DNS spoofing attack, where a malicious DNS server provides false information to manipulate or interrupt network traffic.
</details>

19. Open your browser and go to nslookup.io and perform a DNS lookup of thesolafoundation.org. What IP addresses are provided within the A record.
<details closed>
<summary>Answer</summary>
DNS providers often return different IP addresses based on the location of the resolver or client making the request. As a result, answers may vary.
</details>

20. Open your browser and go to nslookup.io and perform a DNS lookup of thesolafoundation.org. What is the primary mail server, and how might an attacker use this information?
<details closed>
<summary>Answer</summary>
By identifying the mail server, an attacker knows where email is delivered for that domain. This allows them to craft phishing or spoofed emails that target users or systems within the organization. If the organization’s mail server is hosted by a known provider (like Google or Microsoft), attackers can also tailor their attacks to mimic those platforms more convincingly.
</details>
