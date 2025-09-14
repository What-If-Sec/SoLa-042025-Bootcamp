## Activity Objective

Students will use Burp Suite to complete PortSwigger's SQL injection (SQLi) lab. By the end of this activity, students will be able to intercept and manipulate web requests, identify SQL injection vulnerabilities, exploit these vulnerabilities to retrieve sensitive information from databases, and understand the impact of insecure query handling in web applications.



## Activity Instructions

Follow the instructions below:
1. Read the information provided by PortSwigger about SQLi [here](https://portswigger.net/web-security/sql-injection#what-is-sql-injection-sqli) to complete the knowledge check below.
2. Once the knowledge check is completed, complete the lab found [here](https://portswigger.net/web-security/sql-injection/lab-retrieve-hidden-data).

### Knowledge Check
1. What is SQL injection (SQLi)?
    1. An attack that exploits vulnerabilities in JavaScript functions
    2. An attack that injects malicious SQL statements into a database query
    3. An attack that modifies network packets in transit
    4. An attack that installs a backdoor on the server
<details closed> <summary>Answer</summary><p>SQL injection occurs when an attacker manipulates user input to inject SQL commands into a query. This can allow unauthorized access to, or manipulation of, a database.</p></details>

2. During testing, a penetration tester enters the following into a login form’s username field:
`' OR '1'='1`
Why is this input commonly used to identify SQL injection vulnerabilities?
    1. Because it forces the database query condition to always be true
    2. Because it causes the database to return a syntax error every time
    3. Because it encrypts the query and hides the response from the server
    4. Because it prevents the database from running any SQL commands
<details closed> <summary>Answer</summary><p>The input ' OR '1'='1 is a classic SQL injection test string. It works by modifying the SQL query’s logic so that the condition is always true (e.g., WHERE username='' OR '1'='1'). If the application is vulnerable, this payload can bypass authentication and log the tester in without valid credentials. The fact that this input succeeds is a strong indicator of a SQL injection flaw..</p></details>

3. Which type of SQL injection directly displays error messages from the database that attackers can use to craft further payloads?
    1. Blind SQLi
    2. Error-based SQLi
    3. Union-based SQLi
    4. Time-based SQLi
<details closed> <summary>Answer</summary><p>Error-based SQL injection takes advantage of database error messages returned by the application, revealing details about database structure and queries.</p></details>

4. A penetration tester enters:
`' UNION SELECT username, password FROM users --`
into a vulnerable input field. What type of SQL injection is this?
    1. Error-based SQLi
    2. Time-based SQLi
    3. Boolean-Based SQLi 
    4. Union-based SQLi
<details closed> <summary>Answer</summary><p>Union-based SQLi is an in-band SQL injection technique that leverages the UNION SQL operator to combine the results of two or more SELECT statements into a single result which is then returned as part of the HTTP response.</p></details>

5. Which of the following is a sign that a site may be vulnerable to SQL injection? Select all that apply.
    1. The application reveals unexpected database contents in the response
    2. The page loads very quickly
    3. The page displays SQL syntax error messages
    4. The server returns a 5XX error message
    5. The page response time changes significantly when unusual input is provided
    6. The database returns a result due to an always true condition
<details closed> <summary>Answer</summary><p>SQLi vulnerabilities can often be spotted by the way an application and its database respond to unexpected input. If the page displays raw SQL syntax errors, it shows that user input is being directly inserted into queries without proper handling. When a database returns results because of an always true condition, it indicates that injected logic is altering the intended query structure. Similarly, if the application unexpectedly reveals raw database contents, such as rows or column data not normally accessible, it strongly suggests unsanitized queries. Finally, if the page’s response time changes significantly when unusual input is provided, this can indicate blind SQL injection where timing functions are used to confirm injection. Together, these behaviors are clear signs that the application is vulnerable to SQL injection.</p></details>

6. What type of SQLi is used when the application does not display database errors but attackers infer results based on page behavior or timing?
    1. Union-based SQLi
    2. Boolean-based SQLi
    3. Error-based SQLi
    4. Blind SQL injection
<details closed> <summary>Answer</summary><p>Blind SQL injection relies on observing changes in the application’s response or execution time, since no error messages are displayed. Enabling an attacker to reconstruct the database's structure.</p></details>

7. Why is it dangerous for developers to dynamically building build SQL queries with string concatenation?
    1. It allows user input to change the intended SQL command
    2. It always slows down database performance
    3. It makes queries harder to read for developers
    4. It requires more server storage
<details closed> <summary>Answer</summary><p>When queries are built with string concatenation, malicious user input can alter the logic of the SQL command, making the application vulnerable to injection.</p></details>

8. SQLi is not limited to login forms or simple SELECT statements. Which of the following are common locations where SQL injection vulnerabilities may arise? Select all that apply.
    1. In an UPDATE statement, inside the WHERE clause
    2. In an INSERT statement, within the values being inserted
    3. In a DROP TABLE statement that is hardcoded and does not use user input
    4. In a SELECT statement, when user input is used as a table or column name
    5. In a SELECT statement where only constant strings are used and no user input is concatenated
    6. In a SELECT statement, inside the ORDER BY clause
<details closed> <summary>Answer</summary><p>SQLi vulnerabilities can occur anywhere user input is included in a query without proper sanitization or parameterization. This risk is not limited to login forms or simple SELECT statements. It can appear in UPDATE statements, either in the values being set or in the WHERE clause, in INSERT statements where user-provided values are written into the database, or in SELECT statements where input controls table names, column names, or even clauses such as ORDER BY. In contrast, queries that do not use user input, such as hardcoded DROP TABLE commands or queries built only from constant strings, are not vulnerable. The key point is that any part of a query that incorporates unsanitized user input can be exploited by an attacker.</p></details>

9. Why is it dangerous for developers to dynamically building build SQL queries with string concatenation?
    1. Disabling JavaScript on the client browser
    2. Using input validation and sanitization
    3. Using output encoding
    4. Using parameterized queries (prepared statements)
<details closed> <summary>Answer</summary><p>The most effective defense against SQL injection is parameterized queries (prepared statements). These ensure that user input is always treated as data and never as part of the SQL command, no matter what is entered. Input validation and sanitization can reduce risk but cannot cover every case on their own. Output encoding is helpful for preventing XSS but is not a defense against SQL injection. Disabling JavaScript on the client side has no effect because SQL injection occurs on the server side in the database.</p></details>

10. Which of the following tools is commonly used to test for SQL injection vulnerabilities?
    1. Wireshark
    2. Nmap
    3. sqlmap
    4. Metasploit
<details closed> <summary>Answer</summary><p>sqlmap is an automated tool specifically designed to detect and exploit SQL injection vulnerabilities.</p></details>
