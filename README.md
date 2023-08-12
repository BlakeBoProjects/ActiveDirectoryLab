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
- <b>Windows Server 2022</b>

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

Added routing and NAT capabilities to the domain controller. 
<br/>
<img src="https://i.imgur.com/DVKC2lI.png" height="80%" width="80%" alt="Routing and NAT"/>
<br />
<br />

Added a DHCP Server and set a new scope. Verified internet connectivity from Win10, and verified the DHCP lease on the DC. <br/>
<img src="https://i.imgur.com/lSbk5iN.png" height="80%" width="80%" alt="DHCP"/>
<br />
<br />

Joined the Win10 client to the domain. <br/>
<img src="https://i.imgur.com/tSwS3Ay.png" height="80%" width="80%" alt="Domain Join"/>
<br />
<br />

On the domain controller, created two Organization Units in Active Directory Users and Computers, named "_Admins" and "_Sales" respectively. Created a domain admin account in the former OU named "a-sron". Created two regular users, "lruman" and "dthor", in the latter. Logged into the Win10 client with new accounts to test functionality.  <br/>
<img src="https://i.imgur.com/PgIb9dG.png" height="80%" width="80%" alt="Creating sample user accounts"/>
<br />
<br />

Installed RSAT tools on the Win10 client to enable domain admins to access and modify Active Directory Users and Computers, Group Policy Management Console, Server Manager, and other features directly from the client.  <br/>
<img src="https://i.imgur.com/3C9Sh6G.png" height="80%" width="80%" alt="Installed RSAT Tools"/>
<br />
<br />

Added users to security groups. Created and enforced a Group Policy Object to disable shutdown and task manager; also set lockout policy to automatically lock user accounts after 5 failed login attempts. Verified settings.  <br/>
<img src="https://i.imgur.com/dNdB2gh.png" height="80%" width="80%" alt="Group Policy Objects and Encorcement"/>
<br />
<br />

Created 2 file shares, a department-wide 'Sales' folder and a 'Personal' folder, which would contain a subfolder for each user to serve as that user's home folder. Mapped the folders to the accounts of lruman and dthor on the Win10 client.  <br/>
<img src="https://i.imgur.com/vkwxSkS.png" height="80%" width="80%" alt="Creating and Mapping File Shares"/>
<br />
<br />

Enabled remote access on the Win10 client to allow admins to remote into the machine. Tested functionality by remoting into Win10 from the DC client. <br/>
<img src="https://i.imgur.com/NiHW1VL.png" height="80%" width="80%" alt="Enabled Remote Desktop"/>
<br />
<br />

<b>Enabled and tested the Remote Assistance feature, a multi-step process as follows: </b> <br/><br/>
a) Added the Remote Assistance feature in Server Manager.   <br/>
<img src="https://i.imgur.com/cUooiZp.png" height="80%" width="80%" alt="Added Remote Assistance to Server Manager"/>
<br />
<br />

b) Created new security group in Active Directory Users and Computers called "Allow Remote Assist". Added domain admins to the group. <br/>
<img src="https://i.imgur.com/h7CDBEi.png" height="80%" width="80%" alt="New Security Group"/>
<br />
<br />

c) Created Group Policy Object to allow inbound Remote Assistance. Enabled the Configure Offer Remote Assistance feature and added security group. Linked it to the Workstations OU (which includes the Win10 machine). <br/>
<img src="https://i.imgur.com/IGY5flL.png" height="80%" width="80%" alt="New GPO"/>
<br />
<br />

d) Tested functionality <br/>
<img src="https://i.imgur.com/R2q4KaN.png" height="80%" width="80%" alt="Tested Remote Assistance"/>


<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
