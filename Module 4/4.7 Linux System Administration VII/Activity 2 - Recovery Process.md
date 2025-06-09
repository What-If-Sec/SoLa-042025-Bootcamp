## Activity Objectives

Students will demonstrate their understanding of disaster recovery by practicing data recovery using full and incremental backups on their Ubuntu Virtual Machines. This activity will highlight the importance of backup restoration in ensuring data availability and business continuity after a disaster. 

By the end of the activity, students will be able to:
1. Explain the differences between full and incremental backups in the context of disaster recovery.
2. Restore data from a combination of full and incremental backups using the tar command.
3. Identify common challenges in the recovery process and troubleshoot issues to ensure successful restoration.
4. Verify the integrity of recovered data using SHA-256 hash values to ensure accuracy and completeness.
5. Evaluate the effectiveness of a backup and recovery strategy in meeting recovery time objectives (RTO) and recovery point objectives (RPO).

## Activity Scenario

Your VM has been breached by a user named hak0r!!! Hak0r is demanding $1,000,000,000 in bitcoin for you to get your data back. You have identified the user account on your system, which was being used to set up the attack.

Little do they know, you have been implementing an incremental backup process and can recover your files. In this activity you will follow the recovery process below for incremental backups, which begins with the 1st full backup being restored, followed by each subsequent incremental backup in the chain.

## Activity Instructions

 For this activity, students will execute the activity script and then use their full and incremental backups to recover their Downloads directory.

1. Download the script provided [here](https://drive.google.com/file/d/1mwB-5GNSSS7EhJAB0fsWmNtFrH8DGpDw/view?usp=sharing) and set the execute permission for your user using the ```chmod``` command.
<details closed> 
   <summary>Answer Key</summary>
   <code>sudo chmod u+x /pathToFile/4.7.2-ActivitySetupScript.sh</code>
</details>
   
2. Use the ```bash``` command to execute the activity setup script.
<details closed> 
   <summary>Answer Key</summary>
   <code>sudo bash /pathToFile/4.7.2-ActivitySetupScript.sh</code>
</details>

3. Go to your downloads directory and verify that your files are no longer there.
<details closed> 
   <summary>Answer Key</summary>
   <code>ls ~/Downloads</code>
</details>

4. Use the ```usermod```, ```userdel```, and ```groupdel``` commands to disable and then remove the user "hak0r" as well as the user's group from your VM following the proper user de-provisioning process. 
<details closed> 
   <summary>Answer Key</summary>
   <code>sudo usermod -L hak0r && sudo usermod -G "" hak0r && sudo userdel -r hak0r && sudo groupdel hak0r</code>
</details>
   
5. Determine the integrity of your full and incremental back ups, as well as determine which backup was affected by the malware based on verifying the file hashes.
<details closed> 
   <summary>Answer Key</summary>
   <code>sha256sum -c ~/Backups/downloads.tar.xz.sha256; sha256sum -c ~/Backups/YYYY-MM-DD-downloads-01.tar.xz.sha256; sha256sum -c ~/Backups/YYYY-MM-DD-downloads-02.tar.xz.sha256</code>
</details>

6. Once you've identified which (if any) of the backups were impacted, restore your system following proper backup procedures. Start by restoring the full backup to ensure that the system is reverted to the state it was in at the time the full backup was created.
<details closed> 
   <summary>Answer Key</summary>
   <code>sudo tar -xvJf ~/Backups/YYYY-MM-DD-downloads.tar.xz -C ~/Downloads</code>
</details>
  
7. After restoring the full backup, apply the incremental backups in the correct order, starting with the first incremental backup, followed by the next.
<details closed> 
   <summary>Answer Key</summary>  
<code>sudo tar -xvJf ~/Backups/YYYY-MM-DD-downloads-01.tar.xz -C ~/Downloads && sudo tar -xvJf ~/Backups/YYYY-MM-DD-downloads-02.tar.xz -C ~/Downloads
</code></details>
 
8. Verify that all of your data has been recovered.
<details closed> 
   <summary>Answer Key</summary>
   <code>ls ~/Downloads</code>
</details>

