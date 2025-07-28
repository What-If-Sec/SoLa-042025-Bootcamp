## Activity Objective

The objective of this activity is to assess students' understanding of the core concepts, terminology, and infrastructure of Active Directory. By completing this knowledge check, students will demonstrate their grasp of key components such as domains, objects including  users and groups, domain controllers, and trust relationships. 

This review will help reinforce foundational knowledge and identify any areas that may need further clarification before moving into hands-on labs and real-world applications.



## Activity Instructions

Complete the knowledge check below.

### Knowledge Check
1. What is an object in Active Directory?
   1. A set of policies that manage computer access.
   2. A security feature for blocking unauthorized users.
   3. A unique entry in Active Directory that represents a physical or logical entity, such as a user or printer.
   4. A method for backing up user data.
<details closed>
<summary>Answer</summary>
A unique entry in Active Directory that represents a physical or logical entity, such as a user or printer.
</details>

2. Which of the following is an example of an object type in Active Directory?
   1. Printer
   2. Server
   3. User
   4. All of the above
<details closed>
<summary>Answer</summary>
All of the above
</details>

3. What is the purpose of attributes in Active Directory objects?
   1. They store detailed information about an object.
   2. They store domain information about an object.
   3. They define the permissions of an object
   4.  They define how long a user can remain logged in
<details closed>
<summary>Answer</summary>
They store detailed information about an object, such as a user’s email address, phone number, or job title.
</details>

4. Which of the following is an example of an attribute of a user object in Active Directory?
   1. Username
   2. IP address
   3. Active Directory replication schedule
   4. Physical location
<details closed>
<summary>Answer</summary>
Username
</details>

5. Which of the following is a standard attribute for a computer object in Active Directory?
   1. User’s group membership
   2. Computer’s hostname
   3. User’s email address
   4. GPO inheritance
<details closed>
<summary>Answer</summary>
Computer’s hostname
</details>

6. When adding a new user to Active Directory, which object type is being created?
   1. Organizational Unit
   2. Computer Object
   3. User Object
   4. Domain Name
<details closed>
<summary>Answer</summary>
User Object
</details>

7. In Active Directory, the 'Distinguished Name' (DN) of an object represents?
   1. The global identifier for a user
   2. The IP address of the domain controller
   3. The object’s group membership
   4. The full path to the object in the directory hierarchy
<details closed>
<summary>Answer</summary>
User Object
</details>

8. Which of the following best describes the Schema in Active Directory?
   1. The set of rules that define object types and attributes in the directory.
   2. The logical layout of OUs and Groups.
   3. A list of usernames and passwords.
   4. A backup of the domain controller.
<details closed>
<summary>Answer</summary>
The set of rules that define object types and attributes in the directory.
</details>

9. Which of the following best describes the Schema in Active Directory?
   1. The format and rules for DNS entries.
   2. The configuration of Group Policies.
   3. The definition of every type of object and what attributes it can have.
   4. Which users belong to which OUs.
<details closed>
<summary>Answer</summary>
The set of rules that define object types and attributes in the directory.
</details>

10. What is a "class" in Active Directory schema terms?
    1. A classification of objects by their operational state
    2. A way to group users based on job roles
    3. A template that defines the attributes of an object type, such as User or Computer
    4. A physical location where a computer can be found
<details closed>
<summary>Answer</summary>
A template that defines the attributes of an object type, such as User or Computer
</details>

11. Which of the following best describes Active Directory (AD)?
    1. A web server
    2. A central identity and access management system for Windows networks
    3. A remote desktop manager
    4. A Windows configuration tool
<details closed>
<summary>Answer</summary>
A central identity and access management system for Windows networks
</details>

12. Which of the following is NOT a feature of Active Directory?
    1. File system backup
    2. User and group management
    3. A remote desktop manager
    4. A Windows configuration tool
<details closed>
<summary>Answer</summary>
File system backup
</details>

13. What is a  Active Directory Domain Controller (AD DC)?
    1. A backup server for file shares
    2. A user permission level
    3. A Windows firewall rule
    4. A server that handles AD authentication and services
<details closed>
<summary>Answer</summary>
A server that handles AD authentication and services
</details>

14. What is a Forest in AD?
    1. A shared printer directory
    2. A grouping of organizational units
    3. A collection of domains that share a schema and trust relationship
    4. A list of backup servers
