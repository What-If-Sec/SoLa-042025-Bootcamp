## Activity Objective:c 
Students will gain a comprehensive understanding of how email communication functions by exploring the roles of SMTP, POP3, and IMAP. They will be able to explain the processes involved in sending and receiving emails, identify the differences between POP3 and IMAP in terms of email retrieval and synchronization, and understand the standard ports associated with each protocol. Additionally, students will assess the advantages and disadvantages of POP3 versus IMAP based on user needs and device access requirements.

## Activity Instructions:
Complete the following knowledge check.

### Knowledge Check
1. Which of the following protocols are commonly used in email communication? (Select all that apply)
    1.	SMTP – used for sending email between clients and servers
    2.	SFTP – used for retrieving and managing email from a server
    3.	POP3 – used for downloading email from a server to a client
    4.	IMAP – used for transferring files between systems
<details closed>
<summary>Answer Key</summary>
  <p>
Email communication relies on three main protocols. SMTP is used for sending messages from an email client to a mail server and for relaying mail between servers. IMAP allows users to retrieve and manage email while keeping it stored on the server, which is useful for accessing mail from multiple devices. POP3 also retrieves email but typically downloads it to the client and removes it from the server. SFTP is not used in email communication. 
  </p>
</details>
   
2. What port(s) does SMTP use? (Select all that apply)
    1.	Port 25
    2.	Port 587
    3.	Port 110
    4.	Port 995
<details closed>
<summary>Answer Key</summary>
  <p>
Port 25, the original SMTP port, is primarily for server-to-server communication and is often blocked by ISPs due to security concerns. Port 587, on the other hand, is the standard for secure email submission from client to server, requiring authentication and often supporting TLS encryption. 
  </p>
</details>

3. What port(s) does IMAP use? (Select all that apply)
    1.	Port 110
    2.	Port 143
    3.	Port 993
    4.	Port 995
<details closed>
<summary>Answer Key</summary>
  <p>
POP3 (Post Office Protocol version 3) uses two primary port numbers for email retrieval: 110 for non-secure connections and 995 for secure connections using SSL/TLS. Port 110 is the default for unencrypted POP3, while 995 is used for secure, encrypted communication. 
  </p>
</details>

4. What port(s) does POP3 use? (Select all that apply)
    1.	Port 110
    2.	Port 123
    3.	Port 995
    4.	Port 996
<details closed>
<summary>Answer Key</summary>
  <p>
    DNS records are stored in zone files, a zone file is a plain text file maintained by a DNS server that contains mappings between domain names and IP addresses along with other resource records (like A, AAAA, MX, CNAME, and TXT). It defines the authoritative data for a particular DNS zone and tells the server how to resolve queries for that domain.
  </p>
</details>

5. What is the primary purpose of a name server in the Domain Name System (DNS)?
    1.	To manage email security protocols like SPF and DKIM
    2.	To translate human-readable domain names into IP addresses
    3.	To host websites and store web content
    4.	To manage domain registration and ownership records
<details closed>
<summary>Answer Key</summary>
  <p>
   The primary purpose of a name server in the Domain Name System (DNS) is to translate human-readable domain names into IP addresses (and vice versa), so that users can access websites and services using names like example.com instead of numerical addresses. In other words, the name server stores and serves DNS records for a domain and answers queries from clients or other servers to guide them to the correct destination on the internet.
  </p>
</details>

6. What is the primary function of a mail server in email communication?
    1.	To store website data and serve it to users
    2.	To authenticate users for network access
    3.	To send, receive, and store email messages for a domain
    4.	To convert domain names into IP addresses
<details closed>
<summary>Answer Key</summary>
  <p>
   The primary function of a mail server in email communication is to send, receive, store, and forward email messages between senders and recipients. It acts as the backbone of email delivery by using protocols such as SMTP (for sending), and IMAP/POP3 (for retrieving), ensuring that messages are routed to the correct destination and made available for users to access.
  </p>
</details>

7. Which protocol allows a user to access and manage email messages while keeping them stored on the mail server, making it easy to check email from multiple devices?
    1.	SMTP
    2.	IMAP
    3.	POP3
<details closed>
<summary>Answer Key</summary>
  <p>
IMAP (Internet Message Access Protocol) is designed to keep messages on the server while allowing the user to organize and read them across multiple devices. 
  </p>
</details>

8. Which protocol typically downloads email messages from the server to a single client and often removes them from the server after retrieval?
    1.	IMAP
    2.	POP3
    3.	SMTP
<details closed>
<summary>Answer Key</summary>
  <p>
POP3 (Post Office Protocol 3) is designed to download messages from the mail server to the client, and by default, it deletes them from the server. This makes it best suited for single-device email use.
  </p>
</details>

9. A user wants to access the same mailbox from a laptop, phone, and webmail while keeping everything synchronized. Which protocol is best suited for this use case?
    1.	SMTP
    2.	POP3
    3.	IMAP
<details closed>
<summary>Answer Key</summary>
  <p>
IMAP synchronizes messages with the mail server, ensuring consistency across multiple devices. POP3 typically removes messages from the server after download, and SMTP only sends mail.
  </p>
</details>

10. A user downloads email to their desktop using a mail client, but later notices the same messages are no longer available when checking email on their phone. Which protocol is most likely being used?
    1.	POP3
    2.	SMTP
    3.	IMAP
<details closed>
<summary>Answer Key</summary>
  <p>
POP3 typically downloads messages from the mail server to a single client and then removes them from the server. This makes the emails unavailable on other devices. IMAP, in contrast, keeps mail on the server and syncs across devices. And SMTP is only for sending mail.
  </p>
</details>
