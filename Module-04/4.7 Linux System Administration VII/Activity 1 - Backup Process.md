## Activity Objectives

Students will demonstrate an understanding of effective backup strategies by configuring and creating incremental backups on their Ubuntu Virtual Machines. This activity will focus on ensuring data security, availability, and reliability in alignment with best practices for business continuity and disaster recovery. 

By the end of the activity, students will be able to:
1. Explain the role of incremental backups in minimizing storage usage and recovery times.
2. Understand the concept of incremental backups and the advantages they offer over full backups.
3. Use the tar command to create initial and subsequent incremental backups.
4. Generate and store SHA-256 hash values for each backup to verify the integrity of back up data.

## Activity Instructions

For this activity you will be creating an incremental backup of your Downloads directory., by completing the following tasks:
1. Create a directory named "Backups" in your home directory.
<details closed> 
   <summary>Answer Key</summary>
   <code>mkdir ~/Backups </code>
</details>
  
2. Create an initial full backup of your Downloads directory using the tar command and compress the backup with xz. Name the snapshot file "downlooads.snar" and store both the backup and compressed file in the "Backups" directory you previously created.  
<details closed> 
   <summary>Answer Key</summary>
   <code>tar -cvJf ~/Backups/downloads.tar.xz --listed-incremental=~/Backups/downloads.snar ~/Downloads</code>
</details>

3. Verify the contents of your downloads backup file using tar.
<details closed> 
   <summary>Answer Key</summary>
   <code>tar -tvJf ~/Backups/downloads.tar.xz</code>
</details>

4. Create a hash of your backup file using the SHA256 algorithm and store the hash in the Backups directory.
<details closed> 
   <summary>Answer Key</summary>
   <code>sha256sum ~/Backups/downloads.tar.xz > ~/Backups/downloads.tar.xz.sha256</code>
</details>
 
5. Create a file (name it whatever you want) in your Downloads directory using the touch command.
<details closed> 
   <summary>Answer Key</summary>
   <code>touch ~/Downloads/myNewFile</code>
</details>
  
6. Create your 1st incremental backup of your Downloads directory using the tar command and compress your backup using xz. Remember to add "-01"  to the end of the file name for your incremental backup. The backup name should follow this structure: "YYYY-MM-DD-filename-01".
<details closed> 
   <summary>Answer Key</summary>
   <code>tar -cvJf ~/Backups/YYYY-MM-DD-downloads-01.tar.xz --listed-incremental=~/Backups/downloads.snar ~/Downloads
</code>
</details>

7. Create a hash of your incremental backup file using the SHA256 algorithm and store the hash in the Backups directory.
<details closed> 
   <summary>Answer Key</summary>
   <code>sha256sum ~/Backups/YYYY-MM-DD-downloads-01.tar.xz > ~/Backups/YYYY-MM-DD-downloads-01.tar.xz.sha256</code>
</details>

8. Create a file (name it whatever you want) in your Downloads directory using the touch command.
<details closed> 
   <summary>Answer Key</summary>
   <code>touch ~/Downloads/myNewFile2</code>
</details>
   
9. Create your 2nd incremental backup of your Downloads directory using the tar command and compress your backup using xz. Remember to add "-02" to the end of the file name for your incremental backup. The backup name should follow this structure: "YYYY-MM-DD-filename-02".
<details closed> 
   <summary>Answer Key</summary>
   <code>tar -cvJf ~/Backups/YYYY-MM-DD-downloads-02.tar.xz --listed-incremental=~/Backups/downloads.snar ~/Downloads</code>
</details>

10. Create a hash of your incremental backup file using the SHA256 algorithm and store the hash in the Backups directory.
<details closed> 
   <summary>Answer Key</summary>
   <code>sha256sum ~/Backups/YYYY-MM-DD-downloads-02.tar.xz > ~/Backups/YYYY-MM-DD-downloads-02.tar.xz.sha256</code>
</details>






