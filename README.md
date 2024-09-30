# Seting up a Basic Home Lab Running Active Directory (Oracle VirtualBox) | Add Users with PowerShell

This guide walks us through setting up a basic home lab running Active Directory (AD) using Oracle VirtualBox with a Windows Server VM. We'll learn how to install and configure AD Domain Services, and manage user accounts via PowerShell commands. This environment allows hands-on practice with AD administration tasks alongside some basic Windows networking.




![1_iUD-io2JyZK32fES59KqHw](https://github.com/user-attachments/assets/a6bb02f7-5bad-46ee-a6e8-79764a762966)




We'll start by downloading and installing Oracle VirtualBox, which will be used to run the virtual machines (VMs). Once installed, we'll download both a Windows 10 ISO and a Server 2019 ISO to set up two separate VMs, each running its respective operating system.




![VBox](https://github.com/user-attachments/assets/08349134-8ef4-4555-8a42-1396033edfca)



Once everything is downloaded and installed, we'll create our first virtual machine, which will serve as the Domain Controller and host Active Directory. This VM will have two network adapters: one for internet access and the other for a private network, allowing client connections. After creating the VM, we'll install Server 2019 and configure IP addressing for the internal network. The external network will automatically receive IPs from the home router, so no manual configuration is needed for it.


![2019Server](https://github.com/user-attachments/assets/2714dbc7-a031-4fc9-8e93-389040d7d71a)



Once the IP addressing is configured, we'll name the server and install Active Directory to create our domain. Next, we'll set up routing to ensure that clients on the private network can access the internet through the domain controller. We'll also configure DHCP on the domain controller so that when we create our Windows 10 machine, it will automatically receive an IP address.



![ConfigDHCP](https://github.com/user-attachments/assets/1d393dc9-455d-4bfa-adca-0e7f8ab260dd)



Before creating the client virtual machine, we'll run a PowerShell script on the domain controller to automatically generate 1,000 users in Active Directory. Once the users are created, we'll set up another virtual machine, install Windows 10, and connect it to the private VirtualBox network. We'll name this machine "Client1," join it to the domain, and log in using one of the domain accounts.



![PowerShellScript](https://github.com/user-attachments/assets/dddfa3c5-7b6e-40f0-948b-29e9ae04f8cb)



We can then test for internet connection using the Command Prompt once we are logged in CLIENT1 Virtual Machine.


![CMD](https://github.com/user-attachments/assets/f3acbc19-8c0a-4d9e-b376-1185d5f44759)

