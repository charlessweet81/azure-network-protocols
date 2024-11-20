<p align="center">
<img src="https://i.imgur.com/Ua7udoS.png" alt="Traffic Examination"/>
</p>

<h1>Observing Various Traffic Types Using Wireshark & Powershell</h1>

In this tutorial, we will look at SSH network traffic to and from Azure Virtual Machines with Wireshark. <br />

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

- Step 1: Log into Windows VM
- Step 2: Start a packet capture in Wireshark
- Step 3: Log into Ubuntu Virtual Machine via its private IP address
- Step 4: Filter for traffic
  - 4a: SSH
  - 4b: DCHP
  - 4c: DNS
  - 4d: RDP  
- Step 5: Type commands into the linux connection and observe traffic


<h2>Actions and Observations</h2>

<p>
<img src="https://i.imgur.com/jVz0kZx.png" height="80%" width="80%" alt="Log into Windows VM "/>
</p>
<p>
Step 1: Log into Windows VM <br/> <br/>
</p>

<p>
<img src="https://i.imgur.com/F186Xeg.png" height="80%" width="80%" alt="Start a packet capture in Wireshark"/>
</p>
<p>
Step 2: Start a packet capture in Wireshark <br/> <br/>
</p>

<p>
<img src="https://i.imgur.com/z7qhdp4.png" height="80%" width="80%" alt="Log into Ubuntu Virtual Machine via its private IP address"/>
</p>
<p>
Step 3: Log into Ubuntu Virtual Machine via its private IP address (Powershell)  <br/>
</p>

<p>
<img src="https://i.imgur.com/g2KLbf8.png" height="80%" width="80%" alt="Filter for SSH traffic"/>
</p>
<p>
Step 4a: Filter for SSH traffic <br/> <br/>
</p>

<p>
<img src="https://i.imgur.com/g2KLbf8.png" height="80%" width="80%" alt="Filter for SSH traffic"/>
</p>
<p>
Step 4b: Filter for DCHP traffic <br/> <br/>
</p>

<p>
<img src="https://i.imgur.com/g2KLbf8.png" height="80%" width="80%" alt="Filter for SSH traffic"/>
</p>
<p>
Step 4c: Filter for DNS traffic <br/> <br/>
</p>

<p>
<img src="https://i.imgur.com/g2KLbf8.png" height="80%" width="80%" alt="Filter for SSH traffic"/>
</p>
<p>
Step 4a: Filter for RDP traffic <br/> <br/>
</p>

<p>
<img src="https://i.imgur.com/zYyRbDz.png" height="80%" width="80%" alt="Type commands into the linux connection and observe SSH traffic in WireShark"/>
</p>
<p>
Step 5: Type commands (username, pwd, etc) into the linux connection and observe SSH traffic in WireShark  <br/> <br/>

From here, you can use various commands to retrieve information from the connected device. <br/> <br/>

For example: 
- 'id' generates the username we logged in with
- 'hostname' generates the Linux VM we're currently logged into
- 'uname -a' generates information about the operating system of the connected VM
</p>


<br />
