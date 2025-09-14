## Activity Objective

Students will use Burp Suite to complete PortSwigger's Directory Traversal lab. By the end of this activity, students will be able to identify and exploit directory traversal vulnerabilities, navigate through restricted directories on a web server, retrieve sensitive files, and understand how improper input validation can expose critical file system data in web applications.


## Activity Instructions

Follow the instructions below:
1. Read the information provided by PortSwigger about Directory Traversal [here](https://portswigger.net/web-security/file-path-traversal#what-is-path-traversal) to compete the knowledge check below.
2. Once the knowledge check is completed, complete the lab found [here](https://portswigger.net/web-security/file-path-traversal/lab-simple).

### Knowledge Check
1. What is a directory traversal attack?
    1. An attack that tries to overload a server with requests
    2. An attack that injects malicious SQL queries
    3. An attack that manipulates file paths to access files outside the intended directory
    4. An attack that encrypts files for ransom
<details closed> <summary>Answer</summary><p>Directory traversal (or path traversal) is when an attacker manipulates file paths (e.g., with ../) to access files they shouldn’t, such as /etc/passwd or system configuration files.</p></details>

2. Which of the following inputs is a classic sign of a directory traversal attempt?
    1. `../../etc/passwd`
    2. `?id=12345`
    3. `<script>alert('XSS')</script>`
    4. `' OR '1'='1`
<details closed> <summary>Answer</summary><p>The input "../../etc/passwd" is a classic directory traversal payload, as it attempts to move up directories (../) and access the sensitive Linux password file. The other examples indicate different attack types: "?id=12345" is not a traversal payload but could hint at an IDOR (Insecure Direct Object Reference) vulnerability if changing the number exposes unauthorized resources, "<script>alert('XSS')</script>" is a Cross-Site Scripting (XSS) payload designed to execute JavaScript in the browser, and "' OR '1'='1" is a SQL injection payload used to manipulate database queries. Only "../../etc/passwd" demonstrates directory traversal.</p></details>

3. Why is the file /etc/passwd often targeted in directory traversal attacks on Linux systems?
    1. It contains all running processes
    2. It stores all system passwords
    3. It lists user accounts on the system
    4. It contains the entire system’s source code
<details closed> <summary>Answer</summary><p>The /etc/passwd file contains a list of system users. While it doesn’t store passwords directly anymore (those are in /etc/shadow), it still provides valuable information to attackers about user accounts.</p></details>

4. Which Windows file might an attacker try to access with directory traversal?
    1. C:\Windows\System32\config\SAM
    2. C:\Windows\Temp\logs.txt
    3. C:\Users\Public\Documents\file.docx
    4. C:\Windows\explorer.exe
<details closed> <summary>Answer</summary><p>The SAM (Security Account Manager) file contains hashed Windows passwords. It’s a prime target in directory traversal attacks.</p></details>

5. What does the sequence ../ mean in a file path?
    1. Go into the next directory
    2. Go up one directory
    3. Stay in the same directory
    4. Go down one directory
<details closed> <summary>Answer</summary><p>../ means “move up one directory level.” Attackers chain these (e.g., ../../) to escape the intended folder structure.</p></details>

6. You test a site’s file viewer with this input:
`http://example.com/vulnerabilities/fi/?page=../../../../var/log/apache2/access.log`
Instead of an error, the browser displays a list of recent HTTP requests to the server. What does this confirm?
    1. The site is vulnerable to file path / directory traversal
    2. The site is vulnerable to Cross-Site Scripting (XSS)
    3. The site is vulnerable to SQL injection
    4. The site is functioning normally and secure
<details closed> <summary>Answer</summary><p>If the application lets you access server logs such as "../../../../var/log/apache2/access.log", it confirms that user input is being used unsafely to build file paths. This is a directory traversal vulnerability because the attacker can break out of the intended directory and read sensitive files. While /etc/passwd is often used in demos, real-world attackers may target log files, configuration files, or other system data to gain valuable insights.</p></details>

7. Why might attackers chain directory traversal with other attacks?
    1. To delete antivirus software
    2. To slow down detection
    3. To gain access to sensitive files that aid in privilege escalation
    4. To hide payloads
<details closed> <summary>Answer</summary><p>Directory traversal can reveal sensitive configuration files, API keys, or password hashes. Attackers can then use this data in further attacks (e.g., privilege escalation or lateral movement).</p></details>

8. Which of the following best prevents directory traversal attacks?
    1. Running antivirus on the server
    2. Validating and restricting user input to expected filenames
    3. Using SQL parameterized queries
    4. Disabling JavaScript in the browser
<details closed> <summary>Answer</summary><p>The best defense is to validate input and restrict it to a safe list of allowed files or directories. Antivirus or JavaScript settings won’t stop traversal because it’s a server-side vulnerability.</p></details>
