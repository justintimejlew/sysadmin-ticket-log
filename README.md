# sysadmin-ticket-log

[![Home Button](https://img.shields.io/badge/➤_Go_Back_Home-darkred?style=for-the-badge&logo=)](https://github.com/justintimejlew#home-button)

<details>
<summary> 1. Deploy a new CentOS 9 Virtual Machine on Vsphere </summary>

    TASK: The Infrastructure Team is requesting a new CentOS 9 Virtual Machine (VM) to launch a new product for the software development team. Please use the naming convention in the requirements section below. Ensure VM details are added to the asset tiger inventory tool.

**STEPS TAKEN:**
    
1. Accessed [vSphere]() and selected the correct sandbox correlated to the Host IP address:
        
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T1_1.png?raw=true"/>
        
2. Clicked on “Actions” and selected “New Virtual Machine”
        
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T1_2.png?raw=true"/>
        
3. Selected “Create a new virtual machine”
        
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T1_3.jpg?raw=true"/>
        
4. Created VM according to the “Requirements;” however, CentOS 9 was not listed as an option, so I chose CentOS 8 for the guest OS
        
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T1_4.png?raw=true"/>
        
5. Then later I was able to select the ISO image as listed in the “Requirements”
        
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T1_5.png?raw=true"/>
        
6. Once it was created, I powered it on and clicked “Launch Web Console”
        
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T1_6.png?raw=true"/>
        
7. I booted the OS normally and went through the steps to perform a minimal installation:
        
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T1_7.jpg?raw=true"/>
        
8. I was able to successfully login to the VM
        
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T1_8.png?raw=true"/>
        
9. I ran `ip a` to obtain the IP address and MAC address (link)
        
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T1_9.png?raw=true"/>
        
10. I ran `dmidecode -t system | grep -i serial` to obtain the serial number
        
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T1_10.png?raw=true"/>
</details>

<details>
<summary> 2. Create your own resource pool on VSphere </summary>
    
    TASK: To efficiently manage and allocate organization’s resources, we need to create resource clusters for our deployed and upcoming VMs.
    
**STEPS TAKEN:**
    
1. Followed the instruction listed on the Wiki on “[How to create a resource pool in Vsphere]()”
2. Opened vSphere Client and highlighted Data Center location
3. Right-click on the Data Center and choose ‘New Resource Pool’
4. Named my resource pool as JLEWIS-CLUSTER and clicked ‘OK’
5. Next, I selected the VM I created for Ticket 1 and right-clicked on it to select ‘Migrate’
6. Selected the first option: ‘Change compute resource only’, and clicked ‘Next’
7. Selected ‘Resource Pools’ tab, chose my resource pool, and clicked ‘Next’
8. Selected YT-Intran-VLAN and clicked ‘Next’ until I was able to click ‘Finish’
        
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T2_1.png?raw=true"/>
</details>