## Activity Objective

Students will use Burp Suite to complete PortSwigger's Reflected XSS lab. By the end of this activity, students will be able to intercept and modify web traffic, identify and exploit reflected cross-site scripting (XSS) vulnerabilities, and understand the security implications of improper input validation on web applications.

## Activity Instructions

Follow the instructions below:
1. Complete the knowledge check using the information provided by PortSwigger about XSS [here](https://portswigger.net/web-security/cross-site-scripting#what-is-cross-site-scripting-xss).
2. Once the knowledge check is completed, complete the lab found [here](https://portswigger.net/web-security/cross-site-scripting/reflected/lab-html-context-nothing-encoded).

### Knowledge Check
1. What does XSS (Cross Site Scripting) primarily allow an attacker to do?
    1. Modify server-side configuration files
    2. Inject malicious scripts into webpages viewed by other users
    3. Steal network packets between client and server
    4. Exploit buffer overflows on the server
<details closed> <summary>Answer</summary><p>XSS is a client-side attack that injects malicious code (usually JavaScript) into web pages. When other users view the page, their browsers execute the script. It does not directly alter server files or exploit buffer overflows.</p></details>

2. Which of the following is NOT a type of XSS?
    1. Stored XSS
    2. Reflected XSS
    3. DOM-based XSS
    4. Encrypted XSS
<details closed> <summary>Answer</summary><p>The three main types of XSS are Stored, Reflected, and DOM-based. "Encrypted XSS" is not a recognized category.</p></details>

3. In a Stored XSS attack, where is the malicious payload typically injected?
    1. Directly into the browser’s memory
    2. Inside the victim’s local storage only
    3. Into a server database, comment field, or forum post
    4. In a packet capture file
<details closed> <summary>Answer</summary><p>Stored XSS happens when malicious input is saved on the server (e.g., in a database or post). Every time the stored data is displayed, the script runs for all users who see it.</p></details>

4. Which scenario best describes Reflected XSS?
    1. The malicious payload is included in a URL and reflected back in the HTTP response
    2. Malicious input is saved on the server and shown to many users
    3. The attacker manipulates the Document Object Model (DOM) without server interaction
    4. JavaScript is enabled, so the script executes
<details closed> <summary>Answer</summary><p>Reflected XSS occurs when malicious code is placed in a URL or request and immediately "reflected" in the web page response, usually affecting only the victim who clicks the malicious link.</p></details>

5. What is unique about DOM-based XSS compared to Stored or Reflected XSS?
    1. It happens entirely in the browser, without modifying the server’s response
    2. It requires JavaScript to be enabled
    3. It can be prevented with input validation
    4. It affect one victim at a time
<details closed> <summary>Answer</summary><p>DOM-based XSS is triggered when insecure JavaScript in the browser modifies the page’s DOM with untrusted input. The attack never reaches the server.</p></details>

6. Which of the following user inputs would be most suspicious for an XSS vulnerability?
    1. `<p> alert('Gotcha!')</p>`
    2. `<script>alert('Hacked!')</script>`
    3. `<h1>It Worked!</h1>`
    4. `<head> <title>Hacked!</title> </head>`
<details closed> <summary>Answer</summary><p>The <script> tag with JavaScript inside is the most suspicious because it is the classic XSS payload used to test whether user input is executed in the browser. The other options are normal HTML tags that may change how text is displayed but don’t execute JavaScript.</p></details>

7. Which mitigation technique is the most effective for preventing XSS?
    1. Running antivirus on the server
    2. Using only HTTPS instead of HTTP
    3. Encoding and sanitizing user input before rendering on the page
    4. Blocking all users from submitting text
<details closed> <summary>Answer</summary><p>The best defense against XSS is a combination of input validation and output encoding. Input validation ensures that user data matches the expected format, such as allowing only numbers in a phone number field or requiring a proper email structure in an email field, which prevents malicious code from being accepted in the first place. Output encoding, on the other hand, converts special characters like <, >, and " into harmless representations (&lt;, &gt;, &quot;) before displaying them in the browser. This prevents the browser from interpreting user input as executable code, ensuring that even if attackers attempt to inject scripts, their input is displayed as plain text instead of being executed.</p></details>

8. Why is XSS dangerous for users?
    1. It can force users to download malicious files without their knowledge
    2. It shuts down the web server immediately
    3. It only affects the attacker’s own browser
    4. It can allow attackers to steal cookies, sessions, and sensitive data
<details closed> <summary>Answer</summary><p>XSS can steal cookies, hijack sessions, or trick users into actions they didn’t intend. It’s dangerous because it targets end users rather than the server directly.</p></details>

9. You enter the text `<b>Hello</b>` into a website’s comment box. When the page reloads, the comment shows up as bold text instead of showing the `<b>` tags. What does this most likely indicate?
    1. The site is escaping or sanitizing HTML properly
    2. The site is vulnerable to Stored XSS
    3. The site is vulnerable to Reflected XSS
    4. The site is ignoring all user input
<details closed> <summary>Answer</summary><p>If the site displays the text in bold, it means the HTML tags were rendered as code, not as plain text. Since the input was not displayed literally i.e. `<b>Hello</b>` this indicates that the application is processing the HTML tags and is not implementing input sanitization or output encoding. As a result, the site is vulnerable to Stored XSS.</p></details>

10. You test a website’s feedback form by submitting the input:
`<img src="invalid-image.jpg" onerror="alert('XSS')">`
When the page reloads, a popup alert box appears in your browser. What does this result tell you?
    1. The site is safe because images are harmless
    2. The site is vulnerable to Reflected XSS
    3. The site is vulnerable to DOM-based XSS
    4. The site is not escaping or sanitizing HTML properly
<details closed> <summary>Answer</summary><p>If an <img> tag with an onerror event executes JavaScript when the image fails to load, it means the application is not properly sanitizing or encoding the input. This proves the page is vulnerable to Stored XSS because attackers can inject malicious code through image attributes like onerror.</p></details>

11. You click a malicious link sent in an email:
`http://example.com/search?term=<img src="notfound.jpg" onerror="alert('XSS')">`
When the page loads, the search results page immediately executes the script and shows a popup. What does this behavior indicate?
    1. The site is only vulnerable if you click the link
    2. The site is vulnerable to Reflected XSS
    3. The site is vulnerable to Dom-Based XSS
    4. The site is only vulnerable if you log in
<details closed> <summary>Answer</summary><p>This is Reflected XSS because the malicious payload is injected in the URL query string and immediately reflected in the web page response without sanitization. The script is not stored on the server, so it only runs for users who click the crafted link. Unlike DOM-based XSS, this payload appears in the server’s response, not just client-side JavaScript.</p></details>

12. A website uses JavaScript to read the value from the URL fragment (#) and insert it into the page without sanitization. You visit:
`http://example.com/#<img src="invalid.jpg" onerror="alert('DOM XSS')">`
When the page loads, the browser executes the payload and shows a popup, even though the server’s response did not contain your input. What does this behavior indicate?
    1. The input was stored on the server and displayed to all users
    2. The payload is only dangerous if cookies are enabled
    3. The vulnerability is caused by insecure client-side JavaScript
    4. The vulnerability depends on the backend
<details closed> <summary>Answer</summary><p>For this attack the payload never reaches the server; instead, client-side JavaScript (e.g., using document.write or innerHTML) is inserted into the page’s DOM. As a result, the payload unlike with Stored XSS, it is not saved to the server, and unlike Reflected XSS, it is not included in the server’s response; instead the attack occurs entirely in the browser.</p></details>
