Introduction
This outlines the process of setting up a basic firewall on an Ubuntu virtual machine (VM) running on Oracle VirtualBox and configuring firewall rules to allow or block specific traffic. In this case, the focus was on blocking access to Google search to demonstrate firewall configuration techniques.
Firewall Setup with UFW
Ubuntu's default firewall management tool, Uncomplicated Firewall (UFW), is used to simplify the setup of firewall rules. After confirming that UFW is installed, it was enabled with basic rules to manage incoming and outgoing network traffic.
Commands used
Sudo ufw status (checks if UFW is installed)
Sudo ufw enable (To run UFW)
Sudo ufw allow (To allow specific ports or IP addresses)
Sudo ufw deny (To deny specific ports or IP addresses)
Sudo ufw reset (To reset UFW to its default settings)
Sudo ufw disable (To temporarily disable the firewall)
Blocking Access to Google Search
Blocking via /etc/hosts File
•	The /etc/hosts file was edited to block Google's search domains by redirecting www.google.com, google.com, and regional Google domains to the localhost IP (127.0.0.1). This effectively prevents DNS resolution of these domains, making them inaccessible.
•	Commands used:
sudo nano /etc/hosts

•	Entries added:
127.0.0.1 www.google.com 
127.0.0.1 google.com 
127.0.0.1 www.google.co.uk 
127.0.0.1 google.co.uk
- This approach is effective for domain-based blocking, as it intercepts DNS queries before they reach the network.
- After configuration, attempts to access www.google.com from a browser on the VM resulted in connection errors, confirming successful blocking of Google search.
