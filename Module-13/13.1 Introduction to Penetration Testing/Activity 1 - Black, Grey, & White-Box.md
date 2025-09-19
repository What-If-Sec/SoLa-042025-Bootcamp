#3 Activity Objective

Students will evaluate and identify the appropriate type of penetration testing—white box, black box, or gray box—based on a client’s security objectives, available information, and risk concerns. By analyzing real-world scenarios, students will demonstrate their understanding of the advantages, limitations, and application of each testing methodology, ultimately recommending the most suitable approach to ensure comprehensive security assessment for the client.

## Activity Instructions

Complete the knowledge check below

### Knowledge Check
1. Read the scenario , and determine if white, black, or grey-box pentesting is needed. "A large financial institution is developing a new API that will handle sensitive customer financial data. They want to ensure the API is secure from potential insider threats as well as external attackers. The development team is willing to provide access to the API’s source code and architecture."
    1. White Box
    2. Black Box
    3. Grey Box
<details closed> <summary>Answer</summary><p>In this scenario, the most appropriate approach is white-box penetration testing because the development team is providing full access to the API’s source code and architecture. White-box testing allows testers to thoroughly analyze the system’s internal logic, data flows, and authentication mechanisms, which is especially important for a financial institution handling sensitive customer data. This method not only simulates potential external attackers but also accounts for insider threats by evaluating how someone with detailed system knowledge might exploit vulnerabilities. Since black-box testing would only assess external attacks and grey-box would involve limited access, white-box testing is the best choice to ensure the highest level of security assurance for the new API.</p></details>

2. Read the scenario , and determine if white, black, or grey-box pentesting is needed. "A popular e-commerce company is concerned about the possibility of being hacked by an external attacker. They want to know how vulnerable their website and backend systems are without providing the testing company any internal information about their infrastructure."
    1. White Box
    2. Grey Box
    3. Black Box
<details closed> <summary>Answer</summary><p>In this scenario, the most appropriate approach is black-box penetration testing because the e-commerce company is specifically concerned about attacks from external hackers and does not want to provide any internal details about their systems. Black-box testing simulates the perspective of an outside attacker with no prior knowledge of the target’s infrastructure, focusing on discovering vulnerabilities in the website and backend systems through reconnaissance, scanning, and exploitation attempts. Since the goal is to understand how exposed the systems are to real-world external threats, black-box testing is the best fit, whereas white-box or grey-box testing would not align with the company’s request to withhold internal information.</p></details>

3. Read the scenario , and determine if white, black, or grey-box pentesting is needed. "A healthcare organization needs to ensure its internal network is secure to comply with industry regulations (HIPAA). They want to test both internal vulnerabilities and external threats. The organization is willing to share partial network diagrams and basic access credentials."
    1. Grey Box
    2. White Box
    3. Black Box
<details closed> <summary>Answer</summary><p>In this scenario, the most appropriate approach is grey-box penetration testing because the healthcare organization is providing partial information such as network diagrams and basic credentials, but not full access to all internal details like source code or complete infrastructure documentation. Grey-box testing allows testers to assess both internal vulnerabilities, which is crucial for HIPAA compliance, and external threats, simulating how an attacker with limited insider knowledge might attempt to exploit the system. This balanced approach provides a realistic evaluation of security risks while aligning with the organization’s willingness to share only partial information.</p></details>

4. Read the scenario , and determine if white, black, or grey-box pentesting is needed. "A startup has developed a mobile app for managing personal finance and wants to ensure it is secure before launching. They are reluctant to share detailed information about the app’s source code but still need assurance that both the app and backend services are protected from potential attacks."
    1. White  Box
    2. Grey Box
    3. Black Box
<details closed> <summary>Answer</summary><p>In this scenario, the most appropriate approach is grey-box penetration testing because the startup is not willing to share full access to the app’s source code (which rules out white-box testing) but still needs more than just the limited perspective of a black-box test. Grey-box testing strikes a balance by simulating an attacker with partial knowledge, such as access to the app itself and some insights into how it interacts with backend services, without exposing all internal details. This approach provides a realistic assessment of vulnerabilities that could affect both the mobile app and its backend systems while respecting the company’s reluctance to disclose complete source code information.</p></details>

5. Read the scenario , and determine if white, black, or grey-box pentesting is needed. "A government agency is deploying a secure communications system that will be used internally by high-ranking officials. They are primarily concerned about insider threats and want to thoroughly assess the system's internal security, but also want to ensure it’s not vulnerable to external attacks."
    1. White Box
    2. Black Box
    3. Grey Box
<details closed> <summary>Answer</summary><p>In this scenario, the most appropriate approach is white-box penetration testing because the government agency is primarily concerned about insider threats and wants a deep assessment of the system’s internal security. White-box testing provides testers with full knowledge of the system’s architecture, source code, and configurations, allowing them to uncover logic flaws, privilege escalation risks, and other insider-related vulnerabilities. At the same time, it enables a comprehensive review of potential external attack surfaces, ensuring the system is also protected against outside threats. Since the agency requires both internal and external assurance, white-box testing offers the most thorough and effective evaluation.</p></details>
