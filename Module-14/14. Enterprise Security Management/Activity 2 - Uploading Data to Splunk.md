## Activity Objectives

Students will practice the role of a Junior SOC Analyst by uploading and indexing various log datasets (e.g., webserver, authentication, firewall, IDS) into Splunk. The goal is to learn how to use Splunk for log ingestion, searching, and analysis in order to identify security-relevant events such as brute force attempts, suspicious IP traffic, and potential exploitation attempts.

By the end of the activity, students should be able to successfully import structured log files into Splunk.



## Activity Instructions

Log into your Splunk environment and complete the following instructions:
1. Select add data from either the welcome page or settings, and select upload.
2. Select and upload the following Apache authentication log. Afterwards, click next.
3. Confirm that the source type is set to "csv", and click next.Change the host field value to "Apache", and click next.
4. Review and ensure that the apache log file is being uploaded with a source type set to csv and the host set to Apache. Afterwards, submit.
5. Select "Add More Data", and upload the Nginx authentication log data to Splunk.
6. Set the source type to "csv"" and the host to "Nginx". Afterwards, review and submit.
7. Select "Add More Data", and upload the Fortinet honeypot log data to Splunk. Set the source type to "csv"" and the host to "Fortinet-HP". Afterwards, review and submit.
8. Select "Add More Data", and upload the Cisco firewall log. Set the source type to "csv"" and the host to "Cisco-Firewall". Afterwards, review and submit.
9. Select "Add More Data", and upload the Snort IDS log data to Splunk.
10. Set the source type to "csv"" and the host to "Snort". Afterwards, review and submit

