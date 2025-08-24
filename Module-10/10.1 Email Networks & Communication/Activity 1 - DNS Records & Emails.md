## Activity Objective:

Students will demonstrate their understanding of how DNS records such as MX, SPF, DKIM, and DMARC facilitate and secure email communication by answering related questions. Additionally, they will perform a practical DNS lookup to retrieve and analyze these records for a domain, reinforcing their knowledge of the role DNS plays in email delivery and security.

## Activity Instructions:

Complete the quiz, using CLI tools like nslookup or another online tool like dns.google.com or nslookup.io

### Knowledge Check
1. Select all that apply. Consequence(s) of not using a DMARC record include:
    1.	Lack of protection against phishing and spoofing attacks.
    2.	Sensitive data can be exposed due to no encryption
    3.	Limited control over how receiving mail servers handle failed SPF/DKIM checks.
    4.	No insight into potential abuse of your domain by malicious actors.
<details closed>
<summary>Answer Key</summary>
  <p>
    Without a DMARC record, your domain is more vulnerable because you lose protection against phishing and spoofing, have limited control over how receiving mail servers handle failed SPF or DKIM checks, and miss out on reports that provide visibility into unauthorized use of your domain. DMARC does not provide encryption, so exposure of sensitive data is not a direct consequence of not using it.
  </p>
</details>
   
2. Select all that apply. Consequence(s) of not using a DKIM record include:
    1.	Lack of protection against phishing and spoofing attacks.
    2.	Emails may not be trusted by receiving servers, especially if the server is configured to verify DKIM signatures.
    3.	Limited control over how receiving mail servers handle failed SPF/DKIM checks.
    4.	Lower trust and higher chances of landing in the recipient's spam folder.
<details closed>
<summary>Answer Key</summary>
  <p>
    Without a DKIM record, your domain is more exposed to phishing and spoofing, emails may not be trusted by receiving servers that verify DKIM signatures, and your messages have a higher chance of being flagged as spam or landing in the junk folder due to reduced trust. However, limited control over how receiving servers handle SPF or DKIM failures is a DMARC issue, not a direct consequence of missing DKIM.
  </p>
</details>

3. Select all that apply. Consequence(s) of not using a SPF record include:
    1.	Increased vulnerability to email spoofing where someone can forge the "From" address to appear as if it’s coming from your domain.
    2.	Sensitive data can be exposed due to no encryption
    3.	Email attachments can be tampered with, without detection.
    4.	Higher likelihood of your email being marked as spam.
<details closed>
<summary>Answer Key</summary>
  <p>
    Without an SPF record, your domain is more vulnerable to spoofing since attackers can forge the “From” address to make emails look like they come from you, and your legitimate messages are more likely to be flagged as spam by receiving servers. SPF does not provide encryption or integrity checks on attachments, so exposure of sensitive data or tampering with attachments is not a direct consequence of not using it.
  </p>
</details>

4. DNS records are stored in what file?
    1.	DNS Tree File
    2.	DNS Records File
    3.	DNS Zone File
    4.	DNS Server File
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

7. Why is DKIM important? (More than one answer may apply)
    1.	Prevents email tampering
    2.	Improves email deliverability
    3.	Prevents email eavesdropping
    4.	Works with DMARC to ensure that emails pass through SPF and that DKIM checks are properly authenticated
<details closed>
<summary>Answer Key</summary>
  <p>
DKIM is important because it helps prevent email tampering by using digital signatures to verify message integrity, and it improves email deliverability since receiving servers are more likely to trust signed messages. It also works alongside DMARC to ensure emails are properly authenticated with SPF and DKIM checks. However, DKIM does not prevent email eavesdropping, as it does not encrypt the message content.
  </p>
</details>

8. Why is DMARC important? (More than one answer may apply)
    1.	Reports email tampering
    2.	Reports can give domain owners visibility into email network.
    3.	Reduces the risk of email spoofing and phishing attacks
    4.	Works with SPF and DKIM by adding enforcement and reporting.
<details closed>
<summary>Answer Key</summary>
  <p>
DMARC is important because it gives domain owners visibility into how their email is being used through reports, reduces the risk of spoofing and phishing by allowing them to enforce authentication policies, and works with SPF and DKIM by adding both enforcement and reporting. However, DMARC does not directly report email tampering, as its role is focused on authentication and policy enforcement rather than content integrity.
  </p>
</details>

9. In a SPF record, what does "-all" indicate?
    1.	Pass, the client is authorized.
    2.	Fail, the client is not authorized.
    3.	Soft-Fail, the client is not authorized, but the message may still be accepted.
    4.	Neutral, no explicit authorization or denial.
<details closed>
<summary>Answer Key</summary>
  <p>
In an SPF record, -all indicates a hard fail. This tells receiving mail servers that if an email does not come from an IP address or server explicitly listed in the SPF record, it should be rejected outright.
  </p>
</details>

10. In a SPF record, what does "~all" indicate?
    1.	Pass, the client is authorized.
    2.	Fail, the client is not authorized.
    3.	Soft-Fail, the client is not authorized, but the message may still be accepted.
    4.	Neutral, no explicit authorization or denial.
<details closed>
<summary>Answer Key</summary>
  <p>
In an SPF record, ~all means Soft-Fail and that the client is not authorized to send email for the domain, but the receiving server may still accept the message (often marking it as suspicious or delivering it to spam). This makes option 3 correct. It differs from -all (Fail, reject), ?all (Neutral), and an explicit match that results in Pass.
  </p>
</details>

11. In a SPF record, what does "?all" indicate?
    1.	Pass, the client is authorized.
    2.	Fail, the client is not authorized.
    3.	Soft-Fail, the client is not authorized, but the message may still be accepted.
    4.	Neutral, no explicit authorization or denial.
<details closed>
<summary>Answer Key</summary>
  <p>
In an SPF record ?all means Neutral which indicates there is no explicit authorization or denial for the client. The receiving mail server decides how to handle the message. This makes option 4 correct. It is different from all with a minus sign which means Fail and reject, all with a tilde which means Soft Fail, and a matching rule that results in Pass.
  </p>
</details>

12. What does the DMARC policy "quarantine" (i.e., p=quarantine) signify?
    1.	Messages that pass DMARC are marked as suspicious and may be sent to the spam/junk folder.
    2.	Messages that fail DMARC are rejected and not delivered to the recipient.
    3.	No specific action is taken; emails that fail authentication are still delivered, but reports are generated.
    4.	Messages that fail DMARC are marked as suspicious and may be sent to the spam/junk folder.
<details closed>
<summary>Answer Key</summary>
  <p>
    In a DMARC policy p=quarantine means that messages which fail DMARC are marked as suspicious and may be sent to the recipient’s spam or junk folder. It is different from p=reject which blocks delivery completely and p=none which takes no action but provides reporting.
  </p>
</details>

14. What are the two different types of reports sent using DMARC?
    1.	Aggregate and Reject Reports
    2.	Network and Analysis Reports
    3.	Forensic and Quarantine Reports
    4.	Aggregate and Forensic Reports
<details closed>
<summary>Answer Key</summary>
  <p>
DMARC supports two types of reports which are Aggregate Reports and Forensic Reports. Aggregate reports provide a summary of authentication results across many messages, while forensic reports give detailed information about individual messages that failed authentication.
  </p>
</details>

15. Perform a DNS lookup of https://www.thesolafoundation.org/ and provide the MX, SPF, DKIM, and DMARC records if applicable.
