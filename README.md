# sysadmin-ticket-log

[![Home Button](https://img.shields.io/badge/➤_Go_Back_Home-darkred?style=for-the-badge&logo=)](https://github.com/justintimejlew#home-button)

> Note: Please ignore red font used on tickets 1-48. Some information has been redacted for security purposes.

<details>
<summary> 1. Deploy a new CentOS 9 Virtual Machine on Vsphere </summary>

<code style="white-space: pre-wrap;">TASK: The Infrastructure Team is requesting a new CentOS 9 Virtual Machine (VM) to launch a new product for the software development team. Please use the naming convention in the requirements section below. Ensure VM details are added to the asset tiger inventory tool.</code>

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
    
<code style="white-space: pre-wrap;">TASK: To efficiently manage and allocate organization’s resources, we need to create resource clusters for our deployed and upcoming VMs.</code>
    
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

<details>
<summary> 3. Migrate your deployed VM to your Resource Pool </summary>

<code style="white-space: pre-wrap;">TASK: Now that the Resource Pool has been successfully created, please proceed with moving your server/s into it.</code>

**STEPS TAKEN:**
    
1. I selected the VM I created for Ticket 1 and right-clicked on it to select ‘Migrate’
2. Selected the first option: ‘Change compute resource only’, and clicked ‘Next’
3. Selected ‘Resource Pools’ tab, chose my resource pool, and clicked ‘Next’
4. Selected YT-Intran-VLAN and clicked ‘Next’ until I was able to click ‘Finish’
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T3_1.png?raw=true"/>
</details>

<details>
<summary> 4. Network setup request </summary>

<code style="white-space: pre-wrap;">TASK: Please refer to the IP Address Management (IPAM sheet) to locate the necessary network information. Use this information to establish a static connection for your dev-app server.</code>

**STEPS TAKEN:**
    
1. Used the following command to add a static connection: `nmcli c a con-name dev-app-static autoconnect yes ifname ens192 type ethernet ip4 <ipaddress> gw4 <gatewayaddress> ipv4.dns <dnsaddress>`
2. Added the user procore to wheel group and assigned password.
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T4_1.png?raw=true"/>
</details>

<details>
<summary> 5. Install and Configure FreeIPA client </summary>
    
<code style="white-space: pre-wrap;">TASK: Proceed with the installation and configuration of the IPA client on your new virtual machine (VM).</code>
    
**STEPS TAKEN:**
    
1. Followed the following steps listed here for [configuring an IPA-Client]()
2. Ran the following to install package: `dnf install ipa-client -y`
3. Ran the following install IPA Client:
    * `ipa-client-install --mkhomedir`
    * `procore.dev`
    * `ipa.procore.dev`
4. Entered username and password to enroll IPA Client and received the following confirmation:
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T5_1.png?raw=true"/>
    
5. Used the `id jlewis` command to confirm if IPA was working correctly:
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T5_2.png?raw=true"/>
    
6. Used the `ipa user-show jlewis` command to confirm the following:
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T5_3.png?raw=true"/>
    
7. **Note:** While configuring IPA if you get an error message, try: `ipa-client-install —-mkhomedir --force-join` or use `kinit jlewis` to use Kerberos (security software used w/IPA to ensure connection is genuine) in order to confirm your access and identity.
</details>

<details>
<summary> 6. Add user msoriano to FreeIPA </summary>
    
<code style="white-space: pre-wrap;">TASK: The developer's team recently hired Marie Soriano. Please create a username msoriano for the new user and add them to the group "webmasters." Additionally, set up a temporary password for the user and ensure this information is documented in the ticket.</code>
    
**STEPS TAKEN:**
    
1. Logged into freeIPA, added a new user for Marie Soriano, set password and clicked “Add and Edit”
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T6_1.png?raw=true"/>
    
2. Clicked on the “User Groups” tab in order to add msoriano to the group “Webmasters” by selecting it and moving it from “Available” to “Prospective,” then clicked “Add”
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T6_2.png?raw=true"/>
    
3. Confirmed user was created by running the `id msoriano` command:

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T6_3.png?raw=true"/>
</details>

<details>
<summary> 7. Add user to group using FreeIPA </summary>
    
<code style="white-space: pre-wrap;">TASK: The user you recently added has been assigned to another project supporting the team in revamping the production webpage. Please add this user to the "support" group.</code>
    
**STEPS TAKEN:**
    
1. Clicked on “Active Users” and searched for msoriano
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T7_1.png?raw=true"/>
    
2. Clicked on username, clicked on “User Groups” tab, then clicked “+Add” to move the support group from “Available” to “Prospective” and clicked “Add”
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T7_2.png?raw=true"/>
    
3. Confirmed user was added to the group by running the `id msoriano` command:

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T7_3.png?raw=true"/>
</details>

<details>
<summary> 8. Add the following info to the local DNS file </summary>
    
<code style="white-space: pre-wrap;">TASK: Please add the following information to the local DNS file on the dev-app server.</code>
    
**STEPS TAKEN:**
    
1. Added vim by installing it with: `dnf install vim -y`
2. Used vim to add the following IP address to the `/etc/hosts` directory:
    * 10.1.XX.XX vcenter.sandbox.prod
    * 10.1.XX.XX ipa.procore.dev
    * 10.1.XX.XX dev-nagios.procore.prod1
    * 10.1.XX.XX stage-foreman.procore.prod
    * 10.1.XX.XX stage-bacula.procore.prod1
    * 10.1.XX.XX dev-ansible.procore.prod1 dev-ansible
    * 10.1.XX.XX stage-bastion.procore.prod1 stage-bastion
    * 10.1.XX.XX nfs-dev.procore.prod1
    * 10.1.XX.XX stage-graylog.procore.prod
3. Used the `ping` command to confirm connection to the DNS files
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T8_1.png?raw=true"/>
</details>

<details>
<summary> 9. Create the Following Mount points </summary>
    
<code style="white-space: pre-wrap;">TASK: Please create the following mount points for the upcoming nfs share on the dev-app server.</code>
    
**STEPS TAKEN:**
    
1. Used the following command: `mkdir -pv /nfs/incoming/{home,vhosts,scripts}`.
2. Then used `cd` to enter directory /nfs/incoming to confirm mount points were created:
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T9_1.png?raw=true"/>
</details>

<details>
<summary> 10. Please mount the following NFS shares permanently </summary>
    
<code style="white-space: pre-wrap;">TASK: Please ensure the following NFS shares are mounted permanently on the dev-app server.</code>
    
**STEPS TAKEN:**
    
1. Updated the `/etc/fstab` as shown below:
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T10_1.png?raw=true"/>
    
2. Then ran `mount -a` and `mount | grep nfs` to confirm that they directories were mounted correctly:
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T10_2.png?raw=true"/>
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T10_3.png?raw=true"/>
</details>

<details>
<summary> 11. NFS home directory </summary>

<code style="white-space: pre-wrap;">TASK: Since you will be using SSH in accessing multiple servers, please create a shared directory using your username and 700 permission.</code>

**STEPS TAKEN:**
    
1. Used `cd` to enter `/nfs/incoming/home` directory and then used `mkdir jlewis` to create my shared directory:
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T11_1.png?raw=true"/>
    
2. Then used `chown -R jlewis:jlewis jlewis/` to assign my freeIPA username to be the owner of the directory:
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T11_2.png?raw=true"/>
    
3. Lastly, used `chmod -R 700 jlewis/` to assign the proper permissions on the shared directory
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T11_3.png?raw=true"/>
</details>

<details>
<summary> 12. Please deploy a dev webserver using configuration Template </summary>
    
<code style="white-space: pre-wrap;">TASK: The web development team requires you to deploy a development web server using the NEW-YT-DEV-WEBSERVER-TEMPLATE. Please update the necessary information on the newly deployed server.</code>
    
**STEPS TAKEN:**
    
1. Selected my Cluster folder and clicked on “Actions” to select “New Virtual Machine”
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T12_1.png?raw=true"/>
    
2. For creation type, I selected “Deploy from template”
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T12_2.png?raw=true"/>
    
3. Under “Select a Template,” I clicked on the “Data Center” tab in order to select the NEW-YT-DEV-WEBSERVER-TEMPLATE and clicked “Next”
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T12_3.png?raw=true"/>
    
4. Labeled new ‘Virtual machine name” to dev-performance-jl.procore.prod1 and clicked “Next”
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T12_4.png?raw=true"/>
    
5. When asked to select a compute resource, I selected my cluster folder and clicked “Next”
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T12_5.png?raw=true"/>
    
6. For Storage, DS-01 was selected from the “Batch Configure” tab and then I clicked “Next”
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T12_6.png?raw=true"/>
    
7. For Clone options, I left everything as default and clicked “Next,” then clicked “Finish”
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T12_7.png?raw=true"/>
    
8. Since I did not know the password for the account, I interrupted the GRUB process in order to access rescue mode via the shell
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T12_8.png?raw=true"/>
    
9.  Added password and created autorelabel file to bypass SELinux
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T12_9.png?raw=true"/>
    
10. Logged into VM and enabled SSH, then proceeded to update the hostname as request and shown below:
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T12_10.png?raw=true"/>
    
11. Added static connection using the following `nmcli c a con-name dev-perf-static ifname ens192 type ethernet ip4 <ipaddress> gw4 <gatewayaddress> ipv4.dns <dnsaddress> autoconnect yes`, then I set the connection and made sure that `prod-web` was set to `autoconnect no`
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T12_11.png?raw=true"/>
    
12. Next, I installed freeIPA following the steps from ticket 5 and ran `id jlewis` to confirm that it was properly configured
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T12_12.png?raw=true"/>
    
13. Added the DNS records as outlined in ticket 8, created the mount points as outlined in ticket 9, and permanently mounted the directories as outlined in ticket 10.
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T12_13.png?raw=true"/>
    
14. Ran the following commands to add user procore with the requested information:
    * `useradd -G wheel procore`
    * `echo procoreplus | passwd --stdin procore`
</details>

<details>
<summary> 13. Allow HTTP to use non-standard ports </summary>
    
<code style="white-space: pre-wrap;">TASK: The network and security teams are requesting that your dev-performance web server listens on a non-standard port (8001). Please configure your server to meet this requirement and provide the link for testing.</code>
    
**STEPS TAKEN:**
    
1. Installed `policycoreutils` in order to utilize `semanage`
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T13_1.png?raw=true"/>
    
2. Accessed the man page for `semanage-port` to view the example on how to allow a port via `httpd` services and then ran the following command: `semanage port -a -t http_port_t -p tcp 8001`
3. To confirm it was added correctly, I ran the following: `semanage port -l | grep 8001` which showed it was added:
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T13_2.png?raw=true"/>
    
4. Installed httpd with the following command: `dnf install httpd`
5. Then started the service by running `systemctl enable --now httpd`
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T13_3.png?raw=true"/>
    
6. Next, I had to search the wiki and I found this page that provided steps to follow “[Sfongwe]()” and the first thing I did was edit the `/etc/httpd/conf/httpd.conf` file to listen for port 8001
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T13_4.png?raw=true"/>
    
7. Then, I installed netstat (`dnf install net-tools`) to run the following command to confirm if the server was listening: `netstat -tuln | grep 8001`
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T13_5.png?raw=true"/>
    
8. Add the following services and port to the firewall:
    * `firewall-cmd --permanent --add-service=http`
    * `firewall-cmd --permanent --add-service=https`
    * `firewall-cmd --add-port=8001/tcp`
9. Created the link: http://{insertipaddress}:8001/
</details>

<details>
<summary> 14. Configure a repository </summary>
    
<code style="white-space: pre-wrap;">TASK: The Development team requires you to install a third-party application that can be found on below repository.</code>
    
**STEPS TAKEN:**
    
1. Added repository by using `vim epel.repo` to add the following information in the `/etc/yum.repos.d` directory
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T14_1.png?raw=true"/>
    
2. Ran `dnf clean all` and `dnf repoinfo`, then ran `dnf provides tmux` and `dnf install tmux`
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T14_2.png?raw=true"/>
</details>

<details>
<summary> 15. Create and Copy your SSH key </summary>
    
<code style="white-space: pre-wrap;">TASK: The security and network team is requesting that all users generate SSH keys to access the Ansible server and our GitLab repository.</code>
    
**STEPS TAKEN:**
    
1. Logged into jlewis account on `dev-app-jl.procore.prod1` server and ran `ssh-keygen`
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T15_1.png?raw=true"/>
    
2. Then ran the following `ssh-copy-id jlewis@dev-ansible.procore.prod1` , entered my password and my key was added
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T15_2.png?raw=true"/>
    
3. Then tested connection with `ssh jlewis@dev-ansible.procore.prod1`
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T15_3.png?raw=true"/>
    
4. Ran the ssh-keygen command while in the `dev-ansible.procore.prod1` directory
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T15_4.png?raw=true"/>
    
5. Then ran the following `ssh-copy-id jlewis@10.1.XX.XX` since my server has not been added to the /etc/hosts file yet, entered my password and my key was added
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T15_5.png?raw=true"/>
    
6. Accessed `dev-app-jl.procore.prod1` server in order to obtain ssh public key by running `cat id_ed25519.pub` 
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T15_6.png?raw=true"/>
    
7. Finally, accessed GitLab and went to “User Settings” to click on “SSH Keys” and clicked “Add New Key” to paste key into database. Repeated the above steps for `dev-performance` server as well and uploaded both keys to GitLab:
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T15_7.png?raw=true"/>
</details>

<details>
<summary> 16. Add Dev Servers into Ansible inventory </summary>
    
<code style="white-space: pre-wrap;">TASK: To perform automated actions on our infrastructure, please add your development servers to the Ansible inventory file.</code>
    
**STEPS TAKEN:**
    
1. Refered to the [Procore wiki]() and SSH’d into `dev-ansible` server and edited the `/etc/hosts` file by adding the following to the end of the file
    * `10.1.XX.XX     dev-app-jl.procore.prod1                dev-app-jl`
    * `10.1.XX.XX     dev-performance-jl.procore.prod1        dev-perf-jl`
2. Accessed the inventory file (`/etc/ansible/hosts`) and added my ansible group `[dev-jl]`
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T16_1.png?raw=true"/>
    
3. Ran the following to test ping compatibility with my anisble group `ansible -m ping dev-jl`
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T16_2.png?raw=true"/>
</details>

<details>
<summary> 17. Patch your Dev Servers using Ansible </summary>
    
<code style="white-space: pre-wrap;">TASK: In accordance with company policy, all development servers must be patched regularly. Please follow the instructions provided under Infrastructure Resources to patch your development servers using Ansible.</code>
    
**STEPS TAKEN:**
    
1. Used `dnf update python3` to confirm it was installed and up to date on both servers
2. Reviewed the wiki for [Patching Schedule and Instructions](), then used `cd /opt/ansible/patching` to view the `dev-patch.yml` file and copy the contents into `dev-patch-jl.yml`
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T17_1.png?raw=true"/>
    
3. Ran `ansible-playbook dev-patch-jl-app.yml -K` and received the following results that did not match the wiki for a successful patch
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T17_2.png?raw=true"/>
    
4. After reading the fatal error messages and the playbook, it appears that there are some exclusions that are causing this issue. The first exclusion I removed was `kernel-*` and I ran `ansible-playbook dev-patch-jl-app.yml -K` again, which resolved 1 error
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T17_3.png?raw=true"/>
    
5. It appears that the other exclusion is causing an error, so I removed the filter for `rpm-*` and `var=out` line to run the command again and achieved the results as shown on the wiki for both of my servers. I changed the name of the file to `dev-patch-jl.yml`
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T17_4.png?raw=true"/>
</details>

<details>
<summary> 18. Please use Ansible to create the task below </summary>
    
<code style="white-space: pre-wrap;">TASK: The programmers on the webmasters team want to have a shared directory for collaboration on scripting knowledge for their division on all development servers.</code>
    
**STEPS TAKEN:**
    
1. Read the documentation for [ad-hoc commands](https://docs.ansible.com/ansible/latest/command_guide/intro_adhoc.html#patterns-and-ad-hoc-commands). Will attempt to write an ad-hoc command based on documentation: `ansible dev-jl -m ansible.builtin.file -a "dest=/opt/scripts/jlewis/ state=directory owner=jlewis group=webmasters mode=775" -K`
    * `dev-jl` specifies my development servers as learned from ticket 17.
    * `ansible.builtin.file` allows me to change ownership and set permissions.
    * `dest` is used to specify the directory path that I want to create.
    * `state` is used to specify that I would like to create a directory or check that the `dest` is a directory.
    * `owner` is used to specify which user owns the directory.
    * `group` is used to specify which group owns the directory.
    * `mode` is used to specify the permissions needed on the directory/file
    * `-K` is used to request the password to be able to run escalated privilege commands
        
        <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T18_1.png?raw=true"/>
        
2. After running the command, it appears that it could it did not complete the steps because the path is not correct or I did not give proper permissions. Ran `ansible --help` and read the options page for “Privilege Escalation Options:”
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T18_2.png?raw=true"/>
    
3. Decided to run the command with the -b option so that I would not be prompted for passwords and also learned that I do not have to put `ansible.builtin.file`, I can simply specify `file` to run the same command: `ansible dev-jl -m ansible.builtin.file -a "dest=/opt/scripts/jlewis/ state=directory owner=jlewis group=webmasters mode=775" -K -b`
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T18_3.png?raw=true"/>
    
4. I also learned that `-b` does the same thing as `--become-user=root`, so if I need to do this again, the `-b` option is much easier to remember. I verified that both servers had the shared directory created by running the following command: `ll -d /opt/scripts/jlewis/`
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T18_4.png?raw=true"/>
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T18_5.png?raw=true"/>
    
5. To do this as a playbook, I would simply have to create a file named `create_shared_directory.yml` and use `vi` to add the following:
    
    ```
    - hosts: dev-jl
      tasks:
        - name: Create directory
          ansible.builtin.file:
            dest: /opt/scripts/jlewis/
            state: directory
            owner: jlewis
            group: webmasters
            mode: '775'
    ```
    
6. Next, I would run the playbook with `ansible-playbook create_shared_directory.yml -K -b`
</details>

<details>
<summary> 19. Please update the system inventory database </summary>
    
<code style="white-space: pre-wrap;">TASK: For inventory purposes, please populate the system inventory database of your dev servers.</code>
    
**STEPS TAKEN:**
    
1. Accessed `/opt/ansible` on Ansible server to create file `git-repository.yml` and added the following input into the file:
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T19_1.png?raw=true"/>
    
    * The first task is to install `git` on the servers if it is not installed or confirm that it is already installed.
    * The next task is to clone the respository provided and save it under `~/scripts`
    * The last task runs the script file `host_facts.sh` found in the `~` directory
2. Ran the following command to see if input would complete the task and added the -vv option to show more details: `ansible-playbook git-repository.yml -K -b -vv`; however, it only installed git onto my servers and got stuck at the downloading tasks:
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T19_2.png?raw=true"/>
    
3. Decided to run the command `git clone` with the link by itself on each server to see what was going on and instantly realized that running a playbook would be more involved since `git` is asking for login credentials:
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T19_3.png?raw=true"/>
    
4. Researched more about playbook options so that I could incorporate the username and password input. I learned that it was safer to use a personal access token (PAT) and my username to achieve authentication protocol to be able to clone the repository, so I updated the `git-repository.yml` file as shown below:
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T19_4.png?raw=true"/>
    
5. Ran `ansible-playbook git-repository.yml -K -b` again and the following error was produced, which showed that the the file was not being found:
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T19_5.png?raw=true"/>
    
6. After further review, I noticed that the file name was not correct and the Infrastructure team confirmed with me that the file was actually deleted from the repository. They instructued me to use `host_fact.sh_DoNotDelete` file and I updated the `git-repository.yml` file again. I also used double quotes around the `git_token` and `repo` values due to the special characters used in them to prevent errors.
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T19_6.png?raw=true"/>
    
7. Ran `ansible-playbook git-repository.yml -K -b` again, which produced the following results showing that everything ran successfully:
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T19_7.png?raw=true"/>
    
8. I went to both servers and entered the `/tmp` directory to run `ls`, which showed that a `.txt` file was generated for both as shown below:
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T19_8.png?raw=true"/>
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T19_9.png?raw=true"/>
</details>

<details>
<summary> 20. Push the script to gitlab repo </summary>
    
<code style="white-space: pre-wrap;">TASK: The development department will need to have a new version of the host_facts.sh created and uploaded to Gitlab.</code>
    
**STEPS TAKEN:**
    
1. Logged in as `root` on dev-app server and accessed `/root/scripts` where the clone was stored in order to run: `cp host_fact.sh_DoNotDelete jlewis_host_facts.sh`
2. Then ran the following: `echo ‘date >> “/tmp/$HOSTNAME.txt"’ >> jlewis_host_facts.sh` and `cat jlewis_host_facts.sh` 
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T20_1.png?raw=true"/>
    
3. Watched the following [video](https://www.youtube.com/watch?v=mX7lKoabmDw) to learn how to commit changes from Git. In the `/root/scripts` directory, I ran `git init` to initialize the Git repository, then I ran `git add jlewis_host_facts.sh` and `git status`
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T20_2.png?raw=true"/>
    
4. Next, I ran `git commit -m “Adding jlewis_host_facts.sh file”`; however, the following error populated:
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T20_3.png?raw=true"/>
    
5. Ran `git status` and then ran `git restore --staged jlewis_host_facts.sh` to see if that would resolve the `git status` message and status showed the following:
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T20_4.png?raw=true"/>
    
6. Re-ran `git commit -m “Adding jlewis_host_facts.sh file”` again and realized that the error was produced because I specified file at the end of the quotation and that I did not need to do this…reran command as `git commit -m "Add jlewis_host_facts.sh"` and received the following results:
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T20_5.png?raw=true"/>
    
7. Next, I proceeded to push the changes by running the following command `git push -u origin master`
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T20_6.png?raw=true"/>
    
8. When I accessed the GitLab repository, my file was added as shown below:
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T20_7.png?raw=true"/>
</details>

<details>
<summary> 21. Spin up a Web server using a Kickstart file </summary>
    
<code style="white-space: pre-wrap;">TASK: One of our clients intends to build a staging web server to launch a new product. Please set up a new virtual machine (VM) using the naming convention provided below. Refer to the system inventory list to create this server.</code>

**STEPS TAKEN:**
    
1. Selected my Cluster folder and clicked on “Actions” to select “New Virtual Machine” and named “stage-web-jl.procore.prod1”
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T21_1.png?raw=true"/>
    
2. Input all information requested for requirements:
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T21_2.png?raw=true"/>
    
3. Powered on VM and interrupted boot process as specified on the “[How to use kickstart file]()” wiki to press “e” in order to edit the boot parameters for the line that started with `linuxefi` 
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T21_3.png?raw=true"/>
    
4. Added the required line of code so that the GRUB to run the kickstart configuration file and then pressed “`Ctrl-x`” to execute it.
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T21_4.png?raw=true"/>
    
5. The server successfully booted up and I was able to login; however, I did have to update the IP address because it defaulted to `10.1.XX.XX` and I was not able to install packages until I corrected it.
6. Lastly, I completed the steps required from tickets 8-10 to configure the mount points and DNS records:
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T21_5.png?raw=true"/>
</details>

<details>
<summary> 22. Configure FreeIPA Client on the Stage Virtual Machine </summary>
    
<code style="white-space: pre-wrap;">TASK: All new servers must be enrolled in our IPA server. Please enroll the staging server you just created.</code>

**STEPS TAKEN:**
    
1. Installed IPA onto staging server by following Ticket 5 steps:
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T22_1.png?raw=true"/>
    
2. Added SSH key from stage-web server by using the following command to create the unique key `ssh-keygen -t rsa -C "jlewis@stage-web-jl"` and copied it to dev-ansible server with `ssh-copy-id jlewis@dev-ansible` and vice versa.
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T22_2.png?raw=true"/>
    
3. Added stage-web-jl.procore.prod1 to inventory group and then performed Ansible Ping test to confirm they were all successful:
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T22_3.png?raw=true"/>
    
4. Added public key for stage-web server on to GitLab by using the following command: `cat id_rsa.pub`
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T22_4.png?raw=true"/>
</details>

<details>
<summary> 23. Disable and prevent SSH root user access to all your servers as part of the security audit requirement </summary>
    
<code style="white-space: pre-wrap;">TASK: Disallowing root logins over SSH requires system administrators to authenticate using their own individual accounts and then escalate to root via sudo or su. This practice enhances non-repudiation and provides a clear audit trail in the event of a security incident.</code>

**STEPS TAKEN:**
    
1. Followed instructions listed on out [Disabling SSH Root Access]() and confirmed that I was able to SSH into my IPA client account for `jlewis`. Proceeded to access each server via `root` account in order to edit the `/etc/ssh/sshd_config` file to set `PermitRootLogin` to `no`:
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T23_1.png?raw=true"/>
    
2. Next, ran `systemctl restart sshd` and `systemctl daemon-reload`
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T23_2.png?raw=true"/>
    
3. Then I checked to see if the server would allow me to SSH into root and even though I entered the correct password each time, it did not let me access via the `ssh` command, but I was able to use the `su` command to gain root access:
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T23_3.png?raw=true"/>
</details>

<details>
<summary> 24. Restrict SSH access on all servers except Bastion Host (Rich Rule) </summary>
    
<code style="white-space: pre-wrap;">TASK: The security department requests that all servers created on our infrastructure only accept SSH communication from the Bastion host. Please follow the steps outlined on the wiki page to secure your servers accordingly.</code>

**STEPS TAKEN:**
    
1. Reviewed the wiki on how to use the [Bastion Host to Restrict Access](). I made sure I had two terminal sessions open logged in to each server then proceeded to follow the first step, which was to allow the Bastion Host IP by running the following command: `sudo firewall-cmd --permanent --add-rich-rule='rule family="ipv4" source address="{ipaddressofbastionhost}" port port="22" protocol="tcp" accept’`
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T24_1.png?raw=true"/>
    
2. Next, I needed to remove the Default SSH access rules by running the following commands:
    * `sudo firewall-cmd --permanent --remove-port=22/tcp`
    * `sudo firewall-cmd --permanent --remove-service=ssh`
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T24_2.png?raw=true"/>
    
3. Then, I reloaded the firewall to apply the changes by running the following:
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T24_3.png?raw=true"/>
    
4. Next, I exited one terminal to see if I could SSH into it; however, I was not able to SSH via the normal route:
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T24_4.png?raw=true"/>
    
5. I then proceeded to SSH into the Bastion server with my IPA username
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T24_5.png?raw=true"/>
    
6. Finally, I attempted to SSH into my terminal from the Bastion server and I was successful
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T24_6.png?raw=true"/>
    
7. Before leaving, I wanted to make it easier to remember my servers, so I updated the `/etc/hosts` file so that my server names were present and I added an RSA SSH key from the Bastion server to each of my servers below to avoid having to enter a password.
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T24_7.png?raw=true"/>
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T24_8.png?raw=true"/>
</details>

<details>
<summary> 25. Graylog client </summary>
    
<code style="white-space: pre-wrap;">TASK: Please configure your dev-app, dev-performance and stage-web virtual machines to send logs to the Graylog server.</code>

**STEPS TAKEN:**
    
1. Read the wiki for [Shipping logs from host to Graylog server](). The first thing I had to do was check to make sure that the Graylog server’s firewall was configured to accept syslog input over UDP port 5140. Used SSH to access stage-graylog server and check the firewall settings:
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T25_1.png?raw=true"/>
    
    If it was not configured, I would need to run the following commands:
    
    * `sudo firewall-cmd --zone=public --add-port=5140/udp --permanent`
    * `sudo firewall-cmd --reload`
2. The first thing I did to send my logs to Graylog was create a new rsyslog configuration file using the following command on each server: `sudo vim /etc/rsyslog.d/90-graylog.conf` and added the following information into the file `*.*** @10.1.XX.XX:5140;RSYSLOG_SyslogProtocol23Format`
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T25_2.png?raw=true"/>
    
3. Then I restarted the rsyslog service using the following: `sudo systemctl restart rsyslog`. Next, I logged into the Graylog web interface via the following link with my freeIPA credentials: http://10.1.XX.XX:9000/search?q=http&rangetype=relative&relative=300  and searched for my server to confirm that it was transmitting logs.
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T25_3.png?raw=true"/>
</details>

<details>
<summary> 26. Install Apache Web Server </summary>
    
<code style="white-space: pre-wrap;">TASK: Please install the apache webserver to the stage-web-jl.procore.prod1-IP server. Make sure to start and enable apache.</code>

**STEPS TAKEN:**
    
1. The first thing I did was check to see if the service was installed with `sudo dnf info httpd` and checked the status by running the following `systemctl status httpd`
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T26_1.png?raw=true"/>
    
2. Next, I ran `sudo dnf install httpd -y` to install the package and then ran `systemctl enable --now httpd`. I was prompted to enter the procore password three times, then I ran `systemctl status httpd` again
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T26_2.png?raw=true"/>
</details>

<details>
<summary> 27. Allow apache to the firewall </summary>
    
<code style="white-space: pre-wrap;">TASK: After installing Apache, please open ports 80 and 443 on the stage web server you created. Additionally, allow the Apache service through the firewall.</code>

**STEPS TAKEN:**
    
1. On `stage-web` VM, I performed the following commands to open ports 80 and 443, and to add Apache:
    1. `sudo firewall-cmd --permanent --add-port=80/tcp`
    2. `sudo firewall-cmd --permanent --add-port=443/tcp`
    3. `sudo firewall-cmd --permanent --add-service=http`
    4. `sudo firewall-cmd --permanent --add-service=https`
2. Then ran the following `sudo firewall-cmd --list-all` to confirm everything was added correctly and then ran `sudo firewall-cmd --reload`:
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T27_1.png?raw=true"/>
</details>

<details>
<summary> 28. Configure apache web content </summary>
    
<code style="white-space: pre-wrap;">TASK: Please configure ariclaw web server contents on stage-web server which can be found at the URL below.</code>

**STEPS TAKEN:**
    
1. The first thing I had to do was install `git` with `sudo dnf install git`. Then I ran `git clone git@gitlab.com:procoreplusmd/ariclaw.git`, which downloaded the repository to my VM:
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T28_1.png?raw=true"/>
    
2. Then started watching this video to better understand [how to use GitLab](https://pie.yt/?v=https://youtu.be/4lxvVj7wlZw?si=Jn9TlcVhVNIubosn&pieshare=1). Ran `git config --global [user.name](http://user.name/) "justintimejlew"` to specify myself on the respository, moved it to `/var/www/html` and ran `git config --list`
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T28_2.png?raw=true"/>
    
3. Accessed the IP address link and saw the following, which showed that the site was not displaying content:
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T28_3.png?raw=true"/>
    
4. Accessed `/etc/httpd/conf.d/welcome.conf` and read the instructions which stated that I was supposed to comment all of the lines out:
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T28_4.png?raw=true"/>
    
5. Then I restarted the Apache services by running `systemctl restart httpd`
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T28_5.png?raw=true"/>
    
6. Accessed IP address link again and saw the following, which I believe is what is supposed to be displaying for the task
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T28_6.png?raw=true"/>
    
7. When I tried to SSH into git this is what I saw, which shows that my SSH key is working properly; however, my connection was instantly closed. When I search this, I learned that this is a non-fatal warning because GitLab does not have an interactive shell. If I did not want to see the error message, I could run `ssh -T git@gitlab.com`, but it’s not needed because I have completed the task:
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T28_7.png?raw=true"/>
    
8. After reading through the `/etc/httpd/conf` files, it appears that the site is not showing everything correctly. Therefore, under the repository folder, I changed the permissions of the directory by running the following:
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T28_8.png?raw=true"/>
    
9. Added the following configuration file under `/etc/httpd/conf.d/ariclaw.conf` and input the following content:
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T28_9.png?raw=true"/>
    
10. Restarted httpd service:
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T28_10.png?raw=true"/>
    
11. Cleared my cache on my webbrowser and attempted to access the IP address link again and it provided me with the following:
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T28_11.png?raw=true"/>
</details>

<details>
<summary> 29. Update web content for ariclaw </summary>
    
<code style="white-space: pre-wrap;">TASK: Ariclaw has recently changed their phone number. Please update the website content.</code>

**STEPS TAKEN:**
    
1. The current site shows the following information for the phone number in two places:
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T29_1.png?raw=true"/>
    
2. Accessed `/var/www/html` and `/nfs/incoming/vhosts/ariclaw/htdocs` to update the `contact.html` file to replace it with the updated phone number:
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T29_2.png?raw=true"/>
    
3. Ran `sudo systemctl restart httpd` and checked the site again to confirm that the phone number has been updated:
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T29_3.png?raw=true"/>
</details>

<details>
<summary> 30. Install MariaDB </summary>
    
<code style="white-space: pre-wrap;">TASK: The development team requested the installation of MariaDB version 10.3 on your dev-app-jl.procore.prod1-IP server.</code>

**STEPS TAKEN:**
    
1. Read wiki on [How to install MariaDB](). Created and configured the MariaDB repository with the following command `sudo vi /etc/yum.repos.d/MariaDB.repo` in order to insert the following:
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T30_1.png?raw=true"/>
    
2. Installed MariaDB Server and Client by running the following: `sudo dnf install MariaDB-server MariaDB-client` then started the services by running `sudo systemctl enable --now mariadb` and confirmed by running `sudo systemctl status mariadb`
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T30_2.png?raw=true"/>
    
3. Next, I ran the secure installation script `sudo mariadb-secure-installation` and followed the prompts until it was secured.
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T30_3.png?raw=true"/>
    
4. Lastly, I ran `mysql -u root -p` and entered the password created during prompts:
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T30_4.png?raw=true"/>
</details>

<details>
<summary> 31. Create a snapshot of your VM </summary>
    
<code style="white-space: pre-wrap;">TASK: The infrastructure team will perform a company wide maintenance next week. Please create a snapshot of all your Virtual Machines.</code>

**STEPS TAKEN:**
    
1. Accessed vSphere Client and click on each VM to be able to access the “Snapshots” tab to click on “Take Snapshot…”
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T31_1.png?raw=true"/>
    
2. Named each snapshot respective to the server and Ticket 31:
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T31_2.png?raw=true"/>
    
3. Waited till all of the VM’s had there snapshots created as shown below for each server:
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T31_3.png?raw=true"/>
</details>

<details>
<summary> 32. Register your VMs to Foreman </summary>
    
<code style="white-space: pre-wrap;">TASK: The Security Team is requiring that all servers be registered with the Foreman server and patched accordingly moving forward.</code>

**STEPS TAKEN:**
    
1. Reviewed the wiki to better understand [Foreman client installation and configuration](). The first thing I did was SSH into the `stage-foreman` VM, then switched to root using the password provided in order to copy the Foreman proxy key to all of the VM; however, I was unable to access the server due to firewall restrictions for SSH:
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T32_1.png?raw=true"/>
    
2. I updated the `/etc/ssh/sshd_config` file to allow for root login and reloaded the firewall to ensure the changes were applied correctly (`sudo systemctl restart sshd && sudo systemctl daemon-reload`) so that I could run the command again (`ssh-copy-id -i ~foreman-proxy/.ssh/id_rsa_foreman_proxy.pub 10.1.XX.XX`) and entered my root password for each client VM to successfully add the keys:
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T32_2.png?raw=true"/>
    
3. Next, I installed the `subscription-manager` package: `curl --insecure --output katello-ca-consumer-latest.noarch.rpm`
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T32_3.png?raw=true"/>
    
4. Then ran the following command `sudo dnf localinstall katello-ca-consumer-latest.noarch.rpm` to install the Katello CA certificate and registered the server with Foreman and entered my password when prompted: `subscription-manager register --org="Procore" --activationkey="XXXXXX"`
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T32_4.png?raw=true"/>
    
5. Next, I needed to verify the registration in Foreman Web UI by logging into the following site with my freeIPA credentials: https://10.1.XX.XX/users/login and then accessed the Hosts—>Content Hosts tab to filter for my VMs:
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T32_5.png?raw=true"/>
</details>

<details>
<summary> 33. Run remote command from Foreman </summary>

<code style="white-space: pre-wrap;">TASK: The Security Team needs to create a local user on all the VMs of the infrastructure using Foreman, the user's name is Reuben Camilo, the username would be rcamilo.</code>

**STEPS TAKEN:**
    
1. Navigated to the https://10.1.XX.XX/hosts and filtered for my VMs, then selected all 3 of them in order to click “Schedule Remote Job”
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T33_1.png?raw=true"/>
    
2. Next, I added the command `useradd -C “Reuben Camilo” rcamilo` to the “Job Invocation” section, added the password for root, and clicked Submit:
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T33_2.png?raw=true"/>
    
3. It showed that all of the jobs failed and the reason I believe is because I changed Permit Root login to “no” again. Changed my `dev-app-jl.procore.prod1` server to “yes” to see if this would affect it.
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T33_3.png?raw=true"/>
    
4. When I clicked on my first VM, I saw why it clearly failed due to using the wrong option `-C`, when I should have used `-c`:
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T33_4.png?raw=true"/>
    
5. Clicked “ReRun” and updated the command to `useradd -c “Reuben Camilo” rcamilo` and reran again, but it produced the same error so I just ran `useradd rcamilo`, which showed that it was only success if `PermitRootLogin` was set to “yes:”
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T33_5.png?raw=true"/>
    
6. Set all servers to `PermitRootLogin` and reran the job, which showed successful on all 3 VMs
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T33_6.png?raw=true"/>
</details>

<details>
<summary> 34. Create a central location for logs </summary>

<code style="white-space: pre-wrap;">TASK: We would like to establish a central location on the server dev-app-jl.procore.prod1-IP to store logs.</code>

**STEPS TAKEN:**
    
1. Powered off `dev-app-jl.procore.prod1` server and clicked on “Edit Settings” in order to add a new 1 GB hard disk, clicked “OK” and powered VM back on:
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T34_1.png?raw=true"/>
    
2. When I powered my VM back on, I used `lsblk` to confirm that the hard disk was added to my VM, which is found under `/dev/sdb`:
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T34_2.png?raw=true"/>
    
3. Used `fdisk /dev/sdb` to create partition
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T34_3.png?raw=true"/>
    
4. Created `ext4` mount by creating VG and LV first:
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T34_4.png?raw=true"/>
    
5. Created mount point `/lfjs/logs` by using `mkdir -p /lfjs/logs`, created local user `lfjs` with `useradd lfjs`, and used `sudo chown -R lfjs:webmasters /lfjs/logs` to assign the correct owners to the mount point. It should be noted that permission `755` is already set by default.
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T34_5.png?raw=true"/>
    
6. Then used `sudo chmod 2755 /lfjs/logs/` to assign the proper permissions for the mount point and to ensure all future files will be assigned to the `webmasters` group.
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T34_6.png?raw=true"/>
    
7. Finally, edited the /etc/fstab file to mount the directory persistently
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T34_7.png?raw=true"/>
    
8. Confirmed with `lsblk`
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T34_8.png?raw=true"/>
</details>

<details>
<summary> 35. Users are having issues with SSH </summary>

<code style="white-space: pre-wrap;">TASK: We have received numerous emails from developers regarding issues with SSH access to your dev-app server. Please investigate the issue and attach the last 20 lines of the logs to this ticket.</code>

**STEPS TAKEN:**
    
1. Used `id apprentice` to confirm user existed and then attempted to SSH into apprentice profile by using `ssh apprentice@localhost`:
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T35_1.png?raw=true"/>
    
2. Next, attempted to access the `/lfjs/logs` directory as `apprentice` and noticed there was a directory; however, I was unable since the `lost+found` folder was set to `root` despite me previously setting everything to `lfjs` for user and `webmasters` for group.
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T35_2.png?raw=true"/>
    
3. I exited and noticed that everything was set back to root under my account, so I went through the steps on ticket 35 to assign correct permissions again and used `su apprentice` to access the directory and confirm the file showed proper permissions
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T35_3.png?raw=true"/>
    
4. When I accessed the directory, there was no contents to be shown:
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T35_4.png?raw=true"/>
    
5. The next thing I did was cd into `/var/log` and tried to access `tallylog` and `lastlog`, but I did not find anything there as well:
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T35_5.png?raw=true"/>
    
6. Next, since I could not find anything I decided to run `find / -type f -user apprentice | grep ssh` and ran cat on all 3 files shown; however, there was nothing to note except it appears that there is a similar key in both `known_hosts` and `known_hosts.old` 
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T35_6.png?raw=true"/>
    
7. Lastly, I exited the `apprentice` user account and checked the `/var/log/secure` file for the last 20 items and the only thing that appears to be going on with user `apprentice` is they are not using `port 22` for SSH:
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T35_7.png?raw=true"/>
</details>

<details>
<summary> 36. Users are reporting repo issues </summary>
    
<code style="white-space: pre-wrap;">TASK: One of our clients has reported that the del.extreme-ix repository is not functioning properly on dev-app-[initials].procore.prod1-IP. Could someone from the infrastructure team please investigate this issue?</code>
    
**STEPS TAKEN:**
    
1. Accessed the epel.repo file and I remember when I originally set this up, `enabled=1` was not a part of the instructions for setup, but I included it. This may be the issue if I didn’t account for adding it, but after looking at the url again, they may be experiencing an issue if the url requires `https`. At this time, I do not believe this is the issue. Please see below for reference:
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T36_1.png?raw=true"/>
</details>

<details>
<summary> 37. User is having issue in accessing file </summary>
    
<code style="white-space: pre-wrap;">TASK: User created in ticket 6 has reported that he/she is unable to write to the directory /lfjs/logs when logged into dev-app-[initials].procore.prod. Please provide your assistance in resolving this issue.</code>
    
**STEPS TAKEN:**
    
1. `msoriano` is apart of the webmasters group so it is not clear why they do not have access to write. Decided to create an ACL for user `msoriano` by running the following command: `sudo setfacl -m u:msoriano:rw /lfjs/logs` since only group and others are only supposed to be read and write.
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T37_1.png?raw=true"/>
</details>

<details>
<summary> 38. Urgent! Malicious IP </summary>

<code style="white-space: pre-wrap;">TASK: The networking team has reported a malicious IP that is trying to get into our network.</code>

**STEPS TAKEN:**
    
1. Used Google to search for “how do I block an IP address from ssh on centos 9” and the following was provided as steps:
2. Ran the following command on each VM `sudo firewall-cmd --permanent --add-rich-rule='rule family="ipv4" source address="XX.XX.XX.XX" port port="22" protocol="tcp" drop'`
3. Then ran `sudo firewall-cmd --reload` in order to apply the new rich rule.
4. Lastly, I ran `sudo firewall-cmd --list-all` to confirm that it was applied on each VM:
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T38_1.png?raw=true"/>
</details>

<details>
<summary> 39. Please provide the apache version </summary>

<code style="white-space: pre-wrap;">TASK: The development team is helping us troubleshoot an issue with apache on stage-web-jl.procore.prod1-IP.</code>

**STEPS TAKEN:**
    
1. Ran both `dnf list httpd` and `dnf info httpd` to obtain the version information shown in two different formats:

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T39_1.png?raw=true"/>
</details>

<details>
<summary> 40. Get a list of all the users that have enrolled on FreeIPA </summary>

<code style="white-space: pre-wrap;">TASK: The administration is requesting a detailed list of all users registered on the FreeIPA server. Please generate this list using IPA commands and redirect the output to a file. Master centralized authentication and streamline user/group management using FreeIPA.</code>

**STEPS TAKEN:**
    
1. Accessed dev-app-jl server and used `ipa user-find msoriano` to confirm user was in database and then ran `ipa user-del msoriano` to delete user:
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T40_1.png?raw=true"/>
    
2. Then ran `ipa user-find >> ipa_users.txt`p to add all the users into the file.
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T40_2.png?raw=true"/>
</details>

<details>
<summary> 41. Please configure cronjob </summary>

<code style="white-space: pre-wrap;">TASK: Hi there, the engineering team would like to have a cron job configured on the dev-app-jl.procore.prod1-IP server.</code>

**STEPS TAKEN:**
    
1. Accessed script location and copied the script file from `/nfs/incoming/scripts/logs.sh` to `~/` and then changed permission of file to my freeIPA user:
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T41_1.png?raw=true"/>
    
2. Ran `sudo systemctl status crond` to confirm service was running and then ran `crontab -eu jlewis` to input the following information to execute the cron job:
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T41_2.png?raw=true"/>
    
3. Checked /var/log/cron and confirmed that the script was running every 6 hours:
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T41_3.png?raw=true"/>
</details>

<details>
<summary> 42. Please create a cronjob </summary>

<code style="white-space: pre-wrap;">TASK: Please create a cronjob on stage-web-jl.procore.prod1-IP server to restart apache every 2 days at 11 AM.</code>

**STEPS TAKEN:**
    
1. Set up cronjob on `stage-web-jl` server by using the following commands:
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T42_1.png?raw=true"/>
    
2. Confirmed cronjob was running by setting up a temporary duplicate that ran every 2 minutes.
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T42_2.png?raw=true"/>
    
3. After checking `/var/log/cron`, I saw that the job ran; however, there was an error since it requires authentication:
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T42_3.png?raw=true"/>
    
4. Cronjob needs to run as `root` so I ran the following command `sudo crontab -eu root` to add the one cronjob and test if the job ran successfully:
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T42_4.png?raw=true"/>
    
5. Updated cronjob to run `0 11 */2 * * systemctl restart httpd` as root, as shown below:
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T42_5.png?raw=true"/>
</details>

<details>
<summary> 43. Create NAGIOS user and configure access </summary>

<code style="white-space: pre-wrap;">TASK: To utilize the NAGIOS service, you need to create an HTTP user on the server. Please refer to the wiki page below for detailed instructions.</code>

**STEPS TAKEN:**
    
1. Read the wiki for “[Adding users to Nagios]()” and started by using the following command to SSH into server: `ssh jlewis@dev-nagios`:
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T43_1.png?raw=true"/>
    
2. Next, I added a user with htpasswd by running the following command: `htpasswd /usr/local/nagios/etc/htpasswd.users jlewis`
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T43_2.png?raw=true"/>
    
3. Next, I edited the cgi.cfg configuration file by running the following command: `sudo vi /usr/local/nagios/etc/cgi.cfg` and added my user to the end of all the directives listed.
    
4. Then, I simply restarted the Nagios service to bring in my changes by running: `sudo systemctl restart nagios` and lastly, I verified my user access by visiting the following url () and logging in with the credentials that I created.
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T43_3.png?raw=true"/>
</details>

<details>
<summary> 44. Add the servers to Nagios </summary>

<code style="white-space: pre-wrap;">TASK: Please add your Virtual machines to Nagios monitoring system.</code>

**STEPS TAKEN:**
    
1. Reviewed wiki for “[Adding servers for Nagios monitoring]()” and the first thing I did was install NRPE and Nagios plugins on my `stage-nagios-jl` server by running the following `sudo dnf install epel-release nrpe nagios-plugins-{load,http,users,procs,disk,swap,nrpe,uptime} -y`
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T44_1.png?raw=true"/>
    
2. Next, I edited the NRPE configuration file to allow my Nagios server IP (with `sudo vim /etc/nagios/nrpe.cfg`) and updated the “allowed_hosts” directive to add `allowed_hosts=127.0.0.1,10.1.XX.XX` 
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T44_2.png?raw=true"/>
    
3. I started the NRPE service by running `sudo systemctl enable --now nrpe.service` and then I proceeded to add my hosts to the Nagios Server Configuration by creating a config file for the `dev-app-jl` and `stage-web-jl` servers by copying the `yt-templates.cfg.bak` by using the following `sudo cp yt-templates.cfg.bak dev-app-jl.cfg` and `sudo cp yt-templates.cfg.bak stage-web-jl.cfg` to be able to insert the following host definitions for each:
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T44_3.png?raw=true"/>
    
4. Next, I had to link the new config files to the main Nagios Config file (`sudo vi /usr/local/nagios/etc/nagios.cfg`) by adding the following line under the “monitoring the local (Linuxi) host” section: `cfg_file=/usr/local/nagios/etc/objects/dev-app-jl.cfg` and `cfg_file=/usr/local/nagios/etc/objects/stage-web-jl.cfg`

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T44_4.png?raw=true"/>
    
5. Then, I reloaded the Nagios service (`sudo systemctl reload nagios.service`) to ensure my config files linked properly; however, received warning message:
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T44_5.png?raw=true"/>
    
6. I referenced Grok and it suggest that I run: `sudo /usr/local/nagios/bin/nagios -v /usr/local/nagios/etc/nagios.cfg` which showed me the following error message:
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T44_6.png?raw=true"/>
    
7. I updated the config file `/usr/local/nagios/etc/nagios.cfg`and commented out the referenced file that was missing from the directory and reran `sudo /usr/local/nagios/bin/nagios -v /usr/local/nagios/etc/nagios.cfg` which showed no errors or warnings, but when I try to run `sudo systemctl reload nagios.service` I got the same message from step 5. 
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T44_7.png?raw=true"/>
    
8. The issue was that someone changed the user:group of the `/usr/local/nagios/` directory, which prevented the service from running. I had to run `sudo chown -R nagios:nagios /usr/local/nagios/`to correct the directories, I was finally able to get the service running again
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T44_8.png?raw=true"/>
    
9. Lastly, I accessed http://10.1.XX.XX/nagios/ and visited the “Services” section and was able to confirm that my hosts were being monitored and both statuses showed OK!
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T44_9.png?raw=true"/>
</details>

<details>
<summary> 45. Configure FTP Server and Client </summary>

<code style="white-space: pre-wrap;">TASK: Please configure the FTP server on dev-app-jl.procore.prod1-IP and the FTP client on stage-web-jl.procore.prod1-IP.</code>

**STEPS TAKEN:**
    
1. Used `sudo dnf info ftp` to see if `ftp` was installed and it was not so I used `sudo dnf install ftp -y` to install it on both servers and then I accessed `/nfs/incoming/vhosts/ftp-files/` on `dev-app-jl` in order to use `cp ftp-prod.config ~/`
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T45_1.png?raw=true"/>
    
2. Next, I added the ftp service to both servers by running the following command: `sudo firewall-cmd --permanent --add-service=ftp` and then ran sudo `firewall-cmd --reload` to apply the changes
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T45_2.png?raw=true"/>
    
3. When I tried to run `ftp stage-web-jl`, I received the following error message
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T45_3.png?raw=true"/>
    
4. Googled “how to use ftp on centOS” and the first thing they said to do was `install vsftpd` so I used `sudo yum install vsftpd -y` to install it on `dev-app-jl` and `stage-web-jl`. Next, I ran sudo `firewall-cmd --permanent --add-port=21/tcp` to open the ftp port, reloaded it, and ran `sudo systemctl enable --now vsftpd`
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T45_4.png?raw=true"/>
    
5. Then I used `ftp dev-app-jl` again to login using my freeIPA credentials from `stage-web-jl`. I used `ls` to confirm the file was present on the home directory and then I ran `get ftp-prod.config` to download the file.
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T45_5.png?raw=true"/>
    
6. Lastly, I used `ll` to confirm that the file was on the home directory for `stage-web-jl`
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T45_6.png?raw=true"/>
</details>

<details>
<summary> 46. Create tasks using Ansible Playbook </summary>

<code style="white-space: pre-wrap;">TASK: Please create an ansible playbook that would perform the below tasks on dev-app-jl.procore.prod1-IP.</code>

**STEPS TAKEN:**
    
1. Accessed the `dev-ansible` server and created the file `user_add.yml` in a folder for my playbooks: `/etc/ansible/playbook/jlewis`. Reviewed Ansible Documentation for [Manage user accounts](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/user_module.html) and [Manage packages with dnf](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/dnf_module.html)
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T46_1.png?raw=true"/>
    
2. Then I ran `ansible-playbook user_add.yml -K -b`
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T46_2.png?raw=true"/>
    
3. Confirmed on `dev-app-jl` server that everything was completed correctly:
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T46_3.png?raw=true"/>
</details>

<details>
<summary> 47. Closing these ports via an ansible playbook </summary>

<code style="white-space: pre-wrap;">TASK: Please create an Ansible playbook to close ports 80 and 443 on dev-app-jl.procore.prod1-IP.</code>

**STEPS TAKEN:**
    
1. Searched Ansible Documentation and reviewed the [ansible.posix.firewalld](https://docs.ansible.com/ansible/latest/collections/ansible/posix/firewalld_module.html#examples) information since I couldn’t find `ansible.builtin.firewalld` documentation and wrote the `close_ports.yml` file:
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T47_1.png?raw=true"/>
    
2. Ran the following command: `ansible-playbook close_ports.yml -K -b`
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T47_2.png?raw=true"/>
</details>

<details>
<summary> 48. Please create backups for your server kernel </summary>

<code style="white-space: pre-wrap;">TASK: The infrastructure team will deploy a company wide kernel update next week.</code>

**STEPS TAKEN:**
    
1. Accessed /lib/modules for each server and used the following command to create a backup to the requested location: `sudo tar -czvf /nfs/incoming/vhosts/backup/dev-app-jl-kernel-backup.tar.gz 5.14.0-621.el9.x86_64` and `sudo tar -czvf /nfs/incoming/vhosts/backup/stage-web-jl-kernel-backup.tar.gz 5.14.0-575.el9.x86_64/`
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T48_1.png?raw=true"/>
</details>

<details>
<summary> 49. Create a Symlink </summary>

<code style="white-space: pre-wrap;">TASK: Please create a symlink in your home directory on your stage-web VM for the file /var/www/html/ariclaw/elements.html and name the symlink elements.</code>

**STEPS TAKEN:**
    
1. Ran the following command: `ln -s /var/www/html/ariclaw/elements.html ~/elements`

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T49_1.png?raw=true"/>
</details>

<details>
<summary> 50. Provide log information from Graylog </summary>

<code style="white-space: pre-wrap;">TASK: The development team requires information about the MariaDB database you installed on your dev-app server. Please query the logs using the Graylog server to determine the exact date and time of the installation.</code>

**STEPS TAKEN:**
    
1. Accessed graylog site and searched for “MariaDB”
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T50_1.png?raw=true"/>
    
2. Results did not show much, so I clicked the dropdown on “source” and added dev-app-jl. This updated the search content to “MariaDB AND source:dev\-app\-jl” and I changed the time from “last 5 minutes” to “last 14 days.” This showed me that I initially installed MariaDB on October 18
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T50_2.png?raw=true"/>
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T50_3.png?raw=true"/>
</details>

<details>
<summary> 51. RAM upgrade request </summary>

<code style="white-space: pre-wrap;">TASK: The infrastructure team is requesting that you scale up dev-app-jl.procore.prod1-IP due to an increase in user requests. Please create a clone of the virtual machine before making any changes.</code>

**STEPS TAKEN:**
    
1. Powered down `dev-app-jl` server in order to clone. On vSphere Client, I clicked clone to VM on my `dev-app-jl` server and named it `dev-app-jl-clone`
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T51_1.png?raw=true"/>
    
2. Next, I updated the my memory from 1GB to 1536 MB
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T51_2.png?raw=true"/>
    
3. Lastly, I powered my VM back on and ran `free -mh` to confirm the amount of RAM was updated:
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T51_3.png?raw=true"/>
    
4. Powered on the clone VM and ran `free -mh` to confirm that 500MB was added. It can be seen below that I only had 55MB free and now I have 612MB:
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T51_4.png?raw=true"/>
</details>

<details>
<summary> 52. Storage request </summary>

<code style="white-space: pre-wrap;">TASK: Users have requested additional space to be allocated to the /lfjs/logs filesystem on dev-app-jl.procore.prod1-IP.</code>

**STEPS TAKEN:**
    
1. Ran `lsblk` to confirm the file system and it showed that there was no free space to add to the existing filesystem:
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T52_1.png?raw=true"/>
    
2. Next, I ran `fdisk /dev/sdb` to add another partition for 100MB.
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T52_2.png?raw=true"/>
    
3. Then, I created the PV in order to add it to the VG
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T52_3.png?raw=true"/>
    
4. I used `sudo vgextend vglogs /dev/sdb2` to extend the VG size and then `lvextend -r -L +96 /dev/vglogs/lvlogs` to extend the LV
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T52_4.png?raw=true"/>
    
5. Finally ran `lsblk` to confirm new storage amount:
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T52_5.png?raw=true"/>
</details>

<details>
<summary> 53. Create a script to gather these info below </summary>

<code style="white-space: pre-wrap;">TASK: Please create a script to gather information about your VM.</code>

**STEPS TAKEN:**
    
1. Reviewed YellowTail notes and ticket 20. The following commands will help me gather the information required, but I had to refer to the man pages in order to better understand which options I needed to use for each one:
    * `date`
    * `last -F 10`
    * `free -h`
    * `uname -srv`
    * `nmcli | grep “inet4 10.*”`
2. I created the file `/tmp/serverinfo.info` and started to populate the following to test the file:
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T53_1.png?raw=true"/>
    
3. Next, I changed the file permission by using `sudo chmod +x serverinfo.info` and ran it with the following `./tmp/serverinfo.info` on each server:
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T53_2.png?raw=true"/>
    
4. At this time, my network access was giving me issues and I could not access my other VMs to provide screenshots.
</details>

<details>
<summary> 54. Create your own GitLab repository </summary>

<code style="white-space: pre-wrap;">TASK: For documentation purposes, we request that everyone create their own GitLab repository and upload their Ansible playbooks and Bash scripts.</code>

**STEPS TAKEN:**
    
1. I prompted my LLM to question me throughout the process instead of giving me answers. I learned about `scp` and `rsync` for copying the files from my `dev-ansible` server to my `dev-app-jl` server since this is where my playbooks are located; however, I do not have an SSH key saved on GitLab for `dev-ansible`. Decided to run `rsync` since it mirrors any updates made on my `dev-ansible` server. Ran the following command `rsync -avs --delete jlewis@dev-ansible:/etc/ansible/playbook/jlewis /home/jlewis/gitlab`
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T54_1.png?raw=true"/>
    
    * `-a`: archive mode (recursive, preserves symlinks/permissions/times/owner/group)
    * `-v`: verbose output
    * `-z`: compresses data during transfer
    * `--delete`: delete files in dest not in src (allows for mirroring).
2. Files were copied successfully, so I accessed [GitLab](http://gitlab.com) and clicked on “+” and then click “New project/repository,” selected “Blank Project,” entered my repository name, URL, and slug, and then clicked “Create Project”
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T54_2.png?raw=true"/>
    
3. Next, I copied the URL (https://gitlab.com/justintimejlew/ansible_playbooks) and on my `dev-app-jl` server under `/home/jlewis/gitlab` I ran 
    * `git init`
    * `git remote add origin https://gitlab.com/justintimejlew/ansible_playbooks`
    * `git status`
    * `git add .`
    * `git commit -m “Initial commit: Ansible playbooks and scripts”`
    * `git push -u origin master` ran into error because I changed the name to `main`
        
        <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T54_3.png?raw=true"/>
        
4. Check the `man` pages for `git pull` and decided to run `git pull --rebase origin main` first and then `git push -u origin main` again
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T54_4.png?raw=true"/>
    
5. Then I saw on GitLab that my files were committed to the following URL: https://gitlab.com/justintimejlew/ansible_playbooks/
</details>

<details>
<summary> 55. Please rotate HTTPD logs </summary>

<code style="white-space: pre-wrap;">TASK: The ariclaw website is generating a large number of logs. Please modify the log rotation settings to rotate the HTTPD logs daily and ensure that log rotation retains logs for only 14 days on stage-web-jl.procore.prod1-IP.</code>

**STEPS TAKEN:**
    
1. Accessed /etc/logrotate.d/http and set the following parameters: `daily` and `rotate 14`
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T55_1.png?raw=true"/>
    
    * `daily` - rotates every day.
    * `rotate N` - this keeps old logs for N days.
2. Then I ran `sudo systemctl status logrotate` which showed me that the service runs and then deactivates after it runs
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T55_2.png?raw=true"/>
    
3. Lastly, I ran `sudo logrotate -f /etc/logrotate.d/httpd` to force the changes made.
</details>

<details>
<summary> 56. Add both of your servers to CheckMK </summary>

<code style="white-space: pre-wrap;">TASK: Please add both of you servers to CheckMK monitoring tools.</code>

**STEPS TAKEN:**
    
1. Reviewed the wiki for “[How to add clients in Check-mk]().” Installed wget (`sudo dnf install wget`) in order to installed the required tools and the Checkmk agent. Then ran the following commands: `wget` to download the rpm and `sudo dnf -y localinstall check-mk-agent-2.3.0p2-1.noarch.rpm` to install it.
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T56_1.png?raw=true"/>
    
2. Next, I opened port 6556 for Checkmk agent communication by running the following commands: `sudo firewall-cmd --zone public --add-port 6556/tcp --permanent`, `sudo firewall-cmd --reload`, and `systemctl status check-mk-agent.socket`
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T56_2.png?raw=true"/>
    
3. Then I accessed the Checkmk Web Interface located at http://10.1.XX.XX/procore/check_mk, used the login credentials provided to access the site, navigated to the “Hosts” section by clicking on the “Setup” tab, then clicked on the DEV directory in order to click “Add Host”
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T56_3.png?raw=true"/>
    
4. Next, I entered my hostname for each VM with their respective IP addresses in the “Basic settings” and “Network address” sections, and clicked “Save & run service discovery”
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T56_4.png?raw=true"/>
    
5. After everything was scanned, I clicked “Changes” to activate the changes:
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T56_5.png?raw=true"/>
    
6. Then clicked “Activate on selected sites”
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T56_6.png?raw=true"/>
    
7. Lastly, verified the host were created by going to “Views” under the “Customize” tab, then clicked on “All hosts,” but nothing showed here. Decided to go back to “Hosts” and filtered results with “jl” for my servers
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T56_7.png?raw=true"/>
</details>

<details>
<summary> 57. Fix the issue on your Web Server </summary>

<code style="white-space: pre-wrap;">TASK: We have been receiving a lot of emails about your stage-web-jl-procore.prod1-IP. Verify and troubleshoot critical services using CheckMK.</code>

**STEPS TAKEN:**
    
1. Accessed checkmk site at http://10.1.XX.XX/procore/check_mk/ then I went to “Hosts” tab to search for `stage-web-jl` and I clicked on the “Host name” to view the server.
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T57_1.png?raw=true"/>
    
2. Next, I click on the “Host” tab and clicked on “Monitoring Status” first, but there was nothing shown in this area of concern.
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T57_2.png?raw=true"/>
    
3. Next, I clicked on “Host” again and selected “Rules,” which shown a list of several rules Checkmk was running. If I needed to update the Rules for notifications, I could alter them here.
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T57_3.png?raw=true"/>
    
4. Next, I clicked on “Host” and selected “Test notification” and I saw a section where the fallback email address needed to be added. This may be the issue since emails for rule based notifications will go to the admin; however, notifications not defined by the rules will not be sent out. Clicked on “fallback email address”
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T57_4.png?raw=true"/>
    
5.  Added my email address to the system:
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T57_5.png?raw=true"/>
    
6. My changes popped up and when I clicked on “Changes” I had to click on “Activate on selected sites” to implement them
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T57_6.png?raw=true"/>
    
7. Lastly, I went back to my “Host” to view stage-web-jl and I accepted all the the monitoring services. All of the services were okay except for NTP, which showed “CRIT”
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T57_7.png?raw=true"/>
    
8. I went back to my terminal to run the following commands to check if NTP was running properly: `sudo systemctl status chronyd` and everything appeared to be running correctly, but I decided to running `sudo systemctl enable --now chronyd` and then rescan checkmk.
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T57_8.png?raw=true"/>
    
9. When the scan was completed, I searched for NTP and it showed that everything was OK. What I learned from this is that checkmk allows me to visually see what issues I may have on my servers and that I can set rules to be alerted by email anytime something goes wrong on them. Also, I noticed that anytime I make a change on checkmk, I have to activate the changes. Decided to also remove my email address from the “Global Settings” since this is just a troubleshooting experiment.
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T57_9.png?raw=true"/>
</details>

<details>
<summary> 58. Create a systemd service for the script procored </summary>

<code style="white-space: pre-wrap;">TASK: Procore-Plus has deployed a new daemon that needs to be running on every server.</code>

**STEPS TAKEN:**
    
1. The first thing I did was access the `procored.sh` file via the nfs server and use the following command to copy the file to `/usr/bin` on each server: `sudo cp /nfs/incoming/scripts/procored.sh /usr/bin/procored` and confirmed the location of the file using `ll /usr/bin/procored`
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T58_1.png?raw=true"/>
    
2. I ran `sudo systemctl enable --now procored`, but it showed me the following:
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T58_2.png?raw=true"/>
    
3. I found this [Medium article](https://medium.com/@benmorel/creating-a-linux-service-with-systemd-611b5c8b91d6) on Google for how to create a Systemd service and what I needed to do was create a configuration/unit file under `/etc/systemd/system/procored.service`. From the article, I did not use `StartLimitIntervalSec=0` because I learned that it should only be used in containers.
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T58_3.png?raw=true"/>
    
4. Next, I ran `sudo systemctl daemon-reload` since I edited the `/etc/systemd/system/` directory and then ran `sudo systemctl enable --now procored` and `sudo systemctl status procored`:
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T58_4.png?raw=true"/>
</details>

<details>
<summary> 59. Configure an NFS Server </summary>

<code style="white-space: pre-wrap;">TASK: Please configure an NFS server on dev-app-jl.procore.prod1.</code>

**STEPS TAKEN:**
    
1. I created the directory for where the nfs server would operate from (dev-app-jl) by running `sudo mkdir -p /nfs-jlewis`, then I entered the directory and used `sudo wget` to download the rpm into my server:
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T59_1.png?raw=true"/>
    
2. Next, I found this walkthrough on Google explaining “[how to setup the server and client for NFS](https://www.netapp.com/learn/azure-anf-blg-linux-nfs-server-how-to-set-up-server-and-client/)” and that I needed to edit the export file with `sudo vim /etc/exports` and added the following `/nfs-jlewis stage-web-jl(rw,sync,no_root_squash)` 
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T59_2.png?raw=true"/>
    
    * `rw`: Allow read/write from client.
    * `sync`: Force synchronous writes (safer).
    * `no_root_squash`: Client root keeps root privileges on share.
3. Next, I reviewed the `man` page for `exportfs` and decided to run `exportfs -rav` to refreshe the NFS export table without restarting the service.
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T59_3.png?raw=true"/>
    
    * `-r`: Re-export all entries from /etc/exports to apply any changes.
    * `-a`: Applies to all directories and not just one.
    * `-v`: Verbose—shows what’s being exported.
4. I checked my firewall to make sure that the `nfs` service was allowed by running `sudo firewall-cmd --list-all`
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T59_4.png?raw=true"/>
    
5. Next, I accessed the client server (`stage-web-jl`) in order to run the following commands to create the mount point for the NFS server to mount and confirm: `sudo mkdir -p /nfs-jlewis`,  `sudo mount -t nfs dev-app-jl.procore.prod1:/nfs-jlewis /nfs-jlewis` and `df -hT`
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T59_5.png?raw=true"/>
    
6. Lastly, I wanted to permanently mount the server so I ran `sudo vim /etc/fstab` to update my file with the following:
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T59_6.png?raw=true"/>
    
7. After running `sudo systemctl daemon-reload` and `sudo mount -a`, everything successfully ran and on `stage-web-jl` I was able to access the /nfs-jlewis directory:
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T59_7.png?raw=true"/>
</details>

<details>
<summary> 60. Install and Configure Bacula </summary>

<code style="white-space: pre-wrap;">TASK: The infrastructure team needs to back up your VMs. Please install the Bacula Client (downgrade) and Libraries on both of your servers.</code>

**STEPS TAKEN:**
    
**Client Installation:**

1. Reviewed wiki for how to [Build Bacula client on CentOS 9]() and learned that I need to downgrade Bacula so I installed the required development tools and libraries by running the following on each server: `sudo dnf groupinstall "Development Tools" -y` and `sudo dnf install gcc gcc-c++ make cmake autoconf libtool openssl-devel readline-devel ncurses-devel zlib-devel lzo lzo-devel sqlite-devel libacl-devel -y`
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T60_1.png?raw=true"/>
    
2. Then I downloaded Bacula 9.6.6 source code by running the following commands: `curl -LO https://sourceforge.net/projects/bacula/files/bacula/9.6.6/bacula-9.6.6.tar.gz`, `tar -xvzf bacula-9.6.6.tar.gz`, and `cd bacula-9.6.6`
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T60_2.png?raw=true"/>
    
3. Then I configured the build for client only by running the following: `sudo ./configure --enable-client-only`
4. Next, I compiled and installed the Client using the following commands: `sudo make -j$(nproc)` and `sudo make install`
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T60_3.png?raw=true"/>
    
5. Then I had to rebuild the `bacula-fd` systemd Service by running the following commands: `sudo vim /etc/systemd/system/bacula-fd.service` after creating the following unit configuration file `bacula-fd.service` located at `/usr/lib/systemd/system`:
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T60_4.png?raw=true"/>
    
6. Lastly, for the client installation, I ran the following commands to enable and start the Bacula File Daemon: `sudo systemctl daemon-reexec`, `sudo systemctl daemon-reload`, `sudo systemctl start bacula-fd`, and `sudo systemctl enable --now bacula-fd` and realized that a symlink was created under `/etc/systemd/system/multi-user.target.wants/`:
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T60_5.png?raw=true"/>
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T60_6.png?raw=true"/>
    
**Client Configuration:**

1. I already added the IP address in `/etc/hosts` with `10.1.XX.XX prod-bacula.procore.prod1 prod-bacula` and I had run `sudo firewall-cmd --add-service=bacula-client --permanent`, `sudo firewall-cmd --add-port=9102/tcp --permanent`, and `sudo firewall-cmd --reload`, so the first thing I had to do was configure the bacula-fd and bconsole. I ran the following `sudo vim /etc/bacula/bacula-fd.conf` to edit the bacula-fd configuration file first with:
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T60_7.png?raw=true"/>
    
2. Next, I edited the bconsole configuration file using `sudo vi /etc/bacula/bconsole.conf` with the following:
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T60_8.png?raw=true"/>
    
3. After configuring these two files, I enabled and started the bacula-fd service with `sudo systemctl restart bacula-fd`. Then I access the following site [http://10.1.XX.XX:9095]() and used “admin” and Welcome2VITI” to login. After I clicked on “Clients” located on the sidebar tab in order to click “Add Client” and input the following information for each server respectively:
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T60_9.png?raw=true"/>
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T60_10.png?raw=true"/>
    
4. Next, I clicked on “Details” for each one in order to verify connectivity for each server by clicking on “Status Client.” My dev-performance-jl server was not working, but I realized that I did update the firewall to allow for bacula service and adding the 9102 port.
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T60_11.png?raw=true"/>
    
5. Next, I clicked on “Jobs” in the sidebar tabs in order to create a backup job. The first thing I had to do was click “New job wizard” and input the following information for each step, until I was able to click “Create job:”
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T60_12.png?raw=true"/>
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T60_13.png?raw=true"/>
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T60_14.png?raw=true"/>
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T60_15.png?raw=true"/>
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T60_16.png?raw=true"/>
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T60_17.png?raw=true"/>
    
6. Next, on the “Jobs” tab I clicked on “Run Job” and entered the following information:
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T60_18.png?raw=true"/>
    
7. Verified that the backup ran for each server. I reviewed the screenshots and thought I did it incorrectly because it showed File2 on one of the screenshots and I reran many of my machines thinking I had to do it this way, but ultimately realized that backing up to File1 was in line with the initial setup.
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T60_19.png?raw=true"/>
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T60_20.png?raw=true"/>
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T60_21.png?raw=true"/>
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T60_22.png?raw=true"/>
</details>

<details>
<summary> 61. Run Performance script </summary>

<code style="white-space: pre-wrap;">TASK: The development team has notified all users to manually run a performance script on all servers. Please execute the script located at /nfs/incoming/scripts/perfomance.sh as the root user. After running the script, a file named /setup_file.cfg should be created.</code>

**STEPS TAKEN:**
    
1. Created a snapshot on each VM just in case prior to starting this ticket.
2. Accessed `/nfs/incoming/scripts/` to run `sudo ./perfomance.sh` script on each VM and the file `setup_file.cfg` was created on each VM (someone must have changed the name accidentally, so I used `sudo mv perfomance.sh performance.sh`):
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T61_1.png?raw=true"/>
</details>

<details>
<summary> 62. Issues with the Performance script </summary>

<code style="white-space: pre-wrap;">TASK: After running the performance script, the development team noticed some issues with the NFS and HTTPD services. Most of the files for these services were deleted. Please restore these files from the backup you created earlier using Bacula.</code>

**STEPS TAKEN:**
    
1. Visited http://10.1.XX.XX:9095/. Tried to use “Restore wizard;” however, it was not working properly, so I accessed the “Jobs” tab to click on “Details”
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T62_1.png?raw=true"/>
    
2. Then, I clicked on “Job history” and selected the “Full” backup to be able to click “Details”
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T62_2.png?raw=true"/>
    
3. On this screen, I clicked on “Restore”
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T62_3.png?raw=true"/>
    
4. Once the Restore window popped up, I clicked on the “Folder” icon, the the “etc” folder icon. Then I clicked “Add” for both of the files shown, then clicked “Next:”
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T62_4.png?raw=true"/>
    
5. For the “Where” step, I did not change anything here:
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T62_5.png?raw=true"/>
    
6. For the “Options” step, I did not change anything here either
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T62_6.png?raw=true"/>
    
7. On the “Run” step, I simply clicked “Run restore”
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T62_7.png?raw=true"/>
    
8. After the job ran, it produced the following messages saying that the restore job did not run properly; however, the files were added to `/tmp/restore` under `/etc`:
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T62_8.png?raw=true"/>
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T62_9.png?raw=true"/>
    
9. Since the files were moved to the /tmp/restore directorey, I decided to move them into the /etc directory using the `mv` command. Used `sudo mv exports /etc/` and used `sudo mv httpd/ /etc/httpd.bak`:
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T62_10.png?raw=true"/>
    
10. Checked the status of httpd and nfs with the following commands: `sudo systemctl status httpd` and `sudo systemctl status nfs-server`
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T62_11.png?raw=true"/>
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T62_12.png?raw=true"/>
</details>

<details>
<summary> 63. Deploy WordPress Docker Containers </summary>

<code style="white-space: pre-wrap;">TASK: The Public Relations department wants to deploy a WordPress website. Please follow the instructions at the URL below to complete this request.</code>

**STEPS TAKEN:**
    
1. I reviewed the “[Wordpress Docker Image](https://hub.docker.com/_/wordpress)” site and ran the container image command: `docker run --name some-wordpress --network some-network -d wordpress` and I was asked to select an image, so I selected `docker.io/library/wordpress:latest`:
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T63_1.png?raw=true"/>
    
2. When the container finished running, I received the following error:
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T63_2.png?raw=true"/>
    
3. Decided to run the next image container `docker run --name some-wordpress -p 8080:80 -d wordpress` and I was asked to select an image, so I selected `docker.io/library/wordpress:latest` again:
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T63_3.png?raw=true"/>
    
4. I got the same error shown in step 2 so I ran the command `sudo podman system migrate` and reran image container command for ports and it ran successfully:
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T63_4.png?raw=true"/>
    
5. Decided to try to access 10.1.XX.XX:8080 and it was redirected to http://10.1.XX.XX:8080/wp-admin/setup-config.php showing that Wordpress was configured:
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T63_5.png?raw=true"/>
</details>

<details>
<summary> 64. Dev-performance Web server is not responding </summary>

<code style="white-space: pre-wrap;">TASK: Some end users are reporting connectivity issues with the internal dev-performance system. Please troubleshoot the issue.</code>

**STEPS TAKEN:**
    
1. The first thing I did was check if the network connection was active by running `nmcli c s` and then I used `ping -c4 google.com`
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T64_1.png?raw=true"/>
    
2. Next, I checked the status of NetworkManager by running the following `sudo systemctl status NetworkManager`, which showed that the service was running and active:
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T64_2.png?raw=true"/>
    
3. Next, I decided to run `ss -tuln | grep :80` and `ss -tuln | grep :443` which showed that HTTPS does not appear to be working:
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T64_3.png?raw=true"/>
    
4. Decided to check `/etc/httpd/conf` and there was no `httpd.conf` file, which may have been a result of running the script recently for everyone. From the backup restoration, I used the following command to add the `httpd.conf` file to the correct location: `sudo cp httpd.conf /etc/httpd/conf/` and ran `sudo vim /etc/httpd/conf/httpd.conf` to added `Listen 443`
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T64_4.png?raw=true"/>
    
5. Then ran `sudo systemctl restart httpd`, `ss -tuln | grep :443` and `curl -k https://localhost`, which showed that the SSL conf file may need to be updated as well, but this is beyond my current knowledge. I believe I would need to create an SSL certificate to resolve this because curl -k http://localhost shows the html code:
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T64_5.png?raw=true"/>
</details>

<details>
<summary> 65. CPU Utilization issue with service </summary>

<code style="white-space: pre-wrap;">TASK: Please stop and disable the procored system service on all servers. Afterward, verify that CPU utilization is normal using Check_MK.</code>

**STEPS TAKEN:**
    
1. On each server, I ran the following commands: `sudo systemctl stop procored`, `sudo systemctl disable procored`, and `sudo systemctl status procored` to confirm that the service was no longer running:
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T65_1.png?raw=true"/>
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T65_2.png?raw=true"/>
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T65_3.png?raw=true"/>
    
2. Next, I visited Check_MK and clicked on “Setup” and selected “Hosts” in order to view my VMs under /Dev and saw that my CPU utilization was only about 5.06%
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T65_4.png?raw=true"/>
</details>

<details>
<summary> 66. Notify that Procore Products website is under maintenance </summary>

<code style="white-space: pre-wrap;">TASK: The webmaster would like you to add a banner indicating that the website will be down for maintenance.</code>

**STEPS TAKEN:**
    
1. Used cd /var/www/html to access location to clone repository and then ran `sudo git clone git@gitlab.com:procoreplusmd/procore-products.git` , which produced the following error:
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T66_1.png?raw=true"/>
    
2. Decided to run `git init` and then `sudo git clone` on the required repository:
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T66_2.png?raw=true"/>
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T66_3.png?raw=true"/>
    
3. When I ran `git status`, I was instructed to run `git config --global --add safe.directory /var/www/html`, then git status showed me the following:
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T66_4.png?raw=true"/>
    
4. Next, I used `sudo vim /etc/httpd/conf.d/welcome.conf` to comment out all of the lines so that the default CentOS message did not display and I ran `sudo systemctl restart httpd` to apply the changes:
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T66_5.png?raw=true"/>
    
5. When I ran `ll -a` on `/var/www/html` it did not show any contents, so I decided to use `rm -rf .git/` to remove the hidden directory and then I decided to run `git clone` on the repository link instead of `git@`:
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T66_6.png?raw=true"/>
    
6. Next, I decided to use `sudo cp index.html /var/www/html/` and this allowed me to see the web contents when I access http://10.1.XX.XX:
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T66_7.png?raw=true"/>
    
7. Next, I accessed `/var/www/html/procore-products/websiteDownForMaintenance` to use `sudo cp index.html /var/www/html/` in order to apply contents banner for Website maintenance:
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T66_8.png?raw=true"/>
    
8. I believe the website may not be showing all of the content correctly because it matters where the files are located; however, I have shown that I know how to pull the index.html files to display them based on the status of the site. Let me know if there is anything else that needs to be done.
9. Decided to move the contents of `/var/www/html/procore-products/procore` by using `sudo cp -r /var/www/html/procore-products/procore/* /var/www/html` and then ran `sudo cp /var/www/html/procore-products/websiteDownForMaintenance/index.html /var/www/html/`
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T66_9.png?raw=true"/>
</details>

<details>
<summary> 67. Modify User Account Profile Picture </summary>

<code style="white-space: pre-wrap;">TASK: Please modify the profile picture for user Jessica on the website. Use the following files to update her information.</code>

**STEPS TAKEN:**
    
1. Under notification list, observered photo for Jessica was `notification-01.jpg` by right clicking on her photo and using the “Inspect” tool provided by Google:
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T67_1.png?raw=true"/>
    
2. Assessed GitLab and noticed that Jessica’s updated photo was labeled `notification-dog.img`
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T67_2.png?raw=true"/>
    
3. Accessed folder with new picture label `notification-dog.img` under `/var/www/html/procore-products/notificationPhotoChange`. Used `sudo cp notification-dog.img /var/www/html/img/notification-01.jpg`:
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T67_3.png?raw=true"/>
</details>

<details>
<summary> 68. Update Performance chart on Procore Products Website </summary>

<code style="white-space: pre-wrap;">TASK: The website requires a new feature to be added to the performance chart.</code>

**STEPS TAKEN:**
    
1. Took a snapshot of the performance chart prior to completing any changes to ensure I could restore it if need be: 
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T68_1.png?raw=true"/>
    
2. Accessed `/var/www/html/js` and confirmed location of file to be replaced, then accessed `/var/www/html/procore-products/addPinkBarToPerformanceChart` to use `sudo cp tooplate-scripts-orig.js /var/www/html/js/tooplate-scripts.js`
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T68_1.png?raw=true"/>
</details>

<details>
<summary> 69. Update Order List on the Procore Products Website </summary>

<code style="white-space: pre-wrap;">TASK: Please update the Order List table on the Procore Products website to ensure that all cancelled orders are removed.</code>

**STEPS TAKEN:**
    
1. Took a screenshot of what the order list looks like to show the change:
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T69_1.png?raw=true"/>
    
2. Accessed `/var/www/html/procore-products/removeCancelledProducts` and noticed that the only file is the `index.html` file, so used `sudo cp index.html /var/www/html/`:
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T69_1.png?raw=true"/>
</details>

<details>
<summary> 70. Remove Maintenance Banner </summary>

<code style="white-space: pre-wrap;">TASK: Now that all issues on the dev-performance server have been resolved, please remove the maintenance banner that was added.</code>

**STEPS TAKEN:**
    
1. Took a screenshot of what the site looked like prior to making changes
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T70_1.png?raw=true"/>
    
2. Accessed `/var/www/html/procore-products/websiteUpAndReady` then used `sudo cp index.html /var/www/html/`
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T70_2.png?raw=true"/>
</details>

<details>
<summary> 71. Install Terraform on your Virtual Machine </summary>

<code style="white-space: pre-wrap;">TASK: Please install terraform on your dev-app-jl.procore.prod1 VM.</code>

**STEPS TAKEN:**
    
1. Read wiki for “[How to Install Terraform]()” and the first thing I needed to do was determine what is the latest version for Terraform by visiting: https://developer.hashicorp.com/terraform/install and decided to install ARM64 Version: 1.13.4
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T71_1.png?raw=true"/>
    
2. Ran the following command to download Terraform: `sudo wget https://releases.hashicorp.com/terraform/1.13.4/terraform_1.13.4_linux_arm64.zip`
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T71_2.png?raw=true"/>
    
3. Next, I used the following command to unzip the installer: `sudo unzip terraform_1.13.4_linux_arm64.zip` and confirmed it was installed, then used `sudo mv terraform /usr/bin`: 
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T71_3.png?raw=true"/>
    
4. When I ran, `terraform -v` it showed the following error: 
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T71_4.png?raw=true"/>
    
5. Decided to run `sudo dnf install -y yum-utils`, `sudo yum-config-manager --add-repo https://rpm.releases.hashicorp.com/RHEL/hashicorp.repo`, and `sudo dnf -y install terraform` shown on the Terraform site and when I ran `terraform -v`, it worked successfully:
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T71_5.png?raw=true"/>
    
6. On vSphere, I right clicked on my `dev-performance-jl` server to select “Clone VM to Template” and input the following information before clicking “Finish”
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T71_6.png?raw=true"/>
    
7. Confirmed template was created by right clicking on Cluster and selecting “New VM” and chose “Deploy from Template”
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T71_7.png?raw=true"/>
</details>

<details>
<summary> 72. Deploy Production Web Server from Template </summary>

<code style="white-space: pre-wrap;">TASK: Please use Terraform code to deploy the newly fixed web server into production. The server should be created within your vSphere resource pool.</code>

**STEPS TAKEN:**
    
1. Used `sudo mkdir terraform && cd terraform` to create a directory on `dev-app-jl` to perform tasks, then ran `git init` and `sudo git clone https://gitlab.com/procoreplusmd/terraform.git`:
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T72_1.png?raw=true"/>
    
2. Cleaned up directory by running `sudo cp -r /home/jlewis/terraform/terraform/* ~/terraform/`, `sudo rm -rf terraform/*`, and `sudo rm -rd terraform/`
3. Then ran `sudo vim terraform.tfvars` to edit the config file with the following information:
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T72_2.png?raw=true"/>
    
4. Next, I updated the `main.tf` file with my hostname `prod-webserver-jl.procore.prod1`:
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T72_3.png?raw=true"/>
    
5. Then I ran `sudo terraform init`:
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T72_4.png?raw=true"/>
    
6. When I ran `sudo terraform plan`, my resource pool was not found and I believe it is due to case-sensitivity:
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T72_5.png?raw=true"/>
    
7. Updated `sudo vim terraform.tfvars` and reran `sudo terraform plan`
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T72_6.png?raw=true"/>
    
8. When I ran `sudo terraform apply` and entered “yes” to perform the actions, I received the following error:
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T72_7.png?raw=true"/>
    
9. I am not sure why this message popped up other than the fact that I am not allowed to delete VMs; however, the VM was created, and I was able to log into it:
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T72_8.png?raw=true"/>
</details>

<details>
<summary> 73. Install PHP </summary>

<code style="white-space: pre-wrap;">TASK: The web development team requests that PHP be installed on stage-web-jl.procore.prod1-IP.</code>

**STEPS TAKEN:**
    
1. Ran `sudo dnf info php`
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T73_1.png?raw=true"/>
    
2. Then `sudo dnf install php` to install php and all dependencies:
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T73_2.png?raw=true"/>
</details>

<details>
<summary> 74. Install a LAMP stack application </summary>

<code style="white-space: pre-wrap;">TASK: The development team has released a new application, and you have been assigned the task of deploying it and configuring the associated database. Strengthen Linux system administrator expertise through server deployments using LAMP stack.</code>

**STEPS TAKEN:**
    
1. Used `sudo git clone https://gitlab.com/procoreplusmd/crm-project` 
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T74_1.png?raw=true"/>
    
2. Next, I ran `sudo unzip Small_CRM_Projects.zip` to extract the file contents and then I ran `sudo cp -r crm-project/ /var/www/html`
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T74_2.png?raw=true"/>
    
3. Tried to access http://localhost/phpmyadmin; however, there was no connection so I decided to follow the steps on the wiki on how to setup [LAMP stack and phpMyAdmin]() by installing EPEL repository first by running `sudo dnf -y install epel-release`, but it was already installed.

4. Next, I proceeded to install MariaDB by running `sudo dnf -y install mariadb-server mariadb`, then running `sudo systemctl enable --now mariadb` to enable and start the MariaDB service, and running `sudo mysql_secure_installation` to secure the installation:
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T74_3.png?raw=true"/>
    
5. Next, I installed Apache `sudo dnf -y install httpd`, enabled and started the service using `sudo systemctl enable --now httpd`; however, the service could not start since the `httpd.conf` file got deleted by the script.
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T74_4.png?raw=true"/>
    
6. Decided to run `sudo rsync -avs --delete jlewis@dev-perf-jl:/etc/httpd/conf/httpd.conf /etc/httpd/conf/`
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T74_5.png?raw=true"/>
    
7. I reran the `sudo systemctl restart httpd && sudo systemctl status httpd` to confirm service was running. Then I opened the required firewall ports by using `sudo firewall-cmd --permanent --zone=public --add-service={http,https}`, and finally reloaded the firewall using `sudo firewall-cmd --reload` and confirmed access to site was available:
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T74_6.png?raw=true"/>
    
8. Next, I installed PHP and the required utilities with opcache by running `sudo dnf -y install yum-utils php php-opcache && sudo dnf update -y` and I restarted Apache to load the PHP modules: `sudo systemctl restart httpd`

9. The next step was to test the PHP functionality by creating an info page by running: `sudo vi /var/www/html/info.php` and I add the following content:
    
    ```
    <?php
    phpinfo();
    ```
    
    - Then, I visited http://10.1.XX.XX/info.php in my browser to confirm PHP was running.
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T74_7.png?raw=true"/>
    
10. Next, I added **MySQL Support and Common PHP Modules** by installing the necessary PHP modules for database and CMS compatibility by running `sudo dnf -y install php-mysqlnd php-pdo php-gd php-ldap php-odbc php-pear php-xml php-xmlrpc php-mbstring php-soap curl curl-devel` ; however, `php-xmlrpc` was not found so I removed it:
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T74_8.png?raw=true"/>
    
11. Re-ran `sudo dnf -y install php-mysqlnd php-pdo php-gd php-ldap php-odbc php-pear php-xml php-mbstring php-soap curl curl-devel` and restarted Apache again `sudo systemctl restart httpd`
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T74_9.png?raw=true"/>
    
    - And revisited [info.php](http://10.1.XX.XX/info.php) to verify module installation:
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T74_10.png?raw=true"/>
    
12. Lastly, I was directed to install and configure phpMyAdmin by running `sudo dnf -y install phpMyAdmin`
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T74_11.png?raw=true"/>
    
    - Then I edited Apache’s configuration to allow remote access with `sudo vi /etc/httpd/conf.d/phpMyAdmin.conf` and modified the directory section to include:
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T74_12.png?raw=true"/>
    
    - Then I restarted Apache: `sudo systemctl restart httpd.service`
    - Access phpMyAdmin at: http://10.1.XX.XX/phpmyadmin/ and entered my username and password; however, it did not work
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T74_13.png?raw=true"/>
    
13. Realized that I needed to edit the dbconnection.php files by adding my password with `sudo vim /var/www/html/crm/dbconnection.php` and `sudo vim /var/www/html/crm/admin/dbconnection.php`

14. Then I ran the script http://10.1.XX.XX/crm/admin and entered the credentials
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T74_14.png?raw=true"/>
    
15. Then I ran the script http://10.1.XX.XX/crm (frontend) and created my own regular user by clicking the Sign Up link. Attempted to access site with my credentials, but it still was not working. This is when I realized I did not create the database on phpMyAdmin. Added `crm` database and ran the following to import the file to the phpMyAdmin `mysql -u root -p crm < /var/www/html/crm/crm.sql`

16. I tried my credentials; however, they did not work so I recreated my account:
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T74_15.png?raw=true"/>
    
17. After entering my credentials again, I was able to assess the site:
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T74_16.png?raw=true"/>
</details>

<details>
<summary> 75. Create a WIKI page for Documentation Purposes </summary>

<code style="white-space: pre-wrap;">TASK: Please create a wiki document outlining the steps to install and configure a firewall for an HTTP server. Name the page using your username and place it in the Procore-Plus How-To Guides section.</code>

**STEPS TAKEN:**
    
1. Created an account  on the website and entered my information:
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T75_1.png?raw=true"/>
    
2. Visited the Procore-Plus Wiki and clicked “Edit” tab
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T75_2.png?raw=true"/>
    
3. Populated my information on the Editing page:
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T75_3.png?raw=true"/>
    
4. Next, I accessed my link on “JLewis” and added the following content
    
    ```basic
    1. Install Apache (httpd)
    <pre>
    Run Command:
    $ sudo dnf install -y httpd
    </pre>
    2. Start and enable Apache (httpd)
    <pre>
    Start the service:
    $ sudo systemctl enable --now httpd
    </pre>
    3. Check Apache (httpd) status:
    <pre>
    $ sudo systemctl status httpd
    </pre>
    4. Configure firewall to allow web traffic through ports 80 and 443
    <pre>
    Allow http (port 80)
    $ sudo firewall-cmd --add-service=http --permanent
    Allow https (port 443)
    $ sudo firewall-cmd --add-service=https --permanent
    Reload firewall:
    $ sudo firewall-cmd --reload
    </pre>
    5. Verify if Apache is working
    <pre>
    Open a web browser and test the webpage:
    [http://your-server-ip](http://your-server-ip/) or [http://your-server-ip:80](http://your-server-ip/)
    You should see an Apache test page
    </pre>
    ```
    
5. Confirmed changes were shown on my created Wiki link

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T75_4.png?raw=true"/>
</details>

<details>
<summary> 76. Perform a Security Audit on a Linux system using Lynis </summary>

<code style="white-space: pre-wrap;">TASK: The security team has notified all administrators to conduct an audit and scan for security vulnerabilities and loopholes on your Linux machine using the Lynis tool.</code>

**STEPS TAKEN:**
    
1. Ran `sudo dnf provides lynis` and it confirmed which packaged I needed to install so I ran `sudo dnf install lynis`:
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T76_1.png?raw=true"/>
    
2. Then ran `man lynis` which prompted that on the first time usage to run `lynis audit system`, which is the most common audit so I ran the command with the following: `sudo lynis audit system >> /tmp/systemaudit`
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T76_2.png?raw=true"/>
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T76_3.png?raw=true"/>
</details>

<details>
<summary> 77. Create a Python script </summary>

<code style="white-space: pre-wrap;">TASK: The security team requires that administrators create a Python script to gather information about the VM they are working on. The script should display the following information:
      a. Hostname
      b. IP address
      c. OS System
      d. Release of OS
      e. Version of OS
      f. Machine architecture</code>

**STEPS TAKEN:**
    
1. Reviewed the following playlist https://www.youtube.com/playlist?list=PLT98CRl2KxKGIazPd2nQEPbG7sQpT8LEj to learn Python basics. Ran `python -V`, which showed I had `Python 3.9.23`, (under the `python3` package)

2. On my dev-app server, I ran `sudo vim python.sh` to add the following content:
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T77_1.png?raw=true"/>
    
3. Next, I ran `sudo chmod u+x python.sh` to enable the file to be run by using `sudo ./python.sh >> /tmp/pythoninfo`
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T77_2.png?raw=true"/>
</details>

<details>
<summary> 78-83. Project : Managing Active directory </summary>
    
<code style="white-space: pre-wrap;">TASK: Accessing the Windows Active Directory server to manage and administer user accounts.</code>
</details>

<details>
<summary> 79. Access Active Directory Services </summary>

<code style="white-space: pre-wrap;">OBJECTIVE: Enhance system administration skills through identity management using Active Directory.
    - Use the Remote Desktop Client to connect to Active Directory services.</code>

**STEPS TAKEN:**
    
1. Accessed Microsoft Remote Desktop on iMac and clicked on “Add PC”
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T79_1.png?raw=true"/>
    
2. Input the Server and User information in as directed on the wiki:
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T79_2.png?raw=true"/>
</details>

<details>
<summary> 80. Create a New Organization Unit </summary>

<code style="white-space: pre-wrap;">OBJECTIVE: Enhance system administration skills through identity management using Active Directory.
    - To add a new Organizational Unit (OU) under the domain, utilize the Active Directory Users and Computers tool.
    - OU (Organization Unit) should be created under the already created OU Name (VITI) with your {freeipa_username} –VITI</code>

**STEPS TAKEN:**
1. Right clicked on VITI folder under “sandbox.prod → Yellow tail” to select “New—>Organizational Unit,” named it “JLewis-VITI,” and unchecked “Protective Container” option
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T80_1.png?raw=true"/>
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T80_2.png?raw=true"/>
</details>

<details>
<summary> 81. Create a new user </summary>

<code style="white-space: pre-wrap;">OBJECTIVE: Enhance system administration skills through identity management using Active Directory.</code>

**STEPS TAKEN:**
    
1. Right clicked on OU, then selected “New” and  “User”
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T81_1.png?raw=true"/>
    
2. Entered information for user and clicked “Next:”
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T81_2.png?raw=true"/>
    
3. Selected option for “password never expire” and entered password given.
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T81_3.png?raw=true"/>
    
4. Clicked “Finish”
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T81_4.png?raw=true"/>
</details>

<details>
<summary> 82. Create a new user group </summary>

<code style="white-space: pre-wrap;">OBJECTIVE: Enhance system administration skills through identity management using Active Directory.</code>

**STEPS TAKEN:**
    
1. Right clicked on Organizational Unit (OU), then selected “New” and  “Group”
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T82_1.png?raw=true"/>
    
2. Entered group name and made sure “Global” and “Security” were selected
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T82_2.png?raw=true"/>
    
3. Right clicked on user “Mike Tyson” and selected “Add to a group…”
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T82_3.png?raw=true"/>
    
4. Entered group name and clicked “OK”
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T82_4.png?raw=true"/>
</details>

<details>
<summary> 83. Research and create documentation </summary>

<code style="white-space: pre-wrap;">OBJECTIVE: Research and create a document explaining what an Active Directory Domain is and the steps to join a Windows 10 device to it.</code>

**STEPS TAKEN:**
    
1. Googled “What is an active directory domain” and found the following from Microsoft: https://learn.microsoft.com/en-us/windows-server/identity/ad-ds/get-started/virtual-dc/active-directory-domain-services-overview
2. An Active Diretory Domain is a directory on a network that allows for information about users to be stored for access across the network based on the permissions assigned to each user. Users can be added to groups and permissions can be assigned either individually or collectively. Just as users/groups can be added, they can be removed to preserve the current structure of any organization.
3. Googled “How to join a windows 10 device to active directory domain” and found the following from Microsoft: https://learn.microsoft.com/en-us/windows-server/identity/ad-ds/manage/join-computer-to-domain?tabs=cmd&pivots=windows-client-10. There were several different options, but I selected Windows 10 and it listed out several methods such as Control Panel Method, Settings App Method, and Command Line Method. I did not believe it was necessary to list the steps here because they are clearly shown on the site provided above.
</details>

<details>
<summary> 84. Vulnerability Scanning with OpenVAS </summary>

<code style="white-space: pre-wrap;">TASK: Scan a Linux System with Open VAS and generate an auto report of all the vulnerabilities found on the system.</code>

**STEPS TAKEN:**
    
1. Searched Procore Wiki and found “[Scanning Linux Systems with OpenVAS]()” which stated that I needed to run the following command to open the firewall on my development servers: `sudo firewall-cmd --permanent --add-source=10.1.XX.XX` and `sudo firewall-cmd --reload`
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T84_1.png?raw=true"/>
    
2. To access the console, I visited https://10.1.XX.XX/ and used the login credentials provided
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T84_2.png?raw=true"/>
    
3. Next, I created new credentials by hovering over the “Configuration” tab and clicking on “Credentials” then clicking “New Credential.” I entered my information and then clicked “Save”
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T84_3.png?raw=true"/>
    
4. Next, I had to create a target by hovering over “Configuration,” clicking on “Target,” and then clicking on “New Target.” I entered my information and then clicked “Save”
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T84_4.png?raw=true"/>
    
5. In order to execute a vulnerability scan against the development servers, I then had to create a scan task by hovering over “Scans,” clicking “Tasks” and then clicking on “New Task” to enter my information and click “Save”
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T84_5.png?raw=true"/>
    
6. Lastly, I clicked the “Start” button to run the scan
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T84_6.png?raw=true"/>
    
7. After scan was finished, I hovered over “Scans,” clicked on “Reports,” then I clicked on the date that my report ran to be able to click the “Download” button, and finaly clicked “OK”
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T84_7.png?raw=true"/>
    
8. Please find the scan results below:
(OpenVAS-Rescan-Validation.pdf)
</details>

<details>
<summary> 85. Fix the high Vulnerabilities showing in the report </summary>

<code style="white-space: pre-wrap;">TASK: This ticket documents the remediation and subsequent validation of vulnerabilities reported in the initial OpenVAS scan. As part of compliance requirements, provide a clean re-scan as evidence.</code>

**STEPS TAKEN:**
    
1. Reviewed the scan report. For Host Authentications, I was going to add a rich rule to the firewall, but then I rememebered to check the `/etc/ssh/sshd_config file` and changed `PermitRootLogin` to “yes.” This should permit root login and result in a “Success”
2. Next, I could not perform the next request because I am not in control of the version of OpenVAS installed, but if I was I would have updated version 22.4.1 to 23.0.1. Instead, I ran `sudo dnf update` to update all of the packages to ensure they were correct and not outdated to address a portion of 2.1.1 High general/tcp threats:
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T85_1.png?raw=true"/>
    
3. For 2.1.2 Medium 8080/tcp, I ran `sudo podman system migrate` and it stopped my container from running, which should address this error because the configuration is removed and not public anymore:
    
    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T85_2.png?raw=true"/>
    
4. For 2.1.3 Medium 21/tcp, I ran `man ftp` to review the manual in order to set to FTPS; however, there was nothing in the documentation. Instead, I decided to review the configuration file `/etc/vsftpd/vsftpd.conf` since `vsftpd` if used a a very sercure FTP Daemon. There were some lines that I added previously that I believe did not allow the service to run properly, so I commented them out and after running `sudo systemctl status vsftpd` it showed that the service was running properly again; however, after further thought, I decided to simply remove the `ftp` service from the firewall by running `sudo firewall-cmd --remove-service=ftp`
5. For 2.1.4 Low general/icmp, I had to disable the ICMP timestamp reponses by editing the `/etc/sysctl.conf` and adding the following to make it persistent: `net.ipv4.icmp_echo_ignore_all = 1`; however, this did not work, even after running `sudo sysctl -p`. I had to run the following commands to edit the firewall: `sudo firewall-cmd --permanent --add-rich-rule='rule family="ipv4" icmp-type name="timestamp-reply" drop’` and `sudo firewall-cmd --reload`
6. For 2.1.5 Low general/tcp, I had to add the following line `net.ipv4.tcp_timestamps = 0` to `/etc/sysctl.conf` and then run `sudo sysctl -p` to apply the changes.
7. Decided to reboot the VM and then ran scan again to see if all vulnerabilities were addressed and there were:(OpenVAS-Rescan-Validation-2025-11-17.pdf).
</details>