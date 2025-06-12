## Activity Objectives

Students will learn to effectively manage system logs using the ```logrotate``` command on a Linux system. By the end of this activity, students will be able to:

1. Grasp the importance of log rotation for maintaining system performance, optimizing disk space usage, and preserving log data integrity over time.
2. Gain hands-on experience in configuring log rotation rules for various types of logs and define rotation frequencies.
3. Utilize logrotate's features to troubleshoot rotation failures and ensure effective log management.



## Activity Instructions

1. Verify that you have the most up-to-date version of ```logrotate``` installed.
<details closed>
<summary>Answer Key</summary>
<ol>
    <li>Check the installed version:
        <pre><code>logrotate --version</code></pre>
    </li>
    <li>Compare with the latest available version:
        <pre><code>apt list --upgradable | grep logrotate</code></pre>
    </li>
    <li>If an update is available, upgrade it:
        <pre><code>sudo apt update && sudo apt install --only-upgrade logrotate</code></pre>
    </li>
</ol>
</details>

2. Configure the following default parameters for ```logrotate``` by editing /etc/logrotate.conf: (1) A rotation scheme for keeping 8 weeks of backlogs,(2) create new empty log files after rotating old ones, (3) do not rotate empty logs, and (4) compress log files.
<details closed>
<summary>Answer Key</summary>
<ol>
    <li>Open the <code>/etc/logrotate.conf</code> file for editing:
        <pre><code>sudo nano /etc/logrotate.conf</code></pre>
    </li>
    <li>Make the following changes:
        <ul>
            <li>Set the rotation scheme to keep 8 weeks of logs:
                <pre><code>rotate 8</code></pre>
            </li>
            <li>Ensure new empty log files are created after rotating old ones:
                <pre><code>create</code></pre>
            </li>
            <li>Prevent rotating empty logs:
                <pre><code>nocompress</code></pre>
            </li>
            <li>Enable compression for rotated log files:
                <pre><code>compress</code></pre>
            </li>
        </ul>
    </li>
    <li>Save and close the file:
        <ul>
            <li>Press <code>CTRL + X</code>, then press <code>Y</code> to confirm saving, and <code>Enter</code> to close the editor.</li>
        </ul>
    </li>
    <li>Test the configuration:
        <pre><code>sudo logrotate /etc/logrotate.conf --debug</code></pre>
    </li>
</ol>

</details>

3. List the contents of ```logrotate.d``` to see what configuration files are present.
<details closed>
<summary>Answer Key</summary>
 <code>ls /etc/logrotate.d/</code>   
</details>

4. In ```/etc/logrotate.d``` add  configurations (if they do not exist) for the following log files: ```/var/log/auth.log```, ```/var/log/cron.log```, ```/var/log/boot.log``` using the parameters below.
<details closed>
<summary>Answer Key</summary>
<ol>
    <li>Create or edit the configuration files in <code>/etc/logrotate.d/</code>:
        <ul>
            <li>For <code>/var/log/auth.log</code>, create or edit the file <code>/etc/logrotate.d/auth</code> with the following configuration:
                <pre><code>/var/log/auth.log {
    daily
    rotate 180
    compress
    delaycompress
    nocompress
    create 644 root root
}</code></pre>
            </li>
            <li>For <code>/var/log/cron.log</code>, create or edit the file <code>/etc/logrotate.d/cron</code> with the following configuration:
                <pre><code>/var/log/cron.log {
    daily
    rotate 60
    compress
    delaycompress
    nocompress
    create 644 root root
}</code></pre>
            </li>
            <li>For <code>/var/log/boot.log</code>, create or edit the file <code>/etc/logrotate.d/boot</code> with the following configuration:
                <pre><code>/var/log/boot.log {
    daily
    rotate 30
    compress
    delaycompress
    nocompress
    create 644 root root
}</code></pre>
            </li>
        </ul>
    </li>
    <li>Save and close each file:
        <ul>
            <li>After editing each file, press <code>CTRL + X</code>, then press <code>Y</code> to confirm saving, and <code>Enter</code> to close the editor.</li>
        </ul>
    </li>
    <li>Verify Configuration:
        <pre><code>sudo logrotate /etc/logrotate.conf --debug</code></pre>
    </li>
</ol> 
</details>

5. Test that the log rotation works without waiting for the specified scheduled date/ time by forcing logrotate to rotate logs. Afterwards, verify that log rotation was sucessful.
<details closed>
<summary>Answer Key</summary>
 <ol>
    <li>Force logrotate to rotate logs immediately:
        <pre><code>sudo logrotate /etc/logrotate.conf --force</code></pre>
    </li>
    <li>Verify the log rotation was successful:
        <ul>
            <li>Check the log directory (e.g., <code>/var/log</code>) to ensure that the rotated log files are created. Look for files with extensions like <code>.1</code>, <code>.2</code>, etc. (e.g., <code>auth.log.1</code>, <code>cron.log.1</code>, <code>boot.log.1</code>).</li>
            <li>If compression is enabled, check for files like <code>auth.log.1.gz</code>.</li>
            <li>Check the modification time with:
                <pre><code>ls -lh /var/log</code></pre>
            </li>
            <li>Inspect specific log files to verify rotation, for example:
                <pre><code>cat /var/log/auth.log.1</code></pre>
            </li>
        </ul>
    </li>
</ol>

</details>


### Log Rotation Rule Parameters:

For ```/var/log/auth.log```, use the following parameters: 180 days of backlog, rotate daily, Don't rotate empty logs, Compress the file, delay the compression, and the created log should be owned by the root user and group  along with read and write permissions for the user, read permissions for the group, an read permissions for others. Name the configuration file auth.

For ```/var/log/cron.log```, use the following parameters: 60 days of backlog, rotate daily, Don't rotate empty logs, Compress the file, and delay the compression, and the created log should be owned by the root user and group  along with read and write permissions for the user, read permissions for the group, an read permissions for others.  Name the configuration file cron.

For  ```/var/log/boot.log```, use the following parameters: 30 days of backlog, rotate daily, Don't rotate empty logs, Compress the file, delay the compression, and the created log should be create owned by the root user and group  along with read and write permissions for the user, read permissions for the group, an read permissions for others.  Name the configuration file boot.

