Firewall
In this project, I used ufw to configure firewalls on my issued web servers.

Tasks 📃
0. Block all incoming traffic but
0-block_all_incoming_traffic_but: Bash script that installs a ufw firewall to block all incoming traffic except for ports 22, 443, and 80 on a web server.

Script:

bash
Copy code
#!/bin/bash
# Install ufw if not installed
sudo apt-get update
sudo apt-get install -y ufw

# Set default policies
sudo ufw default deny incoming
sudo ufw default allow outgoing

# Allow specific ports
sudo ufw allow 22/tcp
sudo ufw allow 443/tcp
sudo ufw allow 80/tcp

# Enable ufw
sudo ufw enable

# Check the status
sudo ufw status verbose
1. Port forwarding
100-port_forwarding: ufw configuration file that configures a firewall to redirect port 8080/TCP to port 80/TCP.

Configuration:

bash
Copy code
# /etc/ufw/before.rules

# rules.before
#
# Rules that should be run before ufw command line added rules. Custom rules
# should be added to one of these chains:
#   ufw-before-input
#   ufw-before-output
#   ufw-before-forward
#
# START OPENSSH RULES
# OpenSSH by default on port 22/tcp
-A ufw-before-input -p tcp --dport 22 -j ACCEPT
-A ufw-before-output -p tcp --dport 22 -j ACCEPT
# END OPENSSH RULES

# nat Table rules
*nat
:PREROUTING ACCEPT [0:0]
-A PREROUTING -p tcp --dport 8080 -j REDIRECT --to-port 80
COMMIT

# Don't delete these required lines, otherwise there will be errors
*filter
...
Repository
GitHub repository: alx-system_engineering-devops
Directory: 0x13-firewall
Files:
0-block_all_incoming_traffic_but
sh: 1: q: not found
