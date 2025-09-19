## Activity Objective:

Students will learn how to use Shodan.io, a search engine for internet-connected devices, to gather publicly accessible information (OSINT) on devices and services exposed to the internet. By completing this activity, students will understand how attackers use Shodan to identify potential attack targets and how to apply this knowledge ethically for cybersecurity purposes.



> Important Notes:#1 Do not attempt to login or access any system you find#2 The goal is to observe what information is available, not to interact with it#3 Think about how attackers might misuse this information and research how defenders could use it to secure their own systems.



## Activity Instructions:
Students will use shodan.io to find publicly available information that could be useful in an OSINT investigation. 
1. Go to shodan.io and register for an account here.
2. Go to the dashboard of shodan.io.Search for any exposed servers running SSH by searching for "port 22".
3. Search for any exposed FTP servers by searching for "port 21".
4. Search for any exposed IOT devices such as: Alexa, Ring, etc.

### Reflection Questions
1. What did you learn about the types of devices and services that are exposed to the internet and visible on Shodan?
<details closed> 
  <summary>Answer</summary>
  <p>Students may learn that Shodan reveals a wide range of devices and services exposed to the internet, including servers, webcams, routers, IoT devices, and common services like SSH, FTP, and RDP. </p>
</details>

2. Why might it be risky for organizations to leave services like SSH or FTP publicly accessible without additional security controls?
<details closed> 
  <summary>Answer</summary>
  <p>Students will recognize that leaving services like SSH or FTP exposed without proper protections increases the risk of brute-force attacks, unauthorized access, and data breaches.</p>
</details>

3. How could attackers misuse the information gathered from Shodan searches?
<details closed> 
  <summary>Answer</summary>
  <p>Students may realize that attackers can misuse Shodan data to identify vulnerable systems, locate misconfigured devices, and target organizations for exploitation or ransomware attacks.</p>
</details>

4. In what ways could defenders or system administrators use Shodan to strengthen their organization’s security posture?
<details closed> 
  <summary>Answer</summary>
  <p>Students may realize that defenders can use Shodan proactively to audit their own digital footprint, detect misconfigured or exposed services, and reduce the attack surface by hardening or removing unnecessary services.</p>
</details>

5. What connections can you make between this activity and real-world OSINT investigations or penetration testing practices?
<details closed> 
  <summary>Answer</summary>
  <p>Students may connect this activity to real-world OSINT and penetration testing, where similar reconnaissance techniques are used to gather information on targets, assess risks, and plan defense or exploitation strategies.</p>
</details>

