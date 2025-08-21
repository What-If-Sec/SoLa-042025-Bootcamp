## Activity Objective

The objective of this activity is to evaluate students' understanding of LDAP, NTLM, and Kerberos, three key components of authentication and directory services in Windows-based environments. 

Students will demonstrate their ability to identify the purpose and function of each protocol, explain how they interact within Active Directory, and distinguish between modern and legacy authentication methods. This knowledge check will reinforce critical concepts needed for effective system administration and cybersecurity practices.

## Activity Instructions
Complete the knowledge check below.

### Knowledge Check
1. Which of the following is a major reason Kerberos replaced NTLM in modern Windows domains?
   1. Kerberos is easier to configure
   2. NTLM requires multi-factor authentication
   3. Kerberos provides better security guarantees and scalability
   4. NTLM uses public key infrastructure
<details closed>
<summary>Answer</summary>
Kerberos provides better security guarantees and scalability
</details>

2. How does NTLM authenticate a user?
   1. Sends the user's password over the network
   2. Uses a challenge-response mechanism with password hashes
   3. Issues a ticket that is stored in memory
   4. Uses certificates to authenticate users and devices
<details closed>
<summary>Answer</summary>
Uses a challenge-response mechanism with password hashes
</details>

3. What does the Kerberos Authentication Service (AS) initially provide to a client after login?
   1. Ticket Granting Service (TGS)
   2. Service Ticket
   3. Session Key
   4. Ticket Granting Ticket (TGT)
<details closed>
<summary>Answer</summary>
Ticket Granting Ticket (TGT)
</details>

4. Which of the following is a benefit of Kerberos over NTLM?
   1. It prevents replay attacks more effectively
   2. It stores passwords in an encrypted file
   3. It relies on less infrastructure
   4. It does not use password hashes
<details closed>
<summary>Answer</summary>
It prevents replay attacks more effectively
</details>

5. What component issues Service Tickets in the Kerberos protocol?
   1. Authentication Server (AS)
   2. Key Distribution Center (KDC)
   3. AD Domain Controller
   4. Ticket Granting Service (TGS)
<details closed>
<summary>Answer</summary>
Ticket Granting Service (TGS)
</details>

6. What is the function of a TGT in Kerberos?
   1. Authenticates the user to services directly
   2. Stores a list of group memberships
   3. Allows the user to request access to services
   4. Encrypts the service ticket
<details closed>
<summary>Answer</summary>
Allows the user to request access to services
</details>

7. What does mutual authentication in Kerberos ensure?
   1. Only the user is authenticated
   2. Only the service is authenticated
   3. Both client and server verify each other’s identity
   4. The user cannot reuse the same password across systems
<details closed>
<summary>Answer</summary>
Only the user is authenticated
</details>

8. What does the KDC consist of? Select all that apply.
   1. Authentication Service (AS)
   2. User and Group Database
   3. AD Domain Controller (AD DC)
   4. Ticket Granting Service (TGS)
<details closed>
<summary>Answer</summary>
Ticket Granting Service
</details>

9. In a modern Windows domain, when is NTLM still used?
   1. Always by default
   2. Only when Kerberos fails or is unsupported
   3. Only by Linux clients
   4. Never, it is fully deprecated
<details closed>
<summary>Answer</summary>
 Only when Kerberos fails or is unsupported
</details>

10. What does a Kerberos service ticket contain, and how is it accessed by the client?
    1. It contains the user’s password and is stored in the Windows registry
    2. It contains the user's group memberships and is retrieved from AD
    3. It contains a session key and is accessed using the Ticket Granting Ticket (TGT)
    4. It contains the user's password hash
<details closed>
<summary>Answer</summary>
It contains a session key and is accessed using the Ticket Granting Ticket (TGT)
</details>

11. What is the primary role of LDAP in an Active Directory environment?
    1. Encrypts user credentials during login
    2. Authenticates users and issues tickets
    3. Provides a structured method to query and manage directory information
    4. Manages DNS records for domain controllers
<details closed>
<summary>Answer</summary>
Provides a structured method to query and manage directory information
</details>

12. True or False: In a typical Active Directory login, Kerberos is used first for authentication, and then LDAP is used to retrieve user group membership and permissions.
    1. True
    2. False
<details closed>
<summary>Answer</summary>
True
</details>
