# 🏰 Active Directory & Network Services Lab
### [Sergio Garcia | IT Portfolio](https://github.com/garcias3317-source)

<h2>Description</h2>
This project demonstrates the deployment of a fully functional Windows Server 2019 environment. I configured a Domain Controller from scratch, managed networking services (DHCP/NAT), and implemented enterprise security policies via Group Policy Objects (GPO). This lab simulates a real-world corporate environment for user management and technical support.
<br />

---

<h2>Project Walk-through:</h2>

### 1. Domain Controller Installation
I began by promoting a Windows Server 2019 instance to a Domain Controller. This involved installing **Active Directory Domain Services (AD DS)** and configuring the forest for **Company.org**.

<p align="center">
<img src="https://i.imgur.com/lgpXMaB.png" height="80%" width="80%" alt="Installing AD DS Roles"/>
</p>

### 2. Networking: Static IP & NAT Configuration
To ensure the server could act as a gateway, I assigned a static IP (**192.168.0.1**) and configured **Network Address Translation (NAT)** to allow domain-joined workstations to access the internet through the server.

<p align="center">
<img src="https://imgur.com/fm8Ql7G.png" height="80%" width="80%" alt="Network Configuration"/>
</p>

### 3. DHCP Scope Setup
I implemented a **DHCP Server** role to automate IP addressing for the network. I defined a scope for the `192.168.0.100 - 192.168.0.200` range to prevent IP conflicts.

<p align="center">
<img src="https://i.imgur.com/j7u3HM3.png" height="80%" width="80%" alt="DHCP Configuration"/>
</p>

### 4. User Management & Domain Join
I designed a custom **Organizational Unit (OU)** structure. I created user accounts and added them to the **Domain Admins** group. I then successfully joined a Windows 10 workstation to the domain using these credentials.

<p align="center">
<img src="https://i.imgur.com/0Up0Rz2.png" height="80%" width="80%" alt="User Properties"/>
<br />
<img src="https://imgur.com/KTbwNa6.png" height="80%" width="80%" alt="Domain Join Verification"/>
</p>

### 5. Security Policies (Group Policy Objects)
To secure the environment, I configured two specific GPOs:
1. **Interactive Logon Banner:** A legal warning displayed to all users upon sign-in.
2. **Password Policy:** Enforced a minimum length of 7 characters to improve security posture.

<p align="center">
<img src="https://i.imgur.com/NXx7Qcc.png" height="80%" width="80%" alt="Banner Configuration"/>
<br />
<img src="https://i.imgur.com/qsDyv02.png" height="80%" width="80%" alt="Password Policy Settings"/>
</p>

### 6. Verification & Final Results
After running `gpupdate /force`, I verified the policies were applied. The final result shows the custom "WARNING" banner appearing on the client workstation before login.

<p align="center">
<img src="https://i.imgur.com/6PDrUfc.png" height="80%" width="80%" alt="Applying Policies"/>
<br />
<img src="https://i.imgur.com/V6Q58Yb.png" height="80%" width="80%" alt="Final Policy Result"/>
</p>

---
