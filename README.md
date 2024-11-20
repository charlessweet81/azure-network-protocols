<p align="center">
<img src="https://i.imgur.com/Ua7udoS.png" alt="Traffic Examination"/>
</p>

<h1>ICMP Traffic Monitoring and Analysis</h1>
Observing ICMP traffic helps troubleshoot intermittent connectivity issues. By deploying monitoring tools to analyze ICMP packets we can identify where the breakdown occurs when users report slow or lost connections to services. <br/><br/>

In this tutorial, we will look at various network traffic to and from Azure Virtual Machines with Wireshark. <br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop (Microsoft Remote Desktop)
- Various Command-Line Tools (via Powershell)
- Various Network Protocols (SSH, RDH, DNS, HTTP/S, ICMP)
- Wireshark (Protocol Analyzer)

<h2>Operating Systems Used </h2>

- Windows 10 (21H2)
- Ubuntu Server 20.04

<h2>High-Level Steps</h2>

- Step 1: Log into remote desktop 
- Step 2: Open Wireshark and start packet capture
- Step 3: Within Wireshark, filter for ICMP traffic only
- Step 4: Ping the second terminal from Powershell

<h2>Actions and Observations</h2>

<p>
<img src="https://i.imgur.com/7E93uXW.png" height="80%" width="80%" alt="Log into Remote Desktop"/>
</p>
<p>
Step 1: We're going to log into a remote desktop using the virtual machine's public IP address and created username and password. 
</p>
<br />

<p>
<img src="https://i.imgur.com/dlnWxf3.png" height="80%" width="80%" alt="Filter for ICMP"/>
</p>
<p>
Step 2: Open Wireshark and type 'ICMP' into the filter - this lets us test the connectivity between the Windows VM and a second VM (Linux) device without seeing irrelevant traffic. 
</p>
<br />

<p>
<img src="https://i.imgur.com/5IRiRtj.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Step 3: Retrieve the private IP address of VM. 

</p>

<p>
<img src="https://i.imgur.com/nVyKkxZ.png" height="80%" width="80%" alt="Ping the Linux virtual machine using Powershell"/>
</p>
<p>
Step 4: Ping the second VM from Powershell. Notice that there are 4 reply lines there.  

</p>

<p>
<img src="https://i.imgur.com/P3vSmtq.png" height="80%" width="80%" alt="Ping the Linux virtual machine using Powershell"/>
</p>
<p>
You can see that the Linux VM is successfully receiving and sending traffic by Wireshark showing 4 request and 4 reply lines, respectively. 

</p>

<br />
