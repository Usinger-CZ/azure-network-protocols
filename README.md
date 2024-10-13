<p align="center">
<img src="https://i.imgur.com/Ua7udoS.png" alt="Traffic Examination"/>
</p>

<h1>Network Security Groups (NSGs) and Inspecting Traffic Between Azure Virtual Machines</h1>
In this tutorial, we observe various network traffic to and from Azure Virtual Machines with Wireshark as well as experiment with Network Security Groups. <br />





<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Computer)
- Remote Desktop
- Various Command-Line Tools
- Various Network Protocols (SSH, RDH, HTTP/S, ICMP)
- Wireshark (Protocol Analyzer)

<h2>Operating Systems Used </h2>

- Windows 10 (21H2)
- Ubuntu Server 20.04

<h2>High-Level Steps</h2>

- Configuring a Firewall [Network Security Group]
- SSH (Secure Shell) into a Linux Server
- Observe DHCP Traffic

<h2>Actions and Observations</h2>

![Screenshot (4)](https://github.com/user-attachments/assets/89cc3874-a3c9-479a-9a21-13620209e44d) ![Screenshot (14)](https://github.com/user-attachments/assets/8cf1e5ef-f1f8-4bc7-bf77-19545144eac9) ![Screenshot (6)](https://github.com/user-attachments/assets/d7a2bd3f-3a62-4158-947b-2ba5a49daad0)



<p>
In Wireshark, I applied a filter to capture only ICMP traffic. Subsequently, I initiated a continuous ping between my Windows 10 virtual machine and a Linux server. I then configured a new inbound security rule within the Linux network security group to block all incoming traffic. As a result, I observed the ping requests timing out, indicating that the Windows VM could no longer communicate with the Linux server due to the newly enforced inbound rule.  
</p>
<br />

![Screenshot (10)](https://github.com/user-attachments/assets/dd2d50fc-c7de-4e9a-8be7-4741d8bf5820)

<p>
Utilized Wireshark to apply an SSH filter for monitoring encrypted traffic. Using PowerShell on the Windows 10 VM, I established a secure SSH connection to the Linux server via Remote Desktop, enabling detailed traffic analysis.  
</p>
<br />

![Screenshot (15)](https://github.com/user-attachments/assets/06006280-cbfc-4493-a2bd-20d829e3ed23)

<p>
Utilized Wireshark to capture and filter network traffic, isolating DHCP-specific packets. Subsequently, I developed a script using Notepad to automate the process of releasing the system's current DHCP lease and initiating a request for a new one. Upon executing the script, the network connection was successfully released and seamlessly renewed with a fresh DHCP lease  
</p>
<br />
