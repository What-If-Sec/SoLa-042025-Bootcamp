## Activity Objective:
Students will learn and apply passive reconnaissance techniques to gather publicly available information about a target without directly interacting with the target’s systems. By the end of the activity, students will be able to utilize OSINT tools and resources, such as domain registries, social media, and public databases, to perform reconnaissance in an ethical manner, and understand how attackers leverage this information in the early stages of a cyber attack.

> **ALERT!!!**
> 
> Google dorking by itself is not illegal because it simply uses Google’s advanced search operators such as site:, filetype:, or intitle: to filter search results that are already publicly available.
>
> _The legality depends on intent and use._
>
> It is legal and ethical to practice with harmless file types like PDFs or text documents, to search your own websites or lab environments, and to use it as part of authorized security assessments.
>
> It becomes illegal and unethical when it is used to attempt to access or download sensitive information such as passwords, private databases, or configuration files from systems you do not own or have permission to test, or when the information is used for exploitation or unauthorized access.
>
> The key takeaway is that Google dorking should be thought of as a reconnaissance tool, valuable for learning how attackers think and for auditing your own systems, but it must always be used within the boundaries of lawful and authorized practice  

## Activity Instructions:
Students will use a series of predefined Google Dorks to find publicly available information that could be useful in an OSINT investigation. 
1. Search for only web pages that belong to thesolafoundation.org domain by using `site:` google dork.
<details closed> 
  <summary>Answer</summary>
  <code>site:thesolafoundation.org</code>
</details>

2. Search for PDF, Word, and Excel documents hosted on SoLa’s website by combining the `site:` Google dork with either the `filetype:` or `ext:` Google dork.
<details closed> 
  <summary>Answer</summary>
  <code>site:thesolafoundation.org (filetype:pdf OR filetype:docx OR filetype:xlsx)</code>
</details>

3. DO NOT ATTEMPT TO LOGIN. Search for login pages used by educational domains by using the `site:` and `inurl:` google dorks.
<details closed> 
  <summary>Answer</summary>
  <code>site:.edu inurl:login</code>
</details>

4. DO NOT ATTEMPT TO LOGIN. Search for admin pages used by educational domains by using the `site:` and `inurl:` google dorks.
<details closed> 
  <summary>Answer</summary>
  <code>site:.edu inurl:admin</code>
</details>

5. DO NOT CLICK ON RESULTS. Search for backup or archive files (such as .zip, .7z, .bak, .tar., .gz, etc.) used by organization domains by using the `site:` and `ext:` google dorks.
<details closed> 
  <summary>Answer</summary>
  <code>site:.org (ext:zip OR ext:7z OR ext:bak OR ext:tar OR ext:gz)</code>
</details>

6. DO NOT CLICK ON RESULTS. When directory browsing is not disabled on a web server, the server automatically generates a page titled “Index of” that displays the contents of a folder, including all files and subdirectories inside it. To search for exposed directory listings on organization domains, use the `intitle:` and `site:` google dorks.
<details closed> 
  <summary>Answer</summary>
  <code>intitle:"Index of" site:.org</code>
</details>

7. DO NOT CLICK ON RESULTS. Many camera systems ship with a default web interface that includes the path /view/view.shtml.  Search for publicly available cameras using `inurl:view/view.shtml`. These are examples of misconfiguration and poor access control, exposing cameras or other IoT device interfaces directly to the internet without authentication.
<details closed> 
  <summary>Answer</summary>
  <code>inurl:view/view.shtml</code>
</details>

### Reflection Questions
Answer the reflection questions below, and submit your answers.
1. What kinds of information can be learned by limiting a search to a specific domain with the site: operator?
<details closed> 
  <summary>Answer</summary>
  <p>By using the site: operator, you can find all publicly accessible pages, files, and resources hosted under a specific domain. This helps reveal what content is indexed by search engines, including subpages, documents, and sometimes areas of the site that the organization may not realize are publicly visible.</p>
</details>

2. Why might attackers use this technique during the reconnaissance phase of an attack? How could defenders use the same method to audit their own organization’s online footprint?
<details closed> 
  <summary>Answer</summary>
  <p>Attackers use site: searches to map out a target’s online presence, identify potential entry points, and find sensitive files or login portals. Defenders can use the same technique to see what information about their organization is exposed online, allowing them to identify and secure unintended disclosures before attackers exploit them.</p>
</details>

3. When organizations leave documents such as PDFs, Word files, or Excel spreadsheets publicly accessible, what types of sensitive information could accidentally be exposed in these files?
<details closed> 
  <summary>Answer</summary>
  <p>These files may contain sensitive data such as internal procedures, financial records, employee or customer personal data, meeting notes, contracts, or technical details about systems and networks. Even metadata inside the documents can reveal usernames, software versions, or other useful details for attackers.</p>
</details>

4. What security controls could help prevent sensitive documents from being indexed by search engines?
<details closed> 
  <summary>Answer</summary>
  <p>Organizations can use robots.txt files to block crawlers, apply access controls (authentication/authorization), and restrict directories that contain sensitive documents. Additionally, sensitive data should be stored in secure internal systems rather than on publicly accessible web servers.</p>
</details>

5. What are the risks of leaving login portals easily discoverable on the open internet?
<details closed> 
  <summary>Answer</summary>
  <p>Exposed login portals become easy targets for brute-force attacks, credential stuffing, and phishing campaigns. They also help attackers quickly identify entry points into critical systems.</p>
</details>

6. What makes exposed admin pages especially dangerous compared to general login pages?
<details closed> 
  <summary>Answer</summary>
  <p>Admin pages often provide direct access to system configuration and privileged functions. If compromised, attackers can take complete control of the system, modify settings, steal data, or create new accounts, making the impact much more severe than a normal user login page.</p>
</details>

7.  Why would attackers be interested in finding backup or archive files such as .zip, .bak, or .tar.gz?
<details closed> 
  <summary>Answer</summary>
  <p>Backups and archives may contain full copies of databases, source code, credentials, or other sensitive internal data. If left publicly accessible, attackers can download them and gain a complete picture of the organization’s systems.</p>
</details>

8. What kinds of files could attackers discover when directory listing is left enabled?
<details closed> 
  <summary>Answer</summary>
  <p>Attackers might find configuration files, scripts, backups, logs, or hidden resources not intended for public access. These files can expose vulnerabilities, credentials, or technical details that aid further attacks.</p>
</details>

9. What measures should administrators take to disable directory listing and protect web server contents?
<details closed> 
  <summary>Answer</summary>
  <p>Admins should configure the web server (e.g., Apache, Nginx, IIS) to disable directory listing, enforce least privilege file permissions, and ensure sensitive files are never stored in publicly accessible directories.</p>
</details>

10. What best practices should organizations follow to secure IoT devices from being indexed or accessed publicly? How could attackers abuse access to exposed devices?
<details closed> 
  <summary>Answer</summary>
  <p>IoT devices should be placed behind firewalls, require strong authentication, use encrypted communication, and avoid default credentials. Devices should not be directly exposed to the internet. If attackers gain access, they could spy through cameras, disrupt operations, or pivot into the internal network to launch broader attacks.</p>
</details>

