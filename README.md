# firewall-on-windows-and-linux
Windows Firewall Configuration Steps
Step 1: Open Firewall Settings
Open Control Panel → System and Security → Windows Defender Firewall

Click “Advanced Settings” to open the Windows Firewall with Advanced Security console.

Step 2: List Current Rules
In left pane → Click Inbound Rules
View existing rules in the middle pane (filter by ports or programs)

Step 3: Block Inbound Traffic on Port 23 (Telnet)
In Inbound Rules → Click New Rule
Select Port
Choose TCP, then Specific local ports: 23
Select Block the connection
Apply to all profiles (Domain, Private, Public)
Name it: Block_Telnet

Step 4: Test the Rule
Use telnet 127.0.0.1 23 (if Telnet Client is enabled)
You should get connection failed/refused

Step 5: Remove the Rule
Go back to Inbound Rules
Right-click Block_Telnet → Delete

B. Linux (Ubuntu) with UFW - Uncomplicated Firewall
Step 1: Open Terminal and Enable UFW
sudo ufw enable

 Step 2: List Current Rules
 sudo ufw status numbered

Step 3: Block Port 23 (Telnet)
sudo ufw deny 23

 Step 4: Test the Rule
 telnet localhost 23

Step 5: Allow SSH (if not already allowed)
sudo ufw allow 22

Step 6: Remove the Test Block Rule
sudo ufw delete deny 23


