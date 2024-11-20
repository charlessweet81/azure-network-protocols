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
- Step 4: Filter by network traffic type
  - 4a: SSH
  - 4b: DCHP
  - 4c: DNS
  - 4d: RDP  
- Step 5: Type commands into the linux connection and observe traffic


<h2>Actions and Observations</h2>

<p>
<h3>Step 1: Log into Windows VM </h3>
</p>
<p>
<img src="https://i.imgur.com/jVz0kZx.png" height="80%" width="80%" alt=""/>
</p>

<p>
<h3>Step 2: Start a packet capture in Wireshark </h3>
</p>
<p>
<img src="https://i.imgur.com/F186Xeg.png" height="80%" width="80%" alt=""/>
</p>

<p>
<h3>Step 3: Log into Ubuntu Virtual Machine via its private IP address (Powershell) </h3>
</p>
<p>
<img src="https://i.imgur.com/z7qhdp4.png" height="80%" width="80%" alt=""/>
</p>

<p>
<h3>Step 4: Observe network traffic </h3>

<h4>SSH Network Traffic</h4>
<p>
<img src="https://i.imgur.com/zYyRbDz.png" height="80%" width="80%" alt=""/>
</p>

1. Type 'ssh' into Wireshark's filter.
2. Type commands (username, pwd, etc) into the linux connection and observe SSH traffic in WireShark

For example: 
- 'id' generates the username we logged in with
- 'hostname' generates the Linux VM we're currently logged into
- 'uname -a' generates information about the operating system of the connected VM

3. Type 'exit' to close the SSH connection. 
</p>
<br />

<h4>DHCP Network Traffic</h4>
<p>
<img src="https://i.imgur.com/zYyRbDz.png" height="80%" width="80%" alt=""/>
</p>

1. Filter for DHCP traffic only
2. Attempt to issue your VM a new IP address from the command line by running PowerShell as admin and running: ipconfig /renew

If you don’t see Discover, Offer Request, Acknowledge in Wireshark:

- Try filtering with ‘udp.port == 67 || udp.port == 68’. If that doesn’t work:
  - Create a notepad file with ‘ipconfig /release’ and ‘ipconfig /renew’
  - Name the file ‘dhcp.bat’ (change ‘save as type’ to ‘all files’) and save it in ‘c:\programdata’
  - In Powershell, input ‘cd c:\programdata’ to access the c: drive where you stored the .bat file; you can also use ‘cat /.dhcp.bat’ to verify the contents of the file 
  - Input ‘ls’ for list to confirm you can access the .bat file 
  - Input ‘.\dchp.bat’ to release the IP address and renew the connection
 
You should now see all of the capture information. 

</p>

<p>
<img src="https://i.imgur.com/TSw7X4s.png" height="80%" width="80%" alt=""/>
</p> 

<h4>DNS Network Traffic</h4>
<p>
1. Filter for DNS traffic only using either ‘udp’ or ‘udp.port == 53’ in the Wireshark search bar<br> 
2. From your Windows 10 VM within a command line, use nslookup to see what human-readable URL addresses resolve to
</p>
<p>
<img src="https://i.imgur.com/R8Kzv2i.png" height="80%" width="80%" alt=""/>
</p>

<h4>RDP Network Traffic</h4>
<p>
1. Filter for RDP traffic only either using 'rdp' or 'tcp.port == 3389' in Wireshark search bar<br> 

</p>
<p>
<img src="https://i.imgur.com/YhSz1UQ.png" height="80%" width="80%" alt=""/>
</p>