<details closed>
<summary>Answer</summary>
A server that handles AD authentication and services
</details>

15. What is a Domain in Active Directory?
    1. A backup of user data
    2. A group of computers that share the same physical location
    3. A collection of network resources such as users, computers, and printers that are managed as a unit
    4. A network of servers that store files
<details closed>
<summary>Answer</summary>
A collection of network resources such as users, computers, and printers that are managed as a unit
</details>

16. Which of the following is a key characteristic of a domain in Active Directory?
    1. Domains are associated with physical locations only
    2. A domain provides a boundary for the storage of security policies and user information
    3. Domains do not allow user logins and authentication
    4. Domains are based on IP address ranges
<details closed>
<summary>Answer</summary>
A domain provides a boundary for the storage of security policies and user information
</details>

17. Which of the following best describes a domain trust in Active Directory?
    1. A domain's security policy to block unauthorized devices
    2. A relationship that allows users in one domain to access resources in another domain
    3. A domain's backup of critical user data
    4. A domain's ability to set time policies for login attempts
<details closed>
<summary>Answer</summary>
A relationship that allows users in one domain to access resources in another domain
</details>

18. Which of the following is true about the "Root Domain" in Active Directory?
    1. It is the first domain created in a forest and forms the basis for the AD structure
    2. It is the only domain that can have child domains
    3. It is a domain that only stores global catalog information
    4. It only exists in a multi-forest AD environment
<details closed>
<summary>Answer</summary>
It is the first domain created in a forest and forms the basis for the AD structure
</details>

19. Which of the following can be used to separate different security policies and organizational settings in a multi-domain forest environment?
    1. Organizational Units (OUs)
    2. Trusts
    3. Sites
    4. Domains
<details closed>
<summary>Answer</summary>
Domains
</details>

20. Which of the following describes the role of the Global Catalog in a domain environment?
    1. It stores only the schema of objects in the domain
    2. A domain controller that holds a searchable, partial replica of every object in the forest
    3. It controls user login attempts and failed logins
    4. It stores files and backups for the entire domain
<details closed>
<summary>Answer</summary>
A domain controller that holds a searchable, partial replica of every object in the forest
</details>

21. Why are AD Sites important?
    1. They determine who can log into a system
    2. They help organize user accounts for HR purposes
    3. They allow for email forwarding between domains
    4. They control replication traffic between domain controllers in different physical locations
<details closed>
<summary>Answer</summary>
They control replication traffic between domain controllers in different physical locations
</details>

22. What is a Site in Active Directory?
    1. A security group
    2. A website hosted by AD
    3. A set of IP sub-networks that map to a physical location to control replication and login traffic
    4. A DNS alias for a domain
<details closed>
<summary>Answer</summary>
A set of IP sub-networks that map to a physical location to control replication and login traffic
</details>

23. What is an Organizational Unit (OU)?
    1. An OU is a container within a domain used to organize users or computers and apply GPOs.
    2. An OU is a directory within a domain used to organize objects.
    3. An OU is a domain used to organize users or computers and apply GPOs.
    4. An OU is a logical boundary for AD services
<details closed>
<summary>Answer</summary>
An OU is a container within a domain used to organize users or computers and apply GPOs.
</details>

24. Which AD component typically represents a company or department?
    1. Schema
    2. Site
    3. Domain
    4. OU
<details closed>
<summary>Answer</summary>
OU
</details>

25. What is the smallest unit of replication in Active Directory?
    1. Site
    2. Domain
    3. OU
    4. Object
<details closed>
<summary>Answer</summary>
Object
</details>

26. What is the purpose of Group Policy Objects (GPOs)?
    1. To install antivirus software
    2. To enforce configuration settings on users and computers
    3. To track user browsing activity
    4. To restrict access
<details closed>
<summary>Answer</summary>
To enforce configuration settings on users and computers
</details>

27. You need to create a group of users that will all get the same software restrictions. Would you use a Group, an OU, or both? Why?
<details closed>
<summary>Answer</summary>
You would use an OU due to the fact that OUs are used to logically organize users in AD, and then apply Group Policy Objects (GPOs) to enforce software restrictions.
</details>

