## Activity Objectives

Students will practice using Splunk to perform foundational searches with SPL. They will learn how to identify when fields exist, apply wildcards to discover patterns in usernames, and detect failed login attempts across multiple log sources. The activity emphasizes building core search skills, applying Boolean logic, and filtering results to highlight meaningful security signals such as repeated failed logins and suspicious external traffic.
By the end of this activity, students will be able to:
1. Use SPL to search for events where specific fields exist.
2. Apply wildcards in searches to find usernames with common patterns.
3. Identify and filter failed login attempts in Apache and Nginx authentication logs.
4. Use Boolean expressions to combine or exclude conditions across multiple datasets.
5. Apply aggregations (e.g., counts, top values) to highlight usernames and IPs associated with repeated failures.



## Activity Instructions
Log into your Splunk environment and complete the following instructions:
1. Select "start searching" or open Search and Reporting, then  set a time range that includes your uploaded data.
2. Within the search bar search for all events where the `host` field exists.
<details closed> <summary>Answer</summary>
<code>host=*</code>
</details>

3. Create a SPL query that finds any event where a username field exists.
<details closed> <summary>Answer</summary>
<code>username=*</code>
</details>

4. Create a new SPL query that searches for usernames containing adm anywhere.
<details closed> <summary>Answer</summary>
<code>username=*adm*</code>
</details>

5. Create a new SPL query that searches the Apache authentication logs, and then identify the top usernames contained within the file using the "username" interesting field. Afterwards, go to the statistics tab to view.
<details closed> <summary>Answer</summary>
<img width="882" height="1074" alt="splunk_top_usernames_interesting_field" src="https://github.com/user-attachments/assets/76f5e4df-b6ee-421d-98f4-fb699d12d63f" />
<code>source="apache_authentication_logs_aug2025.csv"| top limit=20 username</code>
</details>

6. Create another SPL query that searches the Apache and Nginx authentication logs for failed logins (i.e. `auth_status="LOGIN_FAILURE"` and `auth_status="LOGIN_INVALID"`.
<details closed> <summary>Answer</summary>
<code>(source="apache_authentication_logs_aug2025.csv" OR source="nginx_authentication_logs_aug2025.csv") AND (auth_status="LOGIN_FAILURE"  OR auth_status="LOGIN_INVALID")</code>
</details>

7. Create an SPL query that searches for failed logins in both Apache and Nginx authentication logs by searching auth_status="LOGIN_INVALID" or auth_status="LOGIN_FAILURE", but excludes results from internal IP ranges 10.*.
<details closed> <summary>Answer</summary>
<code>source="apache_authentication_logs_aug2025.csv" OR source="nginx_authentication_logs_aug2025.csv" | search (auth_status="LOGIN_INVALID" OR auth_status="LOGIN_FAILURE") NOT src_ip="10.*"</code>
</details>

8. Create an SPL query that searches the Fortinet honeypot logs, and filters for the "Exfiltration", "Malware" and "Exploit" attack types where the action is log.
<details closed> <summary>Answer</summary>
<code>source="fortinet_honeypot_logs_aug2025.csv" | search (attack_type="Exfiltration" OR attack_type="Exploit" OR attack_type="Malware") | where action="log" </code>
</details>


