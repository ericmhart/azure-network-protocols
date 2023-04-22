<p align="center">
<img src="https://i.imgur.com/Ua7udoS.png" alt="Traffic Examination"/>
</p>

<h1>Network Security Groups (NSGs) and Inspecting Traffic Between Azure Virtual Machines</h1>
In this tutorial, we observe various network traffic to and from Azure Virtual Machines with Wireshark as well as experiment with Network Security Groups. <br />


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Various Command-Line Tools
- Various Network Protocols (SSH, DNS, RDP, ICMP)
- Wireshark (Protocol Analyzer)

<h2>Operating Systems Used </h2>

- Windows 10 (21H2)
- Ubuntu Server 20.04

<h2>High-Level Steps</h2>

- Download Wireshark to VM1 from Google
- Observe Network Traffic
- Filter Network Traffic (ICMP, SSH, DHCP)
- Change Firewall on VM2 to block traffic and view through Wireshark

<h2>Actions and Observations</h2>

<p>
<img src="https://i.imgur.com/A8HKrGf.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Go to google.com and download wireshark Windows Installer 
</p>
<br />

<p>
<img src="https://i.imgur.com/89o6ttM.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

</p>
<br />

<p>
<img src="https://i.imgur.com/WiACfwt.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Pull up wireshark app. Select Ethernet and click blue shark fin in upper left corner to start capturing packets.
  
</p>
<br />

<p>
<img src="https://i.imgur.com/wj2hvT8.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

</p>
<br />

<p>
<img src="https://i.imgur.com/jP2IN8u.png" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

</p>
<br />


<p>
<img src="https://i.imgur.com/lpFdm4v.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Test connectivity between VM1 and VM2 by using ping command in powershell. Filter wireshark by ICMP to see the traffic. After this is done intiate an infinite ping using ping -t in powershell. Change the firewall on VM2 to block the ICMP traffic. To do this go into Azure Portal> Network Security Groups> Inbound Security Rules> Add. Set Protocol to ICMP and Action to block. Go back into VM1 and view the traffic on wireshark. After done set it back to allow. 
</p>
<br />


<p>
<img src="https://i.imgur.com/vz2NwDg.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Next filter Wireshark traffic by SSH(Secure Shell). Connect to VM2 through Powershell in VM1(note when typing password for VM2 it will not show in powershell) and view traffic on Wireshark. Exit SSH connection. 
</p>
<br />

<p>
<img src="https://i.imgur.com/N1Dxz2Q.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Next filter traffic for DNS(Domain Name Server). Use (nslookup www.google.com) and observe the traffic. For fun you can also filter Wireshark by RDP and watch wireshark spam traffic as there is an active remote session happening.
</p>
<br />