28. You are asked to make sure a new user account is searchable across the entire forest. What must happen for this to work?
<details closed>
<summary>Answer</summary>
Two things need to happen, (1) the domain controller (DC) must be a gloabl catalog (GC) server and (2) the user account must be created on it, and any key details must be shared with the GC for forest-wide searches.
</details>

29. An organization has multiple physical locations. What AD component helps optimize authentication and replication across these sites?
<details closed>
<summary>Answer</summary>
AD Sites optimize efficiency by aligning authentication and replication with the network’s physical layout, by directing users to the nearest domain controller (DC) and using site links and schedules to control replication traffic between sites, reducing network usage.
</details>

30. What is a trust relationship in Active Directory?
    1. A group policy that sets login times for users
    2. A record that is used to find domain controllers
    3. A configuration allowing domains to authenticate users from other domains
    4. A backup process used for user profiles
<details closed>
<summary>Answer</summary>
A configuration allowing domains to authenticate users from other domains
</details>

31. Which type of trust is automatically created between a parent and child domain in the same forest?
    1. External Trust
    2. Realm Trust
    3. Parent-Child Trust
    4. Transitive Trust
<details closed>
<summary>Answer</summary>
Transitive Trust
</details>

32. What does a "transitive trust" allow in Active Directory?
    1. Trust can be extended beyond the two domains that established it
    2. Trust exists only between two specific domains
    3. Trust applies only to local user accounts
    4. Trust is restricted to sites in the same subnet
<details closed>
<summary>Answer</summary>
Trust can be extended beyond the two domains that established it
</details>

33. Which of the following best defines a "non-transitive trust"?
    1. A trust that expires after a set period
    2. A trust that allows group policy replication
    3. A trust that only exists between the two specified domains and does not extend further
    4. A trust that only applies to child domains
<details closed>
<summary>Answer</summary>
A trust that only exists between the two specified domains and does not extend further
</details>

34. You need to allow authentication between two separate forests. Which trust type should you configure?
    1. Forest Trust
    2. External Trust
    3. Parent-Child Trust
    4. Shortcut Trust
<details closed>
<summary>Answer</summary>
Forest Trust
</details>

35. Which trust type allows a domain in a forest to trust a domain in a completely different forest without creating a forest trust?
    1. Realm Trust
    2. External Trust
    3. Shortcut Trust
    4. Parent-Child Trust
<details closed>
<summary>Answer</summary>
External Trust
</details>

36. Which of the following is true about realm trusts?
    1. They are used only within a single forest
    2. They provide backup services for domain controllers
    3. They connect Active Directory domains with non-Windows (e.g., UNIX Kerberos) systems
    4. They are only transitive and two-way
<details closed>
<summary>Answer</summary>
They connect Active Directory domains with non-Windows (e.g., UNIX Kerberos) systems
</details>

37. Why are trust relationships important in an enterprise Active Directory environment?
    1. They allow Group Policy Objects to be replicated to all forests
    2. They enable centralized identity and access management
    3. They allow secure authentication and resource access across domain or forest boundaries
    4. They are used to monitor for attempts to brute-force authentication
<details closed>
<summary>Answer</summary>
They allow secure authentication and resource access across domain or forest boundaries
</details>

38. What is a "shortcut trust" used for in Active Directory?
    1. To speed up authentication between domains in a large tree hierarchy
    2. To allow UNIX clients to connect to AD
    3. To bypass security policy restrictions
    4. To enable cross-forest replication
<details closed>
<summary>Answer</summary>
To speed up authentication between domains in a large tree hierarchy
</details>

39. Which of the following would happen if a domain controller is removed from a domain?
    1. All user and group information would be lost permanently
    2. Domain trust relationships would be deleted
    3. The domain would become non-functional until a new DC is installed
    4. It would no longer authenticate users or perform replication
<details closed>
<summary>Answer</summary>
It would no longer authenticate users or perform replication
</details>

40. What happens when you promote a server to a Domain Controller in Active Directory?
    1. It becomes a secondary domain that acts as a backup for the primary domain
    2. It joins the existing domain and begins to authenticate users and replicate directory data
    3. It gains the ability to manage network traffic and route packets
    4. It becomes a user-only device that allows authentication requests to be forwarded to other servers
<details closed>
<summary>Answer</summary>
It joins the existing domain and begins to authenticate users and replicate directory data
</details>
