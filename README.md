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

## Step 1 Create Virtual Machines
## Step 2 Observe ICMP Traffic
## Step 3 Configuring a Firewall 
## Step 4 Observe SSH, DHCP, DNS, and RDP Traffic



<h2>Actions and Observations</h2>


<p>
  
## Step 1: Create Virtual Machines

![Capture](https://github.com/user-attachments/assets/6fcf18f4-23c5-467a-9b56-0812dc81aa6d)
</p>
<p>
  
- Created a resource group called 'Windows' in Microsoft Azure.
- Deployed a Windows 10 VM and a Linux Ubuntu VM within the same Virtual Network (VNet).
- This setup allows for seamless communication between both VMs.
</p>
<br />

<p>

## Step 2: Observe ICMP Traffic

![2](https://github.com/user-attachments/assets/91a08904-941c-4a10-a8da-11b82a2f664e)
</p>
<p>
  
- Installed Wireshark on the Windows 10 VM.
- Used PowerShell to Ping the private IP of the Ubuntu VM.
- Captured the ICMP traffic in Wireshark to observe basic network connectivity.
</p>
<p>
<br />
  
## Step 3: Configuring a Firewall
  
![image](https://github.com/user-attachments/assets/27c0ed10-1fad-47da-9e39-b9be2648480d)
![image](https://github.com/user-attachments/assets/e5346a69-e3eb-42b6-86f8-89be9087c0e1)
![image](https://github.com/user-attachments/assets/fe7314af-34d5-4fe6-8b9f-80e8c28ec990)

- Configured an Inbound NSG Rule to block ICMP traffic.
- This blocked the ping requests from the Windows VM to the Ubuntu VM, demonstrating the use of Network Security Groups to secure network traffic.
</p>
<br />

## Step 4: Observe SSH, DHCP, DNS, and RDP Traffic
## SSH
![image](https://github.com/user-attachments/assets/d3bdbd24-86d3-4b0f-8887-48142c8f8554)
</p>
<p>
  
- Wireshark was used on the Windows 10 VM to capture SSH traffic while connecting to the Ubuntu VM via PowerShell.
- Ran the command: ssh Labuser@<Ubuntu_IP>.
</p>
<br />

## DHCP
![image](https://github.com/user-attachments/assets/6d144f6d-bfbc-4df4-8e5e-1ab97eb4257a)
</p>
<p>
  
Captured DHCP traffic in Wireshark on the Windows 10 VM.
I ran the ipconfig /renew command to request a new IP lease.
Analyzed the DHCP Discover and Offer packets exchanged between the client and the DHCP server.
</p>
<br />

## DNS
![image](https://github.com/user-attachments/assets/6714cea8-7541-4889-8c20-6ee12e52260a)
</p>
<p>
  
- Used nslookup in PowerShell on the Windows VM to resolve domain names like google.com and disney.com.
- Captured the DNS queries and responses in Wireshark.
</p>
<br />

## RDP
![image](https://github.com/user-attachments/assets/00b11044-fa73-47ac-b6c7-1a07e6c1c1ed)
</p>
<p>
  
- Filtered RDP traffic using the Wireshark filter tcp.port == 3389.
- Observed the continuous traffic flow during an active RDP session.
</p>
<br />

## Conclusion
In this tutorial, I demonstrated how to analyze network traffic and configure Network Security Groups in Azure. By observing and filtering traffic using tools like Wireshark, I gained insights into how different protocols function and how to enhance security configurations.

![Azure](https://img.shields.io/badge/Azure-Cloud-blue)
![Wireshark](https://img.shields.io/badge/Wireshark-Network%20Analyzer-blue)
