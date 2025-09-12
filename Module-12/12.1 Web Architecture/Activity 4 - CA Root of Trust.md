## Activity Objective

By the end of this activity, students will be able to identify and analyze the root, intermediate, and server certificates of secure websites, demonstrating their understanding of the chain of trust in public key infrastructure (PKI) and its role in ensuring secure online communications. Students will also be able to articulate the significance of each certificate within the chain and explain how they contribute to establishing trust in digital environments.

## Activity Instructions

- Identifying Certificates: Each group will visit a predetermined list of secure websites (e.g., https://www.thesolafoundation.org/, https://www.wikipedia.org, https://www.github.com). Optionally, students can select websites relevant to their interests as long as they are secure (HTTPS).
- Each student should record the following for each website: For server certificate: Common name, expiration date, and issuer, for Intermediate Certificate(s): Names and their issuers and for the root certificate: Name of the root CA (if visible) and its issuer.Submit the answers to the reflection questions.

### Steps to Inspect Certificates

#### For Google Chrome:
1. Click on the settings icon in the address bar.
2. Click on "Connection is secure" and then "Certificate is valid."
3. In the certificate window, go to the certificate details tab.
4. Navigate to the "Certification Path" tab to view the chain of trust.

#### For Firefox:
1. Click the padlock icon in the address bar.
2. Click on "Connection Secure" and then  select "More Information."
3. Click on "View Certificate" to open the certificate viewer.
4. View the leaf, intermediate, and root certificates.

### Reflection Questions
1. What new insights did you gain about root, intermediate, and server certificates? What is their purpose?
<details closed> <summary>Answer</summary><p>Learned that the server certificate is tied directly to the website I visit, while the intermediate certificate acts like a link between the server and the trusted root certificate. The root certificate comes from a certificate authority and is what my browser ultimately trusts. Their purpose is to prove the identity of websites and ensure the connection is secure.</p></details>

2. How do these certificates work together to form a chain of trust?
<details closed> <summary>Answer</summary><p>The server certificate is issued by an intermediate certificate, which in turn is trusted by a root certificate. My browser already trusts the root certificate, so by extension it trusts the others in the chain. This creates a verified path from the website back to a trusted authority.</p></details>

3. Why is it important to understand the role of certificates in secure online communication?
<details closed> <summary>Answer</summary><p>It is important because certificates confirm that a website is legitimate and that the information being communicated is encrypted. Without the use of these certificates, users could be tricked into connecting to a fake site or risk their data being intercepted.</p></details>

4. How does the chain of trust protect users from potential security threats?
<details closed> <summary>Answer</summary><p>The chain of trust protects users by preventing attackers from easily creating fake certificates. Since each step in the chain is verified by a trusted authority, it is much harder for malicious actors to impersonate a legitimate website.</p></details>

5. In what situations might you need to check or validate certificates outside of this classroom activity?
<details closed> <summary>Answer</summary><p>If you receive a browser warning about the site being insecure, or for example, if your job is to troubleshoot web connectivity issues or to set up a secure connection for the servers or APIs used by the company you work for.</p></details>

6. How does the ability to analyze a certificate chain be useful in your future role in IT or cybersecurity?
<details closed> <summary>Answer</summary><p>It would help you to diagnose why a secure connection is failing, ensure that servers are configured correctly, and verify that users are protected from attacks. Being able to confirm trust in a digital certificate is critical for spotting misconfigurations or suspicious activity.</p></details>
