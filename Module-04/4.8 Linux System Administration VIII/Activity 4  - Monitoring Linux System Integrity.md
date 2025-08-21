## Activity Objectives

Students will demonstrate their understanding of Linux auditing by creating and implementing audit rules to monitor changes to the ```/etc/shadow``` file and various file manipulation system calls. By the end of this activity, students will be able to:
1. Understand the purpose and importance of Linux audit rules.
2. Create audit rules to monitor access and modifications to  a file or directory.
3. Create audit rules to monitor for system calls.
4. Verify the effectiveness of the audit rules by generating and reviewing audit logs.
5. Understand how to interpret audit logs and take appropriate actions based on the audit results.

## Activity Instructions

1. Verify that ```auditd``` is installed, if not install using the apt package manager.
<details closed>
<summary>Answer Key</summary>
<ol>
    <li>Check if <code>auditd</code> is installed:
        <pre><code>dpkg -l | grep auditd</code></pre>
        <p>If <code>auditd</code> is installed, you'll see a package listed with details. If there is no output, <code>auditd</code> is not installed.</p>
    </li>
    <li>Install <code>auditd</code> if not installed:
        <pre><code>sudo apt update</code></pre>
        <pre><code>sudo apt install auditd</code></pre>
    </li>
    <li>Verify installation:
        <pre><code>sudo systemctl status auditd</code></pre>
        <p>This should show the status of the <code>auditd</code> service, indicating whether it is running or not.</p>
    </li>
</ol>
</details>

2. Verify the auditd service is running using the systemctl command, if not start the daemon.
<details closed>
<summary>Answer Key</summary>
<ol>
    <li>Check the status of <code>auditd</code>:
        <pre><code>sudo systemctl status auditd</code></pre>
        <p>If the service is running, you should see output indicating that the <code>auditd</code> service is active. If the service is not running, you will see that the status is inactive or stopped.</p>
    </li>
    <li>If <code>auditd</code> is not running, start the service:
        <pre><code>sudo systemctl start auditd</code></pre>
    </li>
    <li>Verify the service is running:
        <pre><code>sudo systemctl status auditd</code></pre>
        <p>Ensure that the <code>auditd</code> service is active and running.</p>
    </li>
</ol>
</details>

3. Configure the /etc/audit/auditd.conf file with the following parameters using sudo: (1) log file location is /var/log/audit/audit.log, (2) the number of retained logs is 20, and (3) the maximum log file size is 50.
<details closed>
<summary>Answer Key</summary>
<ol>
    <li>Edit the <code>/etc/audit/auditd.conf</code> file:
        <pre><code>sudo nano /etc/audit/auditd.conf</code></pre>
    </li>
    <li>Update the configuration with the following parameters:
        <ul>
            <li>Set the log file location to <code>/var/log/audit/audit.log</code>:</li>
            <pre><code>log_file = /var/log/audit/audit.log</code></pre>
            <li>Set the number of retained logs to 20:</li>
            <pre><code>num_logs = 20</code></pre>
            <li>Set the maximum log file size to 50 MB:</li>
            <pre><code>max_log_file = 50</code></pre>
        </ul>
        <p>Save the file and exit the editor (in <code>nano</code>, press <code>CTRL + X</code>, then <code>Y</code> to confirm changes, and <code>Enter</code> to save).</p>
    </li>
</ol>
</details>

4. Edit the /etc/audit/rules.d/audit.rules file and create a persistent rule that will monitor for the /etc/shadow file being written to or for any attribute changes. Name the audit rule shadow_changes.
<details closed>
<summary>Answer Key</summary>
<ol>
    <li>Open the <code>/etc/audit/rules.d/audit.rules</code> file using a text editor:
        <pre><code>sudo nano /etc/audit/rules.d/audit.rules</code></pre>
    </li>
    <li>Add the following rule to monitor <code>/etc/shadow</code> for writes and attribute changes:
        <pre><code>-w /etc/shadow -p wa -k shadow_changes</code></pre>
        <p><strong>Explanation:</strong></p>
        <ul>
            <li><code>-w /etc/shadow</code>: Watches the <code>/etc/shadow</code> file for changes.</li>
            <li><code>-p wa</code>: Watches for write (<code>w</code>) and attribute change (<code>a</code>) events.</li>
            <li><code>-k shadow_changes</code>: Names the rule <code>shadow_changes</code> for easy identification in logs.</li>
        </ul>
    </li>
    <li>Save and exit the file:
        <ul>
            <li>In <code>nano</code>, press <code>CTRL + X</code>, then <code>Y</code> to confirm changes, and press <code>Enter</code> to save the file.</li>
        </ul>
    </li>
    <li>Restart the <code>auditd</code> service to apply the new rule:
        <pre><code>sudo systemctl restart auditd</code></pre>
    </li>
    <li>Verify that the rule has been applied:
        <pre><code>sudo auditctl -l</code></pre>
        <p>This command will display the active audit rules, and you should see the rule for <code>/etc/shadow</code> with the key <code>shadow_changes</code>.</p>
    </li>
