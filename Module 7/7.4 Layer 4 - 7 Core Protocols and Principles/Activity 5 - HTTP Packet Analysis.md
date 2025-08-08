## Activity Objective

By completing this quiz, students will demonstrate their understanding of how HTTP works, including common HTTP methods, header fields, and status codes. Students will also learn how to use basic Wireshark filters to analyze HTTP traffic and identify HTTP request types. In addition, students will be able to explain why HTTP is considered insecure and has been replaced by HTTPS, and recognize what different HTTP error codes mean in real-world web communication scenarios.



## Activity Instructions

Complete the knowledge check.

## Knowledge Check
1. Which HTTP method is typically used to retrieve data from a web server?
   1. POST
   2. GET
   3. PUT
   4. DELETE
<details closed>
<summary>Answer</summary>
The GET method is used to request data from a server. It should not change the server state.</details>

2. Which HTTP method is used when sending data to a server?
   1. GET
   2. PATCH
   3. POST
   4. HEAD
<details closed>
<summary>Answer</summary>
POST is commonly used to send data to a server</details>

3. What is the purpose of the HTTP HEAD method?
   1. To delete a resource
   2. To send a file or data to a server
   3. To check which HTTP methods are supported
   4.  To retrieve the headers of a resource, excluding the body.  
<details closed>
<summary>Answer</summary>
HEAD is used to fetch the headers of a resource to check its metadata (e.g., content type or size) without downloading the content. </details>

4. Which HTTP method is used to update or replace an existing resource entirely?
   1. PUT
   2. POST
   3. PATCH
   4. OPTIONS
<details closed>
<summary>Answer</summary>
PUT updates or creates a resource at a specific URI. If the resource exists, it is replaced. If not, it may be created.</details>

5. Which HTTP method is used to make a partial update to an existing resource?
   1. HEAD
   2. PATCH
   3. POST
   4. PUT
<details closed>
<summary>Answer</summary>
PATCH applies partial modifications to a resource, unlike PUT, which replaces the entire resource. 
</details>

6. Which HTTP method is used to remove a specified resource from the server?
   1. DELETE
   2. GET
   3. HEAD
   4. PUT
<details closed>
<summary>Answer</summary>
DELETE tells the server to remove the resource identified by the request URI.
</details>

7. Which HTTP method is used to find out which HTTP methods are supported by a server on a specific resource?
   1. TRACE
   2. HEAD
   3. OPTIONS
   4. GET
<details closed>
<summary>Answer</summary>
OPTIONS is used by clients to query what HTTP methods are supported by the server, often for CORS (Cross-Origin Resource Sharing) checks. </details>

8. Which HTTP method is used to find out which HTTP methods are supported by a server on a specific resource?
   1. POST
   2. OPTIONS
   3. TRACE
   4. CONNECT
<details closed>
<summary>Answer</summary>
CONNECT is used to establish a network connection to another server, typically for tunneling HTTPS requests through an HTTP proxy. </details>

9. Which HTTP method is used to echo the received request back to the client, mainly for diagnostic purposes?
   1. DELETE
   2. POST
   3. OPTIONS
   4. TRACE
<details closed>
<summary>Answer</summary>
TRACE is a diagnostic method used to see what is received by the server and how intermediaries (like proxies) alter the request. </details>

10. True or False: A 200 status code means the request was successful.
     1. True
     2. False
<details closed>
<summary>Answer</summary>
A 200 OK means the server successfully processed the request and returned the expected content. </details>

11. True or False: A 404 error means the server encountered an unexpected condition.
     1. True
     2. False
<details closed>
<summary>Answer</summary>
A 404 Not Found means the server couldn’t find the requested resource. A server error would be a 500-level code. </details>

12. What does an HTTP 403 status code mean?
     1. The resource was not found
     2. Access is forbidden
     3. The server is temporarily unavailable
     4. The request was not successful
<details closed>
<summary>Answer</summary>
 A 403 Forbidden means the server understood the request but refuses to authorize it. </details>

13. Which HTTP method is used to echo the received request back to the client, mainly for diagnostic purposes?
     1. 200
     2. 301
     3. 400
     4. 500
<details closed>
<summary>Answer</summary>
A 400 Bad Request indicates that the client sent a malformed or invalid request. </details>

14. Which of the following indicates a redirect?
     1. 404
     2. 200
     3. 302
     4. 401
<details closed>
<summary>Answer</summary>
 A 302 Found means the resource was temporarily moved to a different URI, prompting the client to redirect.
</details>

15. Which HTTP header tells the server what type of content the client is expecting?
     1. Content-Type
     2. User-Agent
     3. Host
     4. Accept
<details closed>
<summary>Answer</summary>
The Accept header tells the server which content types (e.g., HTML, JSON) the client prefers.
</details>


16. What does the User-Agent header typically include?
     1. Operating system and browser of the client
     2. IP address of the client
     3. Type of content being sent
     4. Response time
<details closed>
<summary>Answer</summary>
User-Agent describes the client’s browser and OS, used for analytics or compatibility adjustments.
</details>

17. Which header is used to indicate the size of the message body in bytes?
     1. Content-Length
     2. User-Agent
     3. Content-Language
     4. HOST
<details closed>
<summary>Answer</summary>
Content-Length tells the server or client how many bytes are in the body of the message.
</details>

18. What is the purpose of the Host header in an HTTP/1.1 request?
<details closed>
<summary>Answer</summary>
It specifies the domain name of the server being requested. This is necessary because multiple domains can be hosted on the same IP address (known as virtual hosting).
</details>

19. You send a POST request to a server and receive a 500 Internal Server Error. What might have gone wrong?
<details closed>
<summary>Answer</summary>
A 500 error is a general server-side error and not caused by the client’s request directly. This means that the server encountered an unexpected condition, such as a bug in server-side code or misconfiguration.
</details>

20. A client sends a GET request and receives a 301 Moved Permanently response. What should the client do next?
<details closed>
<summary>Answer</summary>
A 301 tells the client the resource has been permanently moved. The client should use the new URI/ URL  provided in the Location header in future requests.
</details>

21. What port is used by HTTP?
     1. TCP Port 110
     2. TCP Port 143
     3. TCP Port 25
     4. TCP Port 80
<details closed>
<summary>Answer</summary>
Content-Length tells the server or client how many bytes are in the body of the message.
</details>

22. Open the PCAP file located [here](https://drive.google.com/file/d/1okpRzYCj8Ka9Exr5mCFqozJ32ymwzqlD/view?usp=drive_link) and inspect the HTTP requests and responses to identify:
     1. What pieces of Personally Identifiable Information (PII) can you clearly view?
     2. Why sending data over HTTP is considered insecure?
<details closed>
<summary>Answer</summary>
The name  "michael", email "mike@mike.com", and phone number "323-323-2323" were disclosed. This is because HTTP does not encrypt data, and as a result, anyone that is intercepting the network traffic (for example, via packet sniffing tool like Wireshark on a public Wi-Fi) would be able to read any sensitive information sent over the network.
</details>
