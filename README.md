# Virtual Private Network (VPN)
<p align="center">
<img src="https://i.imgur.com/MntON5Q.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<h1>VPN - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of using a VPN. 
<br />

<h2>Environments and Technologies Used</h2>

- A VPN (Proton VPN)
- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>💻 Operating Systems Used</h2>

- **Windows 10 Pro (22H2)**

<h2>Steps</h2>

- Locate Public IP Address
- Setting Up VM Using Azure
- Locating IP Through VM (Japan)
- Connecting to VPN Through VM
- Locating IP Through VPN (United States)
<br />
<h2>VPN Setup and Usage (Proton VPN)</h2>

Locate your own personal IP address by going to "**www.whatismyipaddress.com**", which will be able to show you your local IP address.

For Privacy Reasons, I won't show my actual Public IP Address, so I'll find an example from Google. 

<p>
<img src="https://github.com/user-attachments/assets/c207e7ce-f9f9-4866-9547-8201062ceee6" height="80%" width="90%" alt="Disk Sanitization Steps"/>
</p>
<p>
Now we will set up a Windows 10 Pro Virtual Machine on Azure. 
</p>
<br />

<h3>Create a Resource Group and Virtual Machine in Azure</h3>
<p>
  Create a Windows 10 Pro Virtual Machine in another Geographic Region (try a different country),

  We will select the country of Japan.
</p>
<p>
<img src="https://i.imgur.com/C6tXZ2n.png" height="80%" width="90%" alt="Disk Sanitization Steps"/>
</p>
For the Username and Password, you can create your custom information; just remember what it is.
</p>

<p>
<img src="https://i.imgur.com/CBScaHu.png" height="80%" width="90%" alt="Disk Sanitization Steps"/>
</p>
<p>
Then select “Review and Create”, once it passes validation, select “Create” at the bottom. 
</p>
<p>
After creating the Virtual Machine, locate the Public IP Address of the Virtual Machine, which for this one is “74.226.224.150”. 
</p>
<br />

<h3>Log into the VM and look up the VM's Public IP Address</h3>
<p>
  Now that we have set up the Virtual Machine, we'll connect it using the application RDP (Remote Desktop Connection) and input the Public IP Address for the VM and then input the credentials we set when creating the VM. 
  
  Once logged in, we will open the web browser and again look up "www.whatismyipaddress.com", this time for the VM's Public IP Address.
</p>
<p>
<img src="https://github.com/user-attachments/assets/997490d9-c128-4e98-97d5-dcec3c15e0a2" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Browse to https://whatismyipaddress.com/
  
Look up the Public IP address for this VM through "www.whatismyipaddress.com", and sure enough, we see that this VM is showing the location for Japan, in Tokyo specifically.
</p>
<p>
<img src="https://github.com/user-attachments/assets/d5ab0cd9-0c1e-4a12-9462-1b83a7e3ecd0" height="80%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<p>
  Pretty Cool. This is the VM with a Non-VPN connection. 
</p>
<br />

<h3>🟦 Sign up for Proton VPN and test the VPN connection</h3>
<p>

On your actual computer, sign up for the free version of Proton VPN.

**Proton VPN; Sign-up**: https://account.protonvpn.com/signup?plan=free&language=en)
  
Using the local computer, go to protonvpn.com and create a free account,

(If you use the VM, then Japan will display on your browser, so use your Local Computer desktop). 
</p>
<p>
<img src="https://i.imgur.com/0YpkN5x.png" height="80%" width="90%" alt="Disk Sanitization Steps"/>
  <img src="https://i.imgur.com/BTnfzhN.png" height="80%" width="90%" alt="Disk Sanitization Steps"/>
</p>
<p>
  Once you are logged into your account, copy the URL from the Proton VPN website and then paste the URL to the VM web browser. 
</p>
<br />

<h3>🔵 Download Proton VPN Client within the VM</h3>
<p>
  Back within your VM, download the Windows version of the Proton VPN client. Make sure it's the free version.

  Once the application Proton VPN is installed, we will log in using the credentials we used when setting up a free account on Proton VPN. Then connect to the VPN through the installed app.  
</p>
<p>
<img src="https://i.imgur.com/oOrq4BV.png" height="70%" width="70%" alt="Disk Sanitization Steps"/>
  <img src="https://i.imgur.com/7kRR7IU.png" height="90%" width="100%" alt="Disk Sanitization Steps"/>
  <img src="https://i.imgur.com/fjPKUzx.png" height="70%" width="70%" alt="Disk Sanitization Steps"/>
  <img src="https://i.imgur.com/JIx8JtO.png" height="90%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<br />

<h3>Test VPN ✅️</h3>
<p>

After we log into the VPN, 

On the left-hand side of the VPN, you can select a country where you want your VPN to be and choose a VPN server in yet another country. 

However, it seems the free version **won't** allow you to choose where you want the VPN Server to be located, so instead we must use the option of "**Quick Connect**".

**Quick Connect** gave me the **United States**
</p>
<p>
<img src="https://i.imgur.com/o07TMrs.png" height="90%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<br />

<p>
Next, let's look at the IP Address again using the VM browser now that we have connected the VPN to the United States. 
  
Browse to the website, www.whatismyipaddress.com
</p>
<p>
<img src="https://i.imgur.com/rD3fD85.png" height="90%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<p>

  It now shows my VM’s IP Address being entirely different; it shows my ISP is from somewhere else and coming from the **United States, Florida region** specifically. 
  
  That’s quite cool.
</p>
<br />

<h3>Conclusion</h3>
<p>
Looking at this VPN Lab, we see that we have utilized 3 different Public IP addresses just from your local computer to connect to the internet.

- Home IP Example (USA): 74.68.56.187

- Virtual Machine IP (**Japan**): 74.226.224.150

- Virtual Machine IP VPN (**USA; Florida**): 149.22.80.123
</p>
<br />
<p>
If you no longer need the VM, make sure to delete it from the Azure account for unnecessary charges.
</p>
