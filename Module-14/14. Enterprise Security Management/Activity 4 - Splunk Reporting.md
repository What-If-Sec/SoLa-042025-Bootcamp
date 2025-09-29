## Activity Objections

By the end of this activity, students will be able to create and save reports in Splunk by writing SPL searches, applying filters, and adding visualizations. Students will understand how reports transform raw log data into reusable insights that highlight patterns, trends, and security events of interest .

## Activity Instructions
Complete the following instructions below:
1. Open Search and Reporting and set a time range that includes your uploaded data. In the search bar, search for Nginx and Apache authentication logs.
<details closed> <summary>Answer</summary>
<code>source="apache_authentication_logs_aug2025.csv" OR source="nginx_authentication_logs_aug2025.csv"</code>
</details>

2. Add a new field to normalize login results by piping the `eval` command to create a field called "LOGIN", and set "LOGIN" equal to "FAILURE" if "auth_status" is either "LOGIN_FAILED" or "LOGIN_INVALID"; otherwise set LOGIN equal to "SUCCESSFUL".
<details closed> <summary>Answer</summary>
<code>source="apache_authentication_logs_aug2025.csv" OR source="nginx_authentication_logs_aug2025.csv" | eval LOGIN = if(auth_status="LOGIN_FAILED" OR auth_status="LOGIN_INVALID", "FAILURE","SUCCESSFUL")</code>
</details>

3. Save your search and create a report titled "Web Server Login Report".
4. Modify your search to include the top 10 requested web pages (requested_uri).
<details closed> <summary>Answer</summary>
<code>source="apache_authentication_logs_aug2025.csv" OR source="nginx_authentication_logs_aug2025.csv"  | eval LOGIN = if(auth_status="LOGIN_FAILED" OR auth_status="LOGIN_INVALID", "FAILURE","SUCCESSFUL")| top limit=20 request_uri</code>
</details>

5. Go to the statistics tab, and save your search to create a report titled "Most Requested Web Pages Report".
6. In the search bar, start a new search and limit your search to Cisco firewall logs.
<details closed> <summary>Answer</summary>
<code>source="cisco_firewall_logs_aug2025.csv"</code>
</details>

7. Pipe the `search` command so that you can only see events where the action field shows that the connection was denied or blocked.
<details closed> <summary>Answer</summary>
<code>source="cisco_firewall_logs_aug2025.csv" | search action=DENY OR action=BLOCK</code>
</details>

8. Pipe the `stat` command to count how many times each unique combination of source IP, destination IP, destination port, and protocol occurs.
<details closed> <summary>Answer</summary>
<code>source="cisco_firewall_logs_aug2025.csv" | search action=DENY OR action=BLOCK | stats count by src_ip, dst_ip, dst_port, protocol</code>
</details>

9. Pipe the `sort` command to arrange the results so the highest counts appear at the top of the table.
<details closed> <summary>Answer</summary>
<code>source="cisco_firewall_logs_aug2025.csv" | search action=DENY OR action=BLOCK | stats count by src_ip, dst_ip, dst_port, protocol | sort - count</code>
</details>

10. Save your search to create a report titled "Top Denied Connections Report".
