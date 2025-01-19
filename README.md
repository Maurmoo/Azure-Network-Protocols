<p align="center">
<img src="https://i.imgur.com/Ua7udoS.png" alt="Traffic Examination"/>
</p>

<h1>Network Security Groups (NSGs) and Inspecting Traffic Between Azure Virtual Machines</h1>
In this tutorial, we observe various network traffic to and from Azure Virtual Machines with Wireshark and experiment with Network Security Groups. <br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Various Command-Line Tools
- Various Network Protocols (SSH, RDH, DNS, HTTP/S, ICMP)
- Wireshark (Protocol Analyzer)

<h2>Operating Systems Used </h2>

- Windows 10 (21H2)
- Ubuntu Server 20.04

<h2>High-Level Steps</h2>

- Create Virtual Machines
- Observe ICMP Traffic
- Configuring a Firewall 
- Observe SSH, DHCP, DNS, and RDP Traffic
<h2>Actions and Observations</h2>


<p>
  
## Step 1: Create Virtual Machines

![Capture](https://github.com/user-attachments/assets/6fcf18f4-23c5-467a-9b56-0812dc81aa6d)
I created a resource group named 'Windows' in Microsoft Azure to organize resources for a Windows 10 Virtual Machine and a Linux Ubuntu Virtual Machine. Both VMs were deployed within the same virtual network (VNet) and subnet, enabling seamless communication.

</p>
<p>

</p>
<br />

<p>

## Step 2: Observe ICMP Traffic

![2](https://github.com/user-attachments/assets/91a08904-941c-4a10-a8da-11b82a2f664e)
I installed Wireshark on the Windows 10 VM and filtered for ICMP traffic. Then, I used PowerShell to ping the private IP address of the Linux VM, allowing me to capture the ICMP traffic in Wireshark for analysis.

</p>
<p>
<br />
  
## Step 3: Configuring a Firewall
  
![image](https://github.com/user-attachments/assets/27c0ed10-1fad-47da-9e39-b9be2648480d)
![image](https://github.com/user-attachments/assets/e5346a69-e3eb-42b6-86f8-89be9087c0e1)
![image](https://github.com/user-attachments/assets/fe7314af-34d5-4fe6-8b9f-80e8c28ec990)
To test firewall functionality, I created an inbound security rule to block ICMP traffic. This prevents pings and helps secure the system against potential vulnerabilities.
</p>
<br />

## Step 4: Observe SSH, DHCP, DNS, and RDP Traffic
## SSH
![image](https://github.com/user-attachments/assets/d3bdbd24-86d3-4b0f-8887-48142c8f8554)
I used Wireshark on the Windows 10 Virtual Machine to filter and observe SSH traffic. Simultaneously, I accessed the Linux Virtual Machine by running a PowerShell command that included its username and private IP address for the SSH connection. For example, the command used in PowerShell was: ssh Labuser@10.1.0.6
## DHCP
![image](https://github.com/user-attachments/assets/6d144f6d-bfbc-4df4-8e5e-1ab97eb4257a)
I filtered DHCP traffic in Wireshark on the Windows 10 Virtual Machine. Then, I opened PowerShell as an administrator and ran the ipconfig /renew command to request a new IP address lease from the DHCP server. This action generated DHCP traffic, which I observed in Wireshark, allowing me to analyze the request and response process.

## DNS
![image](https://github.com/user-attachments/assets/6714cea8-7541-4889-8c20-6ee12e52260a)
From the Windows 10 Virtual Machine, I used PowerShell to run the nslookup command to resolve the IP addresses for google.com and disney.com. As I performed the lookup, I observed the corresponding DNS queries and responses captured in Wireshark.

## RDP
![image](https://github.com/user-attachments/assets/00b11044-fa73-47ac-b6c7-1a07e6c1c1ed)
In Wireshark, I filtered the traffic to display only RDP (Remote Desktop Protocol) traffic by applying the filter tcp.port == 3389. I observed continuous and rapid traffic flow, indicating an ongoing RDP session.

## Conclusion
In this tutorial, we demonstrated how to analyze network traffic and configure Network Security Groups in Azure. By observing and filtering traffic using tools like Wireshark, we gained insights into how different protocols function and how to enhance security configurations.

![Azure](https://img.shields.io/badge/Azure-Cloud-blue)
![Wireshark](https://img.shields.io/badge/Wireshark-Network%20Analyzer-blue)
