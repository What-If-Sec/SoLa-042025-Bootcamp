## Activity Objectives

In this activity, students will learn how to transform search results into meaningful visualizations and organize them within a Splunk dashboard. By the end of the activity, students will be able to:
1. Build SPL searches that summarize key security events.
2. Choose appropriate visualization types (bar chart, pie chart, cluster map, gauge, etc.) to represent different kinds of data.
3. Save visualizations as panels and add them to a dashboard.
4. Create and customize a new dashboard that displays multiple panels for real-time security monitoring.

## Activity Instructions
Complete the following:
1. Open Search and Reporting and set a time range that includes your uploaded data. Run a new search against the Snort IDS log file, and limit the results to the top 20 rule categories by piping  the `top` command with the `rule_category` field.
<details closed> <summary>Answer</summary>
<code>source="snort_ids_logs_aug2025.csv" | top 20 rule_category</code>
</details>

2. Switch to the visualization tab and select the pie chart to show which attack categories are most common.
3. Click save as and choose new dashboard. Afterwards name it "SOC Dashboard", and name the panel "Top IDS Signals".
<details closed> <summary>Answer</summary>
<img width="1455" height="509" alt="splunk_pie_map" src="https://github.com/user-attachments/assets/afae6e7e-68d1-46a4-969b-1d92ed374cb0" />
</details>

4. Execute a search against the Cisco firewall log file and pipe a condition to show only events where the firewall denied or blocked traffic by using the `search` command to query the "action" field.
<details closed> <summary>Answer</summary>
<code>source="cisco_firewall_logs_aug2025.csv" | search (action=DENY OR action=BLOCK) </code>
</details>

5. Pipe the `top` command to list the top 20 most targeted destination ports.
<details closed> <summary>Answer</summary>
<code>source="cisco_firewall_logs_aug2025.csv" | search (action=DENY OR action=BLOCK) | top 20 dst_port </code> 
</details>

6. Switch to the visualization tab and select the bar chart to visualize which ports attackers (or misconfigured systems) are most frequently trying to reach on your network.
<details closed> <summary>Answer</summary>
<img width="2432" height="511" alt="splunk_bar_map" src="https://github.com/user-attachments/assets/d9471b3e-a55b-40f5-a4cb-cb79c9322e87" />
</details>

7. Add this visualization as a new panel on your SOC Dashboard, and provide a title for this new panel.
8. Run a search against the Fortinet honeypot log file, identify the field that holds the attacker's IP address, and pipe the `iplocation` command to use Splunk's built-in IP location lookup tool to add geographic fields.
<details closed> <summary>Answer</summary>
<code>source="fortinet_honeypot_logs_aug2025.csv" | iplocation src_ip</code>
</details>

9. Pipe the `geostats` command and `count` function to use the location data found within the iplocation command to map latitude and longitude data for each event.
<details closed> <summary>Answer</summary>
<code>source="fortinet_honeypot_logs_aug2025.csv" | iplocation src_ip | geostats count</code>
</details>

10. Switch to the visualization tab and select the cluster map to plot the attack source IPs by their geographic location using latitude and longitude values provided by iplocation.
<details closed> <summary>Answer</summary>
  <img width="1684" height="614" alt="splunk_cluster_map" src="https://github.com/user-attachments/assets/975cc46b-bfd5-4f2f-835f-4d1e5c240438" />
</details>

11. Add this visualization as a new panel on your SOC Dashboard, and provide a title for this new panel.
12. Go to the Dashboard tab to view your Splunk Dashboard.
