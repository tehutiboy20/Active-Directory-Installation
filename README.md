<p align="center">
<img src="https://i.imgur.com/HPRl0Uw.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>Active Directory Deployed in the Cloud (Microsoft Azure)</h1>
Hello! In this tutorial I will install Active Directory within Azure Virtual Machines. Like the previous, this tutorial will assume you have two Virtual Machines on Azure already created. One VM using Windows server 2022(Domain Controller) which I will be installing Active Directory on and another VM using Windows 10(the Client) that I will join later to the Domain controller.

<b>*Note: Creating the Client VM is not a mandatory step. This is only for teaching purposes to mock a random computer at a school, buisness, etc that is connected to a Domain Controller*</b>

<br/>

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines)
- Remote Desktop
- Active Directory Domain Services

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (21H2)

<h2> Set the Domain Controller's Private ip to Static</h2>
<b> On the Azure Portal click Domain controller > Click Networking > Click  Network Interface</b>
<img src="https://i.imgur.com/9DlbGza.png">
<b>Click ip Configurations</b>
<img src="https://imgur.com/Xs71iST.png">
<b>Switch Toggle to Static > Click Save</b>
<img src="https://i.imgur.com/Lq6jVwr.png">

<h2> Set the Client DNS settings</h2>
<p> Also in the Azure Portal copy the Domain Controllers private IP
<img src="https://i.imgur.com/UPzntYa.png">

<b>Go to the Client's VM Overview > Click Networking > Click on Network Interface > </b>
<img src="https://imgur.com/Lxk4gSf.png">

<b>Click Ip configurations > Toggle to CUSTOM and Type in the domain's private ip address> Click Save</b>
<img src="https://i.imgur.com/ERVrOgU.png">

<b>Restart the Client VM</b>
<img src="https://imgur.com/sgSfpHN.png">

<h2> Log into Domain Controller </h2>
<a>- Username: Labuser</a>

<a>- Password: Password1</a>

<a> These credentials were created in Azure when we created the DC Virtual Machine</a>
<P>Using Remote Desktop Connection log into your Domain Controller<P/>
<b>On the Server Manager click Add Roles and Features > Click Next >> Confirm private ip address of the Domain Controller </b>
<img src="https://imgur.com/cPd0uAR.png">

<b>Check Active Directory Domain Services</b>
<img src="https://i.imgur.com/J82rwBq.png">

<b>Click Add Features > Click Next>> </b>
<img src="https://i.imgur.com/XxfA8EI.png">

<b>Click Install</b>
<img src="https://i.imgur.com/s40t1Hw.png">

<h2> Promote as a DC</h2>
<b>Click Promote this Server to a Domain Controller</b>

<img src="https://i.imgur.com/Qfha5Cd.png">

<b> Click Add a New Forest</b>
<img src="https://i.imgur.com/WZWtV9s.png">

<b>Choose a password</b>
<img src="https://i.imgur.com/zSiTLwu.png">
<img src="https://i.imgur.com/Qx2l8Oo.png">

<b>Click Install</b>
<img src="https://i.imgur.com/QkN1oD2.png">

The DC will lose connection.

<h2> Log back into the DC with new credentials. Example: </h2>

- Username: mydomain.com\Labuser</a>

- Password: Password1</a>
