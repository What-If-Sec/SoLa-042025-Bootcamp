## Activity Objective

In this activity, students will learn how to create alerts in Splunk that automatically notify analysts when specific conditions are met. By the end of the activity, students will be able to:
1. Write SPL searches that identify security-relevant events.
2. Define alert conditions such as thresholds, patterns, or time-based triggers.
3. Configure alert actions, including email notifications or dashboard updates.
4. Save and manage alerts to support real-time monitoring in a SOC environment.



Activity Instructions

Complete the following instructions:
1. Open Search and Reporting and set a time range that includes your Snort data.
2. Type the base search to limit results to the Snort IDS CSV and run it to verify events load.
<details closed> <summary>Answer</summary>
<code>source="snort_ids_logs_aug2025.csv"</code>
</details>

3. Pipe the `search` command to filter for the `BRUTE_FORCE` value within the `rule_category` field to keep only events labeled BRUTE_FORCE, then run and verify.
<details closed> <summary>Answer</summary>
<code> source="snort_ids_logs_aug2025.csv" | search rule_category="BRUTE_FORCE"</code>
</details>

4. Pipe the `transaction` command to group events that share a `src_ip` and occur within a `maxspan` of sixty seconds, then confirm the eventcount field appears.
<details closed> <summary>Answer</summary>
<code> source="snort_ids_logs_aug2025.csv" | search rule_category="BRUTE_FORCE" | transaction src_ip maxspan=60s</code>
</details>

5. Pipe a `where` command to filter for transcations where 3 or more brute force attempts were made.
<details closed> <summary>Answer</summary>
<code>source="snort_ids_logs_aug2025.csv" | search rule_category="BRUTE_FORCE" | transaction src_ip maxspan=60s | where eventcount >= 3</code>
</details>

6. Pipe a `table` command to show just the `source`, `src_ip`, `dst_ip`, and `eventcount` fields needed for reporting and run to see the final output.
<details closed> <summary>Answer</summary>
<code>source="snort_ids_logs_aug2025.csv" | search rule_category="BRUTE_FORCE" | transaction src_ip maxspan=60s | where eventcount >= 3 | table source src_ip dst_ip eventcount</code>
</details>

7. Click "Save As" then Alert.
8. Name the alert "Potential Brute Force Attempt Alert" and add a short description.
9. Set the permissions to "private" as well as alert type to "Scheduled" and to "run on a cron schedule".
10. Set the time range to "Other - All Time" and the cron expression to `*/1 * * * *` to run every minute.
11. Set it to expire 90 days from now.
12. Set the trigger condition to Number of Results greater than zero.Optional add throttle to suppress repeat notifications per `src_ip` for thirty minutes.
13. Set the trigger action to email and include tokens like `$result.src_ip$` and `$result.eventcount$`, within the message to explain the purpose of the alert, and then save. 

