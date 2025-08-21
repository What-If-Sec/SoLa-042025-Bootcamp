## Activity Objectives

Students will learn to effectively manage and analyze system logs using the journalctl command on a Linux system. By the end of this activity, students will be able to:

1. Understand the role and importance of system logs in maintaining and troubleshooting a Linux system.Utilize the journalctl command to view, filter, and analyze log entries.
2. Apply filtering techniques to isolate specific log entries based on criteria such as time range, log levels, services, and user identifiers (UID).
3. Persistently configure journalctl to manage log retention and storage.Export log data for reporting and further analysis.



## Activity Instructions
Execute the script below prior to starting the activity.
[4.8.2-ActivitySetupScript](https://drive.google.com/file/d/1f_5xg2fu1n-0s4gHTSaHb6IwPWU_jYZB/view)

1. Use ```journalctl``` to show the end of the journal and follow new journal entries.
<details closed>
<summary>Answer Key</summary>
<code>journalctl -f</code>
</details>

2. Use ```journalctl``` to display logs from April 14th, 2025 to today using the ```--since``` and ```--until``` options. What do you observe?
<details closed>
<summary>Answer Key</summary>
<code>journalctl --since "2025-04-14" --until "now"</code>
</details>

3. Use ```journalctl``` to display only error logs using the priority option. What do you observe?
<details closed>
<summary>Answer Key</summary>
<code>journalctl -p err</code>
</details>

4. Use ```journalctl``` to display only messages for the root user. What do you observe?Investigate the actions performed by the user "hak0r" using journalctl. (Hint: use the user's UID). What do you observe?
<details closed>
<summary>Answer Key</summary>
<ol>
    <li>Display only messages for the root user:
        <pre><code>journalctl _UID=0</code></pre>
    </li>
    <li>Find the UID of the user "hak0r":
        <pre><code>id -u hak0r</code></pre>
    </li>
    <li>Display logs for the user "hak0r" using their UID:
        <pre><code>journalctl _UID=&lt;hak0r's UID&gt;</code></pre>
    </li>
</ol>
</details>



