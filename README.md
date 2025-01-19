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

![Capture](https://github.com/user-attachments/assets/6fcf18f4-23c5-467a-9b56-0812dc81aa6d)
I created a resource group named 'Windows' for my Windows 10 Virtual Machine and added a Linux Ubuntu VM, ensuring both VMs were on the same virtual network (VNet) and subnet.

</p>
<p>

</p>
<br />

<p>

![2](https://github.com/user-attachments/assets/91a08904-941c-4a10-a8da-11b82a2f664e)
I installed Wireshark on my Windows 10 VM, filtered ICMP traffic, and used PowerShell to ping the private IP of the Linux VM.

</p>
<p>
<br />

![image](https://github.com/user-attachments/assets/27c0ed10-1fad-47da-9e39-b9be2648480d)
![image](https://github.com/user-attachments/assets/e5346a69-e3eb-42b6-86f8-89be9087c0e1)
![image](https://github.com/user-attachments/assets/fe7314af-34d5-4fe6-8b9f-80e8c28ec990)
I accessed the network group, added an inbound security rule to block ICMP traffic, and then removed the rule

</p>
<br />

![image](https://github.com/user-attachments/assets/d3bdbd24-86d3-4b0f-8887-48142c8f8554)



