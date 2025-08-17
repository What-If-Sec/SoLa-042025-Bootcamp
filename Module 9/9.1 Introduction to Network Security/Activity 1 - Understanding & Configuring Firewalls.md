## Activity Objective

Students will learn how to implement and configure a firewall using firewalld through understanding key concepts such as zones, services, and rules. By the end of the activity, students will be able to manage firewall zones, create custom rules to allow or block traffic, and securely configure services such as SSH and HTTP, ensuring they can apply basic firewall management for network security.

## Activity Instructions

On your Ubuntu Server VM  follow the instructions below to configure firewall rules using firewalld.
1. Ensure that firewalld is running by checking the service's status. If firewalld is not installed, running, or configured to start at boot. Install firewalld to your VM, and then enable and start the service using systemctl.
<details closed> <summary>Answer</summary> <code> sudo systemctl status firewalld </code> <p>If firewalld is not installed:</p> <code> sudo apt update && sudo apt install firewalld -y </code> <p>Then enable and start the service:</p> <code> sudo systemctl enable firewalld && sudo systemctl start firewalld </code> </details>

2. View all available zones in firewalld.
<details closed> <summary>Answer</summary> <code> sudo firewall-cmd --get-zones </code> 
<br><br><p>By default the drop, dmz, external, home, internal, public, nm-shared, trusted, and work zones will exist.</p>
</details>

3. View all active zones.
<details closed> <summary>Answer</summary> <code> sudo firewall-cmd --get-active-zones </code> </details>

4. Set "home" as your default zone, and verify that "home" was set as the active zone.
<details closed> <summary>Answer</summary> <p>Execute: <code> sudo firewall-cmd --set-default-zone=home </code> to set the default zone to home, and excute: <code>sudo firewall-cmd --get-active-zones</code> to verify that "home" is set as the default zone.</p></details>

5. Set your VM's internal network interface to the "home" zone. (Hint: Use `ifconfig` or `ip a` to identify your network interface and IPv4 address.)
<details closed> <summary>Answer</summary> <p>First, identify your active network interface and IP address:</p> <code> ip a </code> <p>Then assign the interface with an inet IPv4 address (e.g., eth0 or ens33) to the <code>home</code> zone permanently:</p> <code>sudo firewall-cmd --zone=home --change-interface=eth0 --permanent </code> </details>

6. View and take note of the services allowed in the public, home, and DMZ.
<details closed> <summary>Answer</summary> <code>sudo firewall-cmd --zone=public --list-all && sudo firewall-cmd --zone=home --list-all && sudo firewall-cmd --zone=dmz --list-all </code> </details>

7. Allow FTP and telnet services to run in the "home" zone and make each firewall rule permanent.
<details closed> <summary>Answer</summary> <code>sudo firewall-cmd --zone=home --add-service=ftp --permanent && sudo firewall-cmd --zone=home --add-service=telnet --permanent </code> </details>

8. Reload your firewall, and verify that each rule was added to the "home" zone.
<details closed> <summary>Answer</summary> <code>sudo firewall-cmd --reload  &&  sudo firewall-cmd --zone=home --list-all </code> </details>

9. Set "public" as your default zone.
<details closed> <summary>Answer</summary> <code> sudo firewall-cmd --set-default-zone=public </code> </details>

10 . Set your VM's bridged network interface to the "public" zone. (Hint: Use `ifconfig` or `ip a` to identify your network interface and IPv4 address.)
<details closed> <summary>Answer</summary> <p>First, identify your active network interface and IP address:</p> <code> ip a </code> <p>Then assign the interface with an inet IPv4 address (e.g., eth0 or ens33) to the <code>home</code> zone permanently:</p> <code>sudo firewall-cmd --zone=public --change-interface=eth1 --permanent </code> </details>

11. Remove the "ssh" service from the public zone and set this as a permanent firewall rule.
<details closed> <summary>Answer</summary> <code> sudo firewall-cmd --zone=public --remove-service=ssh --permanent </code> </details>

12. Add both the http and https services to the public zone, and set these as permenant fiewall rules. 
<details closed> <summary>Answer</summary> <code>sudo firewall-cmd --zone=public --add-service=http --permanent && sudo firewall-cmd --zone=public --add-service=https --permanent </code> </details>

13. Reload firewalld to apply changes, and verify that the appropriate services were added/removed.
<details closed> <summary>Answer</summary> <code> sudo firewall-cmd --reload && sudo firewall-cmd --zone=public --list-all</code> </details>

14. Bonus: Create a runtime firewall rule that will block ICMP echo-requests  and echo-replys in the "home" zone. (Do not reload, reloading will erase the runtime configuration)
<details closed> <summary>Answer</summary> <code>sudo firewall-cmd --zone=home --add-icmp-block=echo-request && sudo firewall-cmd --zone=home --add-icmp-block=echo-reply</code></details>

### Firewalld Command Examples
```bash
# start firewalld
sudo systemctl start firewalld

# Enable service to start at boot
sudo systemctl enable firewalld

# Check status of firewalld
sudo systemctl status firewalld

# Reload firewalld and apply changes
sudo firewall-cmd --reload

# View available zones
sudo firewall-cmd --get-zones

# View active zones
sudo firewall-cmd --get-active-zones

# View services available to firewalld
sudo firewall-cmd --get-services

# View information about a specific zone such as the allowed services, ports, etc.
sudo firewall-cmd --zone=[zone_name] --list-all

# View information about all zones such as the allowed services, ports, etc.
sudo firewall-cmd --list-all-zones

# Assign a zone as the default zone
sudo firewall-cmd --set-detault-zone=[zone_name]

## --permanent is used to add a firewalld rule to the permanent configuration.
## Not including --permanent will add the firewalld rule to the runtime configuration.

# Permanently assign a network interface to a zone
sudo firewall-cmd --zone=[zone_name] --change-interface=[interface_with_IPV4_address] --permanent 

# Permanently create firewall rule to allow a service permanently from a zone
sudo firewall-cmd --zone=[zone_name] --add-service=[service_name] --permanent

# Permanently  remove/ Disable a service from a zone
sudo firewall-cmd --zone=[zone_name] --remove-service=[service_name] --permanent

# Permanently add a port to a zone
sudo firewall-cmd --zone=[zone_name] --add-port=[port_num/protocol]

# Permanently remove a port from a zone
sudo firewall-cmd --zone=[zone_name] --remove-port=[port_num/protocol]
```
