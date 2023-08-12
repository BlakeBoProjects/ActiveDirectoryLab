<h1>Active Directory Home Lab</h1>

 ### [Video Version (YouTube)](https://youtu.be/v58EIkizDns)

<h2>Description</h2>
Created 2 virtual machines, a domain controller running Active Directory and a client running Windows 10. Set up Network Address Translation and a DHCP server to allow the client to access the internet through the domain controller. Created admin and user accounts in Active Directory, put them in security groups, enforced group policy, mapped network drives, and set up Remote Desktop and Remote Assistance. 
<br />

<h2>Programs Used</h2>

- <b>Active Directory</b> 
- <b>RSAT Tools</b>
- <b>Oracle VirtualBox</b>

<h2>Environments Used </h2>

- <b>Windows 10</b>
- <b>Windows Server 2022

<h2>Project Walk-through:</h2>

Created 2 virtual machines, a domain controller (DC) running Windows Server and a client running Windows 10 (Win10). Configured the domain controller to have 2 NICs, one leading out to the internet, and the other for the internal network. The Windows 10 client only had a single network adapter, connecting to the internal network; it connected through the DC to access the internet.
<br/>
<img src="https://i.imgur.com/brVHbll.png" height="80%" width="80%" alt="Created 2 VMs"/>
<br />
<br />

Installed Active Directory on the "DC" machine, promoted it to domain controller, and created a new forest, "domain.com". <br/>
<img src="https://i.imgur.com/BTL35dA.png" height="80%" width="80%" alt="Installed AD"/>
<br />
<br />

Enter the number of passes: <br/>
<img src="https://i.imgur.com/nCIbXbg.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Confirm your selection:  <br/>
<img src="https://i.imgur.com/cdFHBiU.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Wait for process to complete (may take some time):  <br/>
<img src="https://i.imgur.com/JL945Ga.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Sanitization complete:  <br/>
<img src="https://i.imgur.com/K71yaM2.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Observe the wiped disk:  <br/>
<img src="https://i.imgur.com/AeZkvFQ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
