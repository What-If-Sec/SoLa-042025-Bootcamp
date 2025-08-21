## Activity Objective 

Students will learn how to use MD5 and SHA family hash algorithms to verify the integrity of files before execution. They will understand the importance of this practice in ensuring the authenticity and security of files, especially in environments where malicious tampering or corruption could occur. By completing this activity, students will:
1. Be introduced to the concept of hashing, focusing on MD5 and SHA-256 algorithms.
2. Generate and compare hashes using command-line tools (e.g., md5sum, sha256sum) or equivalent tools on different operating systems.
3. Learn the importance of verifying hashes before accessing or executing files will be emphasized, particularly when downloading software from the internet or transferring files over unsecured networks.

## Activity Instructions
Follow the instructions below:
1. Download the files located [here](https://drive.google.com/drive/folders/1wW-3PXvCCBt6CxaqX6fhNK4IbaftNeaB) to your Ubuntu VM.

2. Prior to executing each file verify the MD5 and SHA-256 hashes provided.
<details closed> <summary>Answer</summary> <p>Generate and compare the hashes of each file to the provided values before running them:</p>
  <code>md5sum -c file0_md5hash  file1_md5hash  file2_md5hash  file3_md5hash </code> <br>
  <code>sha256sum -c file0_sha256hash  file1_sha256hash  file2_sha256hash  file3_sha256hash </code></details>

3. Execute the files with hashes that match, and decode each string using base64.
<details closed> <summary>Answer</summary> <p>Make the files executable and run them:</p> <code>chmod u+x file1 && ./file1 chmod u+x file2 && ./file2 chmod u+x file3 && ./file3 </code> <br><br> <p>Each file should output a base64-encoded string. Decode them using:</p> <code>./file1 > encoded_string_file1 && base64 -d encoded_string_file1; ./file2 > encoded_string_file2 && base64 -d encoded_string_file2; ./file3 > encoded_string_file3 && base64 -d encoded_string_file3
</code> </details>

4. Combine the values from each key to form the final key value and go to the website provided.
<details closed> <summary>Answer</summary> <p>Display the final combined result.</p> <code>./file1 > encoded_string_file1 && base64 -d encoded_string_file1 >> decoded_message; ./file2 > encoded_string_file2 && base64 -d encoded_string_file2 >> decoded_message; ./file3 > encoded_string_file3 && base64 -d encoded_string_file3 >> decoded_message && cat decoded_message </code> </details>

5. Create a hash of the file containing the decoded message using MD5 and SHA256.
<details closed> <summary>Answer</summary> <p>Create both an <strong>MD5</strong> and <strong>SHA-256</strong> hash of the decoded_message file:</p> <code>md5sum decoded_message > decoded_message_md5hash && sha256sum decoded_message > decoded_message_sha256hash </code> </details>

6. Submit the decoded_message file and hashes.

-----

> Note: If you executed file0 and experienced the deletion of your home directory, this was intentional — and part of the lesson.
> 
> Let this be a powerful reminder:
> - Even a small oversight, like skipping a hash check, can have serious consequences.
> - Software may appear harmless, but if it's untrusted and unverified, it can destroy data, install malware, or compromise your system.
> - In a real environment, this kind of mistake could cost a company millions, result in data breaches, or lead to disciplinary action.
>
>   Always verify the integrity of files using all provided hashes. Never execute anything that fails verification, even if it "mostly" looks fine.