</ol>
</details>

5. Edit the /etc/audit/rules.d/audit.rules file and create a persistent rule that will monitor for the kill system call. Name the audit rule monitor_kill. (Hint: you will need to monitor for the execve system call and use the /bin/kill path)
<details closed>
<summary>Answer Key</summary>
<ol>
    <li>Open the <code>/etc/audit/rules.d/audit.rules</code> file using a text editor:
        <pre><code>sudo nano /etc/audit/rules.d/audit.rules</code></pre>
    </li>
    <li>Add the following rule to monitor the <code>kill</code> system call:
        <pre><code>-a always,exit -F arch=b64 -S execve -F path=/bin/kill -k monitor_kill</code></pre>
        <p><strong>Explanation of the rule:</strong></p>
        <ul>
            <li><code>-a always,exit</code>: Audits the execution of the system call, both when it enters and exits.</li>
            <li><code>-F arch=b64</code>: Specifies the architecture (64-bit).</li>
            <li><code>-S execve</code>: Monitors the <code>execve</code> system call.</li>
            <li><code>-F path=/bin/kill</code>: Filters the <code>execve</code> system call to monitor only the <code>/bin/kill</code> path.</li>
            <li><code>-k monitor_kill</code>: Assigns the key <code>monitor_kill</code> to this rule for easy identification in logs.</li>
        </ul>
    </li>
    <li>Save and exit the file:
        <ul>
            <li>In <code>nano</code>, press <code>CTRL + X</code>, then <code>Y</code> to confirm changes, and press <code>Enter</code> to save the file.</li>
        </ul>
    </li>
    <li>Restart the <code>auditd</code> service to apply the new rule:
        <pre><code>sudo systemctl restart auditd</code></pre>
    </li>
    <li>Verify that the rule has been applied:
        <pre><code>sudo auditctl -l</code></pre>
        <p>This command will display the active audit rules, and you should see the rule for <code>/bin/kill</code> with the key <code>monitor_kill</code>.</p>
    </li>
</ol>
</details>

6. Create a temporary audit rule using auditctl to monitor for the /etc/passwd file being read, written to, or for any attribute changes. Name the audit rule passwd_changes.
<details closed>
<summary>Answer Key</summary>
<ol>
    <li>Use the <code>auditctl</code> command to create the rule:
        <pre><code>sudo auditctl -w /etc/passwd -p rwa -k passwd_changes</code></pre>
        <p><strong>Explanation of the rule:</strong></p>
        <ul>
            <li><code>-w /etc/passwd</code>: Watches the <code>/etc/passwd</code> file for changes.</li>
            <li><code>-p rwa</code>: Specifies the permissions to watch for:
                <ul>
                    <li><code>r</code>: Read access</li>
                    <li><code>w</code>: Write access</li>
                    <li><code>a</code>: Attribute changes</li>
                </ul>
            </li>
            <li><code>-k passwd_changes</code>: Names the rule <code>passwd_changes</code> for easy identification in the logs.</li>
        </ul>
    </li>
    <li>Verify that the rule is applied by running:
        <pre><code>sudo auditctl -l</code></pre>
        <p>This will display the active audit rules, and you should see the rule for <code>/etc/passwd</code> with the key <code>passwd_changes</code>.</p>
    </li>
</ol>
</details>

7. Restart auditd using systemctl.
<details closed>
<summary>Answer Key</summary>
<pre><code>sudo systemctl restart auditd</code></pre>
</details>

8. Verify that the new audit rules are active. Is the passwd_changes rule there? Explain why not.
<details closed>
<summary>Answer Key</summary>
<pre><code>sudo auditctl -l</code></pre>
The rule is not present because temporary rules are lost after system reboot as well as when the auditd service is restarted resulting in the rule no longer being active.
</details>

9. Recreate and make the previous audit rule to monitor the /etc/passwd file by editing the /etc/audit/rules.d/audit.rules file to make the rule persistent, and restart auditd using systemctl.
<details closed>
<summary>Answer Key</summary>
<ol>
    <li>Edit the <code>/etc/audit/rules.d/audit.rules</code> file:
        <pre><code>sudo nano /etc/audit/rules.d/audit.rules</code></pre>
    </li>
    <li>Add the following line to monitor the <code>/etc/passwd</code> file:
        <pre><code>-w /etc/passwd -p rwa -k passwd_changes</code></pre>
        <p><strong>Explanation of the rule:</strong></p>
        <ul>
            <li><code>-w /etc/passwd</code>: Watches the <code>/etc/passwd</code> file for changes.</li>
            <li><code>-p rwa</code>: Specifies the permissions to watch for:
                <ul>
                    <li><code>r</code>: Read access</li>
                    <li><code>w</code>: Write access</li>
                    <li><code>a</code>: Attribute changes</li>
                </ul>
            </li>
            <li><code>-k passwd_changes</code>: Names the rule <code>passwd_changes</code> for easy identification in the logs.</li>
        </ul>
    </li>
    <li>Save and exit the editor. In <code>nano</code>, press <code>CTRL + X</code>, then <code>Y</code> to confirm changes, and press <code>Enter</code> to save.</li>
    <li>Restart the <code>auditd</code> service to apply the new rule:
        <pre><code>sudo systemctl restart auditd</code></pre>
    </li>
    <li>Verify that the rule is applied by running:
        <pre><code>sudo auditctl -l</code></pre>
        You should see the rule for <code>/etc/passwd</code> with the key <code>passwd_changes</code> in the output.
    </li>
</ol>
</details>

10. Verify that all rules are active and persistent.
<details closed>
<summary>Answer Key</summary>
<pre><code>sudo auditctl -l</code></pre>
</details>

11. Open Firefox, and use ```ps``` command to get a snapshot of currently running processes. Once done, exit the Firefox application using the kill command.
<details closed>
<summary>Answer Key</summary>
<ol>
    <li>Open Firefox:
        <pre><code>firefox &</code></pre>
      This will open Firefox in the background, allowing you to continue using the terminal.
    </li>
    <li>Get a snapshot of currently running processes:
        <pre><code>ps aux</code></pre>
    </li>
    <li>Filter the processes for Firefox:
        <pre><code>ps aux | grep firefox</code></pre>
    </li>
    <li>Find the Firefox process ID (PID) from the output of the previous command.</li>
    <li>Exit Firefox using the <code>kill</code> command:
        <pre><code>kill &lt;PID&gt;</code></pre>
        Replace <code>&lt;PID&gt;</code> with the actual process ID of Firefox.
    </li>
    <li>Verify that Firefox has been closed by running the following command again:
        <pre><code>ps aux | grep firefox</code></pre>
        If no output (except for the <code>grep</code> command) appears, it means Firefox has been successfully closed.
    </li>
</ol>
</details>

12. Use ausearch to query  monitor_kill audit events.
<details closed>
<summary>Answer Key</summary>
<pre><code>sudo ausearch -k monitor_kill</code></pre>
</details>

13. Use aureport to search for failed user authentications. (Hint: Use aureport man page https://linux.die.net/man/8/aureport)
<details closed>
<summary>Answer Key</summary>
<pre><code>sudo aureport -au --failed</code></pre>
</details>

14. Use aureport to search for terminal use.
<details closed>
<summary>Answer Key</summary>
<pre><code>sudo aureport -t</code></pre>
</details>

15. Perform sudo su three time using the wrong password, then generate the same report using aureport. (Notice that there will be 3 entries with no indicating failed login attempts.)
<details closed>
<summary>Answer Key</summary>
<ol>
    <li>Perform <code>sudo su</code> three times with the wrong password:
        <pre><code>sudo su</code></pre>
        (Enter the wrong password each time.)
    </li>
    <li>Generate a report of failed authentication attempts:
        <pre><code>sudo aureport -au --failed</code></pre>
    </li>
</ol>
</details>

16. Create a new user named criminal, then perform a search using aureport for account modifications. 
<details closed>
<summary>Answer Key</summary>
<ol>
    <li>Create a new user named <code>criminal</code>:
        <pre><code>sudo useradd criminal</code></pre>
        (Optional) Set a password for the user:
        <pre><code>sudo passwd criminal</code></pre>
    </li>
    <li>Perform a search for account modifications using <code>aureport</code>:
        <pre><code>sudo aureport -am</code></pre>
    </li>
</ol>
</details>
