# sysadmin-ticket-log

[![Home Button](https://img.shields.io/badge/➤_Go_Back_Home-darkred?style=for-the-badge&logo=)](https://github.com/justintimejlew#home-button)

> Note: Please ignore red font used on tickets 1-48. Some information has been redacted for security purposes.

---

## 📋 Table of Contents

| # | Ticket Title |
|---|---|
| 1 | [Deploy a new CentOS 9 Virtual Machine on Vsphere](#1-deploy-a-new-centos-9-virtual-machine-on-vsphere) |
| 2 | [Create your own resource pool on VSphere](#2-create-your-own-resource-pool-on-vsphere) |
| 3 | [Migrate your deployed VM to your Resource Pool](#3-migrate-your-deployed-vm-to-your-resource-pool) |
| 4 | [Network setup request](#4-network-setup-request) |
| 5 | [Install and Configure FreeIPA client](#5-install-and-configure-freeipa-client) |
| 6 | [Add user msoriano to FreeIPA](#6-add-user-msoriano-to-freeipa) |
| 7 | [Add user to group using FreeIPA](#7-add-user-to-group-using-freeipa) |
| 8 | [Add the following info to the local DNS file](#8-add-the-following-info-to-the-local-dns-file) |
| 9 | [Create the Following Mount points](#9-create-the-following-mount-points) |
| 10 | [Please mount the following NFS shares permanently](#10-please-mount-the-following-nfs-shares-permanently) |
| 11 | [NFS home directory](#11-nfs-home-directory) |
| 12 | [Please deploy a dev webserver using configuration Template](#12-please-deploy-a-dev-webserver-using-configuration-template) |
| 13 | [Allow HTTP to use non-standard ports](#13-allow-http-to-use-non-standard-ports) |
| 14 | [Configure a repository](#14-configure-a-repository) |
| 15 | [Create and Copy your SSH key](#15-create-and-copy-your-ssh-key) |
| 16 | [Add Dev Servers into Ansible inventory](#16-add-dev-servers-into-ansible-inventory) |
| 17 | [Patch your Dev Servers using Ansible](#17-patch-your-dev-servers-using-ansible) |
| 18 | [Please use Ansible to create the task below](#18-please-use-ansible-to-create-the-task-below) |
| 19 | [Please update the system inventory database](#19-please-update-the-system-inventory-database) |
| 20 | [Push the script to gitlab repo](#20-push-the-script-to-gitlab-repo) |
| 21 | [Spin up a Web server using a Kickstart file](#21-spin-up-a-web-server-using-a-kickstart-file) |
| 22 | [Configure FreeIPA Client on the Stage Virtual Machine](#22-configure-freeipa-client-on-the-stage-virtual-machine) |
| 23 | [Disable and prevent SSH root user access to all your servers](#23-disable-and-prevent-ssh-root-user-access-to-all-your-servers-as-part-of-the-security-audit-requirement) |
| 24 | [Restrict SSH access on all servers except Bastion Host (Rich Rule)](#24-restrict-ssh-access-on-all-servers-except-bastion-host-rich-rule) |
| 25 | [Graylog client](#25-graylog-client) |
| 26 | [Install Apache Web Server](#26-install-apache-web-server) |
| 27 | [Allow apache to the firewall](#27-allow-apache-to-the-firewall) |
| 28 | [Configure apache web content](#28-configure-apache-web-content) |
| 29 | [Update web content for ariclaw](#29-update-web-content-for-ariclaw) |
| 30 | [Install MariaDB](#30-install-mariadb) |
| 31 | [Create a snapshot of your VM](#31-create-a-snapshot-of-your-vm) |
| 32 | [Register your VMs to Foreman](#32-register-your-vms-to-foreman) |
| 33 | [Run remote command from Foreman](#33-run-remote-command-from-foreman) |
| 34 | [Create a central location for logs](#34-create-a-central-location-for-logs) |
| 35 | [Users are having issues with SSH](#35-users-are-having-issues-with-ssh) |
| 36 | [Users are reporting repo issues](#36-users-are-reporting-repo-issues) |
| 37 | [User is having issue in accessing file](#37-user-is-having-issue-in-accessing-file) |
| 38 | [Urgent! Malicious IP](#38-urgent-malicious-ip) |
| 39 | [Please provide the apache version](#39-please-provide-the-apache-version) |
| 40 | [Get a list of all the users that have enrolled on FreeIPA](#40-get-a-list-of-all-the-users-that-have-enrolled-on-freeipa) |
| 41 | [Please configure cronjob](#41-please-configure-cronjob) |
| 42 | [Please create a cronjob](#42-please-create-a-cronjob) |
| 43 | [Create NAGIOS user and configure access](#43-create-nagios-user-and-configure-access) |
| 44 | [Add the servers to Nagios](#44-add-the-servers-to-nagios) |
| 45 | [Configure FTP Server and Client](#45-configure-ftp-server-and-client) |
| 46 | [Create tasks using Ansible Playbook](#46-create-tasks-using-ansible-playbook) |
| 47 | [Closing these ports via an ansible playbook](#47-closing-these-ports-via-an-ansible-playbook) |
| 48 | [Please create backups for your server kernel](#48-please-create-backups-for-your-server-kernel) |
| 49 | [Create a Symlink](#49-create-a-symlink) |
| 50 | [Provide log information from Graylog](#50-provide-log-information-from-graylog) |
| 51 | [RAM upgrade request](#51-ram-upgrade-request) |
| 52 | [Storage request](#52-storage-request) |
| 53 | [Create a script to gather these info below](#53-create-a-script-to-gather-these-info-below) |
| 54 | [Create your own GitLab repository](#54-create-your-own-gitlab-repository) |
| 55 | [Please rotate HTTPD logs](#55-please-rotate-httpd-logs) |
| 56 | [Add both of your servers to CheckMK](#56-add-both-of-your-servers-to-checkmk) |
| 57 | [Fix the issue on your Web Server](#57-fix-the-issue-on-your-web-server) |
| 58 | [Create a systemd service for the script procored](#58-create-a-systemd-service-for-the-script-procored) |
| 59 | [Configure an NFS Server](#59-configure-an-nfs-server) |
| 60 | [Install and Configure Bacula](#60-install-and-configure-bacula) |
| 61 | [Run Performance script](#61-run-performance-script) |
| 62 | [Issues with the Performance script](#62-issues-with-the-performance-script) |
| 63 | [Deploy WordPress Docker Containers](#63-deploy-wordpress-docker-containers) |
| 64 | [Dev-performance Web server is not responding](#64-dev-performance-web-server-is-not-responding) |
| 65 | [CPU Utilization issue with service](#65-cpu-utilization-issue-with-service) |
| 66 | [Notify that Procore Products website is under maintenance](#66-notify-that-procore-products-website-is-under-maintenance) |
| 67 | [Modify User Account Profile Picture](#67-modify-user-account-profile-picture) |
| 68 | [Update Performance chart on Procore Products Website](#68-update-performance-chart-on-procore-products-website) |
| 69 | [Update Order List on the Procore Products Website](#69-update-order-list-on-the-procore-products-website) |
| 70 | [Remove Maintenance Banner](#70-remove-maintenance-banner) |
| 71 | [Install Terraform on your Virtual Machine](#71-install-terraform-on-your-virtual-machine) |
| 72 | [Deploy Production Web Server from Template](#72-deploy-production-web-server-from-template) |
| 73 | [Install PHP](#73-install-php) |
| 74 | [Install a LAMP stack application](#74-install-a-lamp-stack-application) |
| 75 | [Create a WIKI page for Documentation Purposes](#75-create-a-wiki-page-for-documentation-purposes) |
| 76 | [Perform a Security Audit on a Linux system using Lynis](#76-perform-a-security-audit-on-a-linux-system-using-lynis) |
| 77 | [Create a Python script](#77-create-a-python-script) |
| 78 | [Project: Managing Active Directory](#78-83-project--managing-active-directory) |
| 79 | [Access Active Directory Services](#79-access-active-directory-services) |
| 80 | [Create a New Organization Unit](#80-create-a-new-organization-unit) |
| 81 | [Create a new user](#81-create-a-new-user) |
| 82 | [Create a new user group](#82-create-a-new-user-group) |
| 83 | [Research and create documentation](#83-research-and-create-documentation) |
| 84 | [Vulnerability Scanning with OpenVAS](#84-vulnerability-scanning-with-openvas) |
| 85 | [Fix the high Vulnerabilities showing in the report](#85-fix-the-high-vulnerabilities-showing-in-the-report) |

---

## 1. Deploy a new CentOS 9 Virtual Machine on Vsphere

`TASK: The Infrastructure Team is requesting a new CentOS 9 Virtual Machine (VM) to launch a new product for the software development team. Please use the naming convention in the requirements section below. Ensure VM details are added to the asset tiger inventory tool.`

**STEPS TAKEN:**

1. Accessed vSphere and selected the correct sandbox correlated to the Host IP address:

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T1_1.png?raw=true"/>

2. Clicked on "Actions" and selected "New Virtual Machine"

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T1_2.png?raw=true"/>

3. Selected "Create a new virtual machine"

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T1_3.jpg?raw=true"/>

4. Created VM according to the "Requirements;" however, CentOS 9 was not listed as an option, so I chose CentOS 8 for the guest OS

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T1_4.png?raw=true"/>

5. Then later I was able to select the ISO image as listed in the "Requirements"

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T1_5.png?raw=true"/>

6. Once it was created, I powered it on and clicked "Launch Web Console"

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T1_6.png?raw=true"/>

7. I booted the OS normally and went through the steps to perform a minimal installation:

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T1_7.jpg?raw=true"/>

8. I was able to successfully login to the VM

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T1_8.png?raw=true"/>

9. I ran `ip a` to obtain the IP address and MAC address (link)

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T1_9.png?raw=true"/>

10. I ran `dmidecode -t system | grep -i serial` to obtain the serial number

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T1_10.png?raw=true"/>

[🔝 Back to Top](#-table-of-contents)

---

## 2. Create your own resource pool on VSphere

`TASK: To efficiently manage and allocate organization's resources, we need to create resource clusters for our deployed and upcoming VMs.`

**STEPS TAKEN:**

1. Followed the instruction listed on the Wiki on "How to create a resource pool in Vsphere"
2. Opened vSphere Client and highlighted Data Center location
3. Right-click on the Data Center and choose 'New Resource Pool'
4. Named my resource pool as JLEWIS-CLUSTER and clicked 'OK'
5. Next, I selected the VM I created for Ticket 1 and right-clicked on it to select 'Migrate'
6. Selected the first option: 'Change compute resource only', and clicked 'Next'
7. Selected 'Resource Pools' tab, chose my resource pool, and clicked 'Next'
8. Selected YT-Intran-VLAN and clicked 'Next' until I was able to click 'Finish'

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T2_1.png?raw=true"/>

[🔝 Back to Top](#-table-of-contents)

---

## 3. Migrate your deployed VM to your Resource Pool

`TASK: Now that the Resource Pool has been successfully created, please proceed with moving your server/s into it.`

**STEPS TAKEN:**

1. I selected the VM I created for Ticket 1 and right-clicked on it to select 'Migrate'
2. Selected the first option: 'Change compute resource only', and clicked 'Next'
3. Selected 'Resource Pools' tab, chose my resource pool, and clicked 'Next'
4. Selected YT-Intran-VLAN and clicked 'Next' until I was able to click 'Finish'

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T3_1.png?raw=true"/>

[🔝 Back to Top](#-table-of-contents)

---

## 4. Network setup request

`TASK: Please refer to the IP Address Management (IPAM sheet) to locate the necessary network information. Use this information to establish a static connection for your dev-app server.`

**STEPS TAKEN:**

1. Used the following command to add a static connection: `nmcli c a con-name dev-app-static autoconnect yes ifname ens192 type ethernet ip4 <ipaddress> gw4 <gatewayaddress> ipv4.dns <dnsaddress>`
2. Added the user procore to wheel group and assigned password.

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T4_1.png?raw=true"/>

[🔝 Back to Top](#-table-of-contents)

---

## 5. Install and Configure FreeIPA client

`TASK: Proceed with the installation and configuration of the IPA client on your new virtual machine (VM).`

**STEPS TAKEN:**

1. Followed the steps listed for configuring an IPA-Client
2. Ran the following to install package: `dnf install ipa-client -y`
3. Ran the following to install IPA Client:
   - `ipa-client-install --mkhomedir`
   - `procore.dev`
   - `ipa.procore.dev`
4. Entered username and password to enroll IPA Client and received the following confirmation:

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T5_1.png?raw=true"/>

5. Used the `id jlewis` command to confirm if IPA was working correctly:

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T5_2.png?raw=true"/>

6. Used the `ipa user-show jlewis` command to confirm the following:

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T5_3.png?raw=true"/>

7. **Note:** While configuring IPA if you get an error message, try: `ipa-client-install --mkhomedir --force-join` or use `kinit jlewis` to use Kerberos (security software used w/IPA to ensure connection is genuine) in order to confirm your access and identity.

[🔝 Back to Top](#-table-of-contents)

---

## 6. Add user msoriano to FreeIPA

`TASK: The developer's team recently hired Marie Soriano. Please create a username msoriano for the new user and add them to the group "webmasters." Additionally, set up a temporary password for the user and ensure this information is documented in the ticket.`

**STEPS TAKEN:**

1. Logged into freeIPA, added a new user for Marie Soriano, set password and clicked "Add and Edit"

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T6_1.png?raw=true"/>

2. Clicked on the "User Groups" tab in order to add msoriano to the group "Webmasters" by selecting it and moving it from "Available" to "Prospective," then clicked "Add"

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T6_2.png?raw=true"/>

3. Confirmed user was created by running the `id msoriano` command:

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T6_3.png?raw=true"/>

[🔝 Back to Top](#-table-of-contents)

---

## 7. Add user to group using FreeIPA

`TASK: The user you recently added has been assigned to another project supporting the team in revamping the production webpage. Please add this user to the "support" group.`

**STEPS TAKEN:**

1. Clicked on "Active Users" and searched for msoriano

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T7_1.png?raw=true"/>

2. Clicked on username, clicked on "User Groups" tab, then clicked "+Add" to move the support group from "Available" to "Prospective" and clicked "Add"

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T7_2.png?raw=true"/>

3. Confirmed user was added to the group by running the `id msoriano` command:

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T7_3.png?raw=true"/>

[🔝 Back to Top](#-table-of-contents)

---

## 8. Add the following info to the local DNS file

`TASK: Please add the following information to the local DNS file on the dev-app server.`

**STEPS TAKEN:**

1. Added vim by installing it with: `dnf install vim -y`
2. Used vim to add the following IP addresses to the `/etc/hosts` directory:
   - `10.1.XX.XX vcenter.sandbox.prod`
   - `10.1.XX.XX ipa.procore.dev`
   - `10.1.XX.XX dev-nagios.procore.prod1`
   - `10.1.XX.XX stage-foreman.procore.prod`
   - `10.1.XX.XX stage-bacula.procore.prod1`
   - `10.1.XX.XX dev-ansible.procore.prod1 dev-ansible`
   - `10.1.XX.XX stage-bastion.procore.prod1 stage-bastion`
   - `10.1.XX.XX nfs-dev.procore.prod1`
   - `10.1.XX.XX stage-graylog.procore.prod`
3. Used the `ping` command to confirm connection to the DNS files

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T8_1.png?raw=true"/>

[🔝 Back to Top](#-table-of-contents)

---

## 9. Create the Following Mount points

`TASK: Please create the following mount points for the upcoming nfs share on the dev-app server.`

**STEPS TAKEN:**

1. Used the following command: `mkdir -pv /nfs/incoming/{home,vhosts,scripts}`
2. Then used `cd` to enter directory `/nfs/incoming` to confirm mount points were created:

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T9_1.png?raw=true"/>

[🔝 Back to Top](#-table-of-contents)

---

## 10. Please mount the following NFS shares permanently

`TASK: Please ensure the following NFS shares are mounted permanently on the dev-app server.`

**STEPS TAKEN:**

1. Updated the `/etc/fstab` as shown below:

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T10_1.png?raw=true"/>

2. Then ran `mount -a` and `mount | grep nfs` to confirm that the directories were mounted correctly:

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T10_2.png?raw=true"/>

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T10_3.png?raw=true"/>

[🔝 Back to Top](#-table-of-contents)

---

## 11. NFS home directory

`TASK: Since you will be using SSH in accessing multiple servers, please create a shared directory using your username and 700 permission.`

**STEPS TAKEN:**

1. Used `cd` to enter `/nfs/incoming/home` directory and then used `mkdir jlewis` to create my shared directory:

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T11_1.png?raw=true"/>

2. Then used `chown -R jlewis:jlewis jlewis/` to assign my freeIPA username to be the owner of the directory:

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T11_2.png?raw=true"/>

3. Lastly, used `chmod -R 700 jlewis/` to assign the proper permissions on the shared directory

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T11_3.png?raw=true"/>

[🔝 Back to Top](#-table-of-contents)

---

## 12. Please deploy a dev webserver using configuration Template

`TASK: The web development team requires you to deploy a development web server using the NEW-YT-DEV-WEBSERVER-TEMPLATE. Please update the necessary information on the newly deployed server.`

**STEPS TAKEN:**

1. Selected my Cluster folder and clicked on "Actions" to select "New Virtual Machine"

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T12_1.png?raw=true"/>

2. For creation type, I selected "Deploy from template"

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T12_2.png?raw=true"/>

3. Under "Select a Template," I clicked on the "Data Center" tab in order to select the NEW-YT-DEV-WEBSERVER-TEMPLATE and clicked "Next"

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T12_3.png?raw=true"/>

4. Labeled new 'Virtual machine name' to `dev-performance-jl.procore.prod1` and clicked "Next"

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T12_4.png?raw=true"/>

5. When asked to select a compute resource, I selected my cluster folder and clicked "Next"

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T12_5.png?raw=true"/>

6. For Storage, DS-01 was selected from the "Batch Configure" tab and then I clicked "Next"

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T12_6.png?raw=true"/>

7. For Clone options, I left everything as default and clicked "Next," then clicked "Finish"

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T12_7.png?raw=true"/>

8. Since I did not know the password for the account, I interrupted the GRUB process in order to access rescue mode via the shell

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T12_8.png?raw=true"/>

9. Added password and created autorelabel file to bypass SELinux

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T12_9.png?raw=true"/>

10. Logged into VM and enabled SSH, then proceeded to update the hostname as requested:

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T12_10.png?raw=true"/>

11. Added static connection using the following `nmcli c a con-name dev-perf-static ifname ens192 type ethernet ip4 <ipaddress> gw4 <gatewayaddress> ipv4.dns <dnsaddress> autoconnect yes`, then set `prod-web` to `autoconnect no`

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T12_11.png?raw=true"/>

12. Next, I installed freeIPA following the steps from ticket 5 and ran `id jlewis` to confirm that it was properly configured

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T12_12.png?raw=true"/>

13. Added the DNS records as outlined in ticket 8, created the mount points as outlined in ticket 9, and permanently mounted the directories as outlined in ticket 10.

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T12_13.png?raw=true"/>

14. Ran the following commands to add user procore with the requested information:
    - `useradd -G wheel procore`
    - `echo procoreplus | passwd --stdin procore`

[🔝 Back to Top](#-table-of-contents)

---

## 13. Allow HTTP to use non-standard ports

`TASK: The network and security teams are requesting that your dev-performance web server listens on a non-standard port (8001). Please configure your server to meet this requirement and provide the link for testing.`

**STEPS TAKEN:**

1. Installed `policycoreutils` in order to utilize `semanage`

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T13_1.png?raw=true"/>

2. Accessed the man page for `semanage-port` to view the example on how to allow a port via `httpd` services and then ran the following command: `semanage port -a -t http_port_t -p tcp 8001`
3. To confirm it was added correctly, I ran the following: `semanage port -l | grep 8001`

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T13_2.png?raw=true"/>

4. Installed httpd with the following command: `dnf install httpd`
5. Then started the service by running `systemctl enable --now httpd`

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T13_3.png?raw=true"/>

6. Edited the `/etc/httpd/conf/httpd.conf` file to listen for port 8001

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T13_4.png?raw=true"/>

7. Installed netstat (`dnf install net-tools`) to confirm the server was listening: `netstat -tuln | grep 8001`

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T13_5.png?raw=true"/>

8. Added the following services and port to the firewall:
   - `firewall-cmd --permanent --add-service=http`
   - `firewall-cmd --permanent --add-service=https`
   - `firewall-cmd --add-port=8001/tcp`
9. Created the link: `http://{insertipaddress}:8001/`

[🔝 Back to Top](#-table-of-contents)

---

## 14. Configure a repository

`TASK: The Development team requires you to install a third-party application that can be found on below repository.`

**STEPS TAKEN:**

1. Added repository by using `vim epel.repo` to add the following information in the `/etc/yum.repos.d` directory

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T14_1.png?raw=true"/>

2. Ran `dnf clean all` and `dnf repoinfo`, then ran `dnf provides tmux` and `dnf install tmux`

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T14_2.png?raw=true"/>

[🔝 Back to Top](#-table-of-contents)

---

## 15. Create and Copy your SSH key

`TASK: The security and network team is requesting that all users generate SSH keys to access the Ansible server and our GitLab repository.`

**STEPS TAKEN:**

1. Logged into jlewis account on `dev-app-jl.procore.prod1` server and ran `ssh-keygen`

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T15_1.png?raw=true"/>

2. Then ran `ssh-copy-id jlewis@dev-ansible.procore.prod1`, entered my password and my key was added

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T15_2.png?raw=true"/>

3. Then tested connection with `ssh jlewis@dev-ansible.procore.prod1`

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T15_3.png?raw=true"/>

4. Ran the ssh-keygen command while in the `dev-ansible.procore.prod1` directory

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T15_4.png?raw=true"/>

5. Then ran `ssh-copy-id jlewis@10.1.XX.XX` since my server had not been added to the /etc/hosts file yet, entered my password and my key was added

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T15_5.png?raw=true"/>

6. Accessed `dev-app-jl.procore.prod1` server in order to obtain ssh public key by running `cat id_ed25519.pub`

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T15_6.png?raw=true"/>

7. Finally, accessed GitLab and went to "User Settings" to click on "SSH Keys" and clicked "Add New Key" to paste key into database. Repeated the above steps for `dev-performance` server as well and uploaded both keys to GitLab:

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T15_7.png?raw=true"/>

[🔝 Back to Top](#-table-of-contents)

---

## 16. Add Dev Servers into Ansible inventory

`TASK: To perform automated actions on our infrastructure, please add your development servers to the Ansible inventory file.`

**STEPS TAKEN:**

1. SSH'd into `dev-ansible` server and edited the `/etc/hosts` file by adding the following to the end of the file:
   - `10.1.XX.XX dev-app-jl.procore.prod1 dev-app-jl`
   - `10.1.XX.XX dev-performance-jl.procore.prod1 dev-perf-jl`
2. Accessed the inventory file (`/etc/ansible/hosts`) and added my ansible group `[dev-jl]`

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T16_1.png?raw=true"/>

3. Ran the following to test ping compatibility with my ansible group `ansible -m ping dev-jl`

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T16_2.png?raw=true"/>

[🔝 Back to Top](#-table-of-contents)

---

## 17. Patch your Dev Servers using Ansible

`TASK: In accordance with company policy, all development servers must be patched regularly. Please follow the instructions provided under Infrastructure Resources to patch your development servers using Ansible.`

**STEPS TAKEN:**

1. Used `dnf update python3` to confirm it was installed and up to date on both servers
2. Used `cd /opt/ansible/patching` to view the `dev-patch.yml` file and copy the contents into `dev-patch-jl.yml`

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T17_1.png?raw=true"/>

3. Ran `ansible-playbook dev-patch-jl-app.yml -K` and received results that did not match the wiki for a successful patch

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T17_2.png?raw=true"/>

4. After reading the fatal error messages, removed the `kernel-*` exclusion and reran, which resolved 1 error

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T17_3.png?raw=true"/>

5. Removed the filter for `rpm-*` and the `var=out` line and reran — achieved successful results on both servers

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T17_4.png?raw=true"/>

[🔝 Back to Top](#-table-of-contents)

---

## 18. Please use Ansible to create the task below

`TASK: The programmers on the webmasters team want to have a shared directory for collaboration on scripting knowledge for their division on all development servers.`

**STEPS TAKEN:**

1. Read the documentation for [ad-hoc commands](https://docs.ansible.com/ansible/latest/command_guide/intro_adhoc.html#patterns-and-ad-hoc-commands) and wrote the following command:
   `ansible dev-jl -m ansible.builtin.file -a "dest=/opt/scripts/jlewis/ state=directory owner=jlewis group=webmasters mode=775" -K`

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T18_1.png?raw=true"/>

2. Command did not complete correctly due to permissions. Ran `ansible --help` and read the options page for "Privilege Escalation Options:"

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T18_2.png?raw=true"/>

3. Added `-b` flag to run as root: `ansible dev-jl -m ansible.builtin.file -a "dest=/opt/scripts/jlewis/ state=directory owner=jlewis group=webmasters mode=775" -K -b`

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T18_3.png?raw=true"/>

4. Verified both servers had the shared directory created: `ll -d /opt/scripts/jlewis/`

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T18_4.png?raw=true"/>

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T18_5.png?raw=true"/>

5. Equivalent playbook (`create_shared_directory.yml`):

    ```yaml
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

6. Run with: `ansible-playbook create_shared_directory.yml -K -b`

[🔝 Back to Top](#-table-of-contents)

---

## 19. Please update the system inventory database

`TASK: For inventory purposes, please populate the system inventory database of your dev servers.`

**STEPS TAKEN:**

1. Created file `git-repository.yml` in `/opt/ansible` with tasks to install git, clone the repository, and run `host_facts.sh`

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T19_1.png?raw=true"/>

2. Ran `ansible-playbook git-repository.yml -K -b -vv` — git installed but cloning stalled due to credential prompt

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T19_2.png?raw=true"/>

3. Ran `git clone` manually and confirmed GitLab required authentication

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T19_3.png?raw=true"/>

4. Updated playbook to use a Personal Access Token (PAT) for authentication

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T19_4.png?raw=true"/>

5. Reran — error showed file was not being found

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T19_5.png?raw=true"/>

6. Corrected the script filename to `host_fact.sh_DoNotDelete` (confirmed with Infrastructure team) and added double quotes around `git_token` and `repo` values

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T19_6.png?raw=true"/>

7. Reran playbook — all tasks completed successfully

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T19_7.png?raw=true"/>

8. Verified `.txt` files were generated in `/tmp` on both servers

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T19_8.png?raw=true"/>

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T19_9.png?raw=true"/>

[🔝 Back to Top](#-table-of-contents)

---

## 20. Push the script to gitlab repo

`TASK: The development department will need to have a new version of the host_facts.sh created and uploaded to Gitlab.`

**STEPS TAKEN:**

1. Logged in as `root` on dev-app server and accessed `/root/scripts`: `cp host_fact.sh_DoNotDelete jlewis_host_facts.sh`
2. Appended a date command and ran `cat jlewis_host_facts.sh`

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T20_1.png?raw=true"/>

3. Ran `git init`, `git add jlewis_host_facts.sh`, and `git status`

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T20_2.png?raw=true"/>

4. Ran `git commit -m "Adding jlewis_host_facts.sh file"` — error populated

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T20_3.png?raw=true"/>

5. Ran `git restore --staged jlewis_host_facts.sh` and checked status

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T20_4.png?raw=true"/>

6. Reran as `git commit -m "Add jlewis_host_facts.sh"` and received successful results

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T20_5.png?raw=true"/>

7. Pushed with `git push -u origin master`

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T20_6.png?raw=true"/>

8. Confirmed file was added to GitLab repository

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T20_7.png?raw=true"/>

[🔝 Back to Top](#-table-of-contents)

---

## 21. Spin up a Web server using a Kickstart file

`TASK: One of our clients intends to build a staging web server to launch a new product. Please set up a new virtual machine (VM) using the naming convention provided below.`

**STEPS TAKEN:**

1. Created new VM named `stage-web-jl.procore.prod1`

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T21_1.png?raw=true"/>

2. Input all information requested for requirements

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T21_2.png?raw=true"/>

3. Powered on VM and interrupted boot process, pressed `e` to edit the boot parameters for the `linuxefi` line

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T21_3.png?raw=true"/>

4. Added the required line of code for GRUB to run the kickstart configuration file and pressed `Ctrl-x` to execute

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T21_4.png?raw=true"/>

5. Server successfully booted; corrected the default IP address to allow package installation
6. Completed the steps from tickets 8–10 to configure mount points and DNS records

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T21_5.png?raw=true"/>

[🔝 Back to Top](#-table-of-contents)

---

## 22. Configure FreeIPA Client on the Stage Virtual Machine

`TASK: All new servers must be enrolled in our IPA server. Please enroll the staging server you just created.`

**STEPS TAKEN:**

1. Installed IPA onto staging server by following Ticket 5 steps

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T22_1.png?raw=true"/>

2. Added SSH key from stage-web server: `ssh-keygen -t rsa -C "jlewis@stage-web-jl"` and copied to dev-ansible with `ssh-copy-id jlewis@dev-ansible` and vice versa

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T22_2.png?raw=true"/>

3. Added stage-web-jl.procore.prod1 to inventory group and performed Ansible Ping test — all successful

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T22_3.png?raw=true"/>

4. Added public key for stage-web server to GitLab using `cat id_rsa.pub`

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T22_4.png?raw=true"/>

[🔝 Back to Top](#-table-of-contents)

---

## 23. Disable and prevent SSH root user access to all your servers as part of the security audit requirement

`TASK: Disallowing root logins over SSH requires system administrators to authenticate using their own individual accounts and then escalate to root via sudo or su.`

**STEPS TAKEN:**

1. Confirmed SSH access via `jlewis` IPA account, then accessed each server as root and edited `/etc/ssh/sshd_config` to set `PermitRootLogin` to `no`

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T23_1.png?raw=true"/>

2. Ran `systemctl restart sshd` and `systemctl daemon-reload`

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T23_2.png?raw=true"/>

3. Confirmed SSH as root was blocked; `su` still worked for local escalation

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T23_3.png?raw=true"/>

[🔝 Back to Top](#-table-of-contents)

---

## 24. Restrict SSH access on all servers except Bastion Host (Rich Rule)

`TASK: The security department requests that all servers created on our infrastructure only accept SSH communication from the Bastion host.`

**STEPS TAKEN:**

1. Opened two terminal sessions per server, then allowed the Bastion Host IP:
   `sudo firewall-cmd --permanent --add-rich-rule='rule family="ipv4" source address="{ipaddressofbastionhost}" port port="22" protocol="tcp" accept'`

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T24_1.png?raw=true"/>

2. Removed default SSH access rules:
   - `sudo firewall-cmd --permanent --remove-port=22/tcp`
   - `sudo firewall-cmd --permanent --remove-service=ssh`

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T24_2.png?raw=true"/>

3. Reloaded the firewall to apply the changes

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T24_3.png?raw=true"/>

4. Confirmed direct SSH was blocked

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T24_4.png?raw=true"/>

5. SSH'd into the Bastion server with my IPA username

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T24_5.png?raw=true"/>

6. Successfully SSH'd into my terminal from the Bastion server

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T24_6.png?raw=true"/>

7. Updated `/etc/hosts` on Bastion and added RSA SSH keys from Bastion to each server

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T24_7.png?raw=true"/>

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T24_8.png?raw=true"/>

[🔝 Back to Top](#-table-of-contents)

---

## 25. Graylog client

`TASK: Please configure your dev-app, dev-performance and stage-web virtual machines to send logs to the Graylog server.`

**STEPS TAKEN:**

1. SSH'd into `stage-graylog` and confirmed firewall was configured to accept syslog input over UDP port 5140

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T25_1.png?raw=true"/>

2. Created `/etc/rsyslog.d/90-graylog.conf` on each server with: `*.* @10.1.XX.XX:5140;RSYSLOG_SyslogProtocol23Format`

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T25_2.png?raw=true"/>

3. Restarted rsyslog and confirmed log transmission in the Graylog web interface

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T25_3.png?raw=true"/>

[🔝 Back to Top](#-table-of-contents)

---

## 26. Install Apache Web Server

`TASK: Please install the apache webserver to the stage-web-jl.procore.prod1-IP server. Make sure to start and enable apache.`

**STEPS TAKEN:**

1. Checked if httpd was installed: `sudo dnf info httpd` and `systemctl status httpd`

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T26_1.png?raw=true"/>

2. Installed with `sudo dnf install httpd -y`, started and enabled with `systemctl enable --now httpd`, and confirmed status

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T26_2.png?raw=true"/>

[🔝 Back to Top](#-table-of-contents)

---

## 27. Allow apache to the firewall

`TASK: After installing Apache, please open ports 80 and 443 on the stage web server you created. Additionally, allow the Apache service through the firewall.`

**STEPS TAKEN:**

1. On `stage-web` VM, ran the following commands:
   - `sudo firewall-cmd --permanent --add-port=80/tcp`
   - `sudo firewall-cmd --permanent --add-port=443/tcp`
   - `sudo firewall-cmd --permanent --add-service=http`
   - `sudo firewall-cmd --permanent --add-service=https`
2. Verified with `sudo firewall-cmd --list-all` and reloaded

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T27_1.png?raw=true"/>

[🔝 Back to Top](#-table-of-contents)

---

## 28. Configure apache web content

`TASK: Please configure ariclaw web server contents on stage-web server which can be found at the URL below.`

**STEPS TAKEN:**

1. Installed `git` and cloned: `git clone git@gitlab.com:procoreplusmd/ariclaw.git`

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T28_1.png?raw=true"/>

2. Configured git user, moved repo to `/var/www/html`, and ran `git config --list`

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T28_2.png?raw=true"/>

3. Accessed the IP address link — site was not displaying content

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T28_3.png?raw=true"/>

4. Accessed `/etc/httpd/conf.d/welcome.conf` and commented out all lines

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T28_4.png?raw=true"/>

5. Restarted the Apache services: `systemctl restart httpd`

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T28_5.png?raw=true"/>

6. Site began displaying content at the IP address

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T28_6.png?raw=true"/>

7. Verified SSH key was working — non-fatal GitLab warning noted (expected behavior)

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T28_7.png?raw=true"/>

8. Changed permissions of the repository folder

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T28_8.png?raw=true"/>

9. Created `/etc/httpd/conf.d/ariclaw.conf` with the required content

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T28_9.png?raw=true"/>

10. Restarted httpd service

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T28_10.png?raw=true"/>

11. Cleared browser cache and confirmed site loaded correctly

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T28_11.png?raw=true"/>

[🔝 Back to Top](#-table-of-contents)

---

## 29. Update web content for ariclaw

`TASK: Ariclaw has recently changed their phone number. Please update the website content.`

**STEPS TAKEN:**

1. Identified phone number in two places on the current site

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T29_1.png?raw=true"/>

2. Updated the `contact.html` file in `/var/www/html` and `/nfs/incoming/vhosts/ariclaw/htdocs` with the new phone number

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T29_2.png?raw=true"/>

3. Ran `sudo systemctl restart httpd` and confirmed the updated number appeared on the site

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T29_3.png?raw=true"/>

[🔝 Back to Top](#-table-of-contents)

---

## 30. Install MariaDB

`TASK: The development team requested the installation of MariaDB version 10.3 on your dev-app-jl.procore.prod1-IP server.`

**STEPS TAKEN:**

1. Created and configured the MariaDB repository: `sudo vi /etc/yum.repos.d/MariaDB.repo`

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T30_1.png?raw=true"/>

2. Installed MariaDB Server and Client, started and enabled the service, and confirmed status

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T30_2.png?raw=true"/>

3. Ran the secure installation script: `sudo mariadb-secure-installation`

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T30_3.png?raw=true"/>

4. Verified login with: `mysql -u root -p`

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T30_4.png?raw=true"/>

[🔝 Back to Top](#-table-of-contents)

---

## 31. Create a snapshot of your VM

`TASK: The infrastructure team will perform a company wide maintenance next week. Please create a snapshot of all your Virtual Machines.`

**STEPS TAKEN:**

1. Accessed vSphere Client and clicked on each VM to access the "Snapshots" tab and clicked "Take Snapshot…"

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T31_1.png?raw=true"/>

2. Named each snapshot respective to the server and Ticket 31

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T31_2.png?raw=true"/>

3. Waited until all VM snapshots were created successfully

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T31_3.png?raw=true"/>

[🔝 Back to Top](#-table-of-contents)

---

## 32. Register your VMs to Foreman

`TASK: The Security Team is requiring that all servers be registered with the Foreman server and patched accordingly moving forward.`

**STEPS TAKEN:**

1. SSH'd into `stage-foreman` VM — unable to access due to firewall restrictions

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T32_1.png?raw=true"/>

2. Updated `/etc/ssh/sshd_config` to allow root login and ran `ssh-copy-id -i ~foreman-proxy/.ssh/id_rsa_foreman_proxy.pub 10.1.XX.XX` for each VM

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T32_2.png?raw=true"/>

3. Downloaded the subscription-manager package

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T32_3.png?raw=true"/>

4. Installed the Katello CA cert and registered with Foreman

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T32_4.png?raw=true"/>

5. Verified registration in Foreman Web UI under Hosts → Content Hosts

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T32_5.png?raw=true"/>

[🔝 Back to Top](#-table-of-contents)

---

## 33. Run remote command from Foreman

`TASK: The Security Team needs to create a local user on all the VMs of the infrastructure using Foreman, the user's name is Reuben Camilo, the username would be rcamilo.`

**STEPS TAKEN:**

1. Selected all 3 VMs in Foreman and clicked "Schedule Remote Job"

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T33_1.png?raw=true"/>

2. Added command `useradd -C "Reuben Camilo" rcamilo` — all jobs failed

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T33_2.png?raw=true"/>

3. Identified `PermitRootLogin` was set to `no` — updated one server to test

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T33_3.png?raw=true"/>

4. Identified the flag error: used `-C` instead of `-c`

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T33_4.png?raw=true"/>

5. Reran with corrected command — still required `PermitRootLogin yes`

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T33_5.png?raw=true"/>

6. Set all servers to `PermitRootLogin yes` and reran — all 3 VMs showed successful

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T33_6.png?raw=true"/>

[🔝 Back to Top](#-table-of-contents)

---

## 34. Create a central location for logs

`TASK: We would like to establish a central location on the server dev-app-jl.procore.prod1-IP to store logs.`

**STEPS TAKEN:**

1. Powered off VM, added a new 1 GB hard disk in vSphere, and powered back on

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T34_1.png?raw=true"/>

2. Confirmed disk at `/dev/sdb` using `lsblk`

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T34_2.png?raw=true"/>

3. Used `fdisk /dev/sdb` to create partition

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T34_3.png?raw=true"/>

4. Created `ext4` filesystem via VG and LV

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T34_4.png?raw=true"/>

5. Created mount point `/lfjs/logs`, user `lfjs`, and assigned ownership: `sudo chown -R lfjs:webmasters /lfjs/logs`

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T34_5.png?raw=true"/>

6. Set SGID permissions: `sudo chmod 2755 /lfjs/logs/`

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T34_6.png?raw=true"/>

7. Edited `/etc/fstab` to mount persistently

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T34_7.png?raw=true"/>

8. Confirmed with `lsblk`

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T34_8.png?raw=true"/>

[🔝 Back to Top](#-table-of-contents)

---

## 35. Users are having issues with SSH

`TASK: We have received numerous emails from developers regarding issues with SSH access to your dev-app server. Please investigate the issue and attach the last 20 lines of the logs to this ticket.`

**STEPS TAKEN:**

1. Used `id apprentice` to confirm user existed, then attempted `ssh apprentice@localhost`

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T35_1.png?raw=true"/>

2. Attempted to access `/lfjs/logs` as `apprentice` — permissions had reset to root

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T35_2.png?raw=true"/>

3. Re-applied correct permissions and confirmed as `apprentice` via `su`

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T35_3.png?raw=true"/>

4. Accessed the directory — no contents found

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T35_4.png?raw=true"/>

5. Checked `/var/log`, `tallylog`, and `lastlog` — nothing notable found

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T35_5.png?raw=true"/>

6. Ran `find / -type f -user apprentice | grep ssh` — noted similar keys in `known_hosts` and `known_hosts.old`

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T35_6.png?raw=true"/>

7. Checked `/var/log/secure` for the last 20 lines — found that user `apprentice` was not using `port 22` for SSH

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T35_7.png?raw=true"/>

[🔝 Back to Top](#-table-of-contents)

---

## 36. Users are reporting repo issues

`TASK: One of our clients has reported that the del.extreme-ix repository is not functioning properly on dev-app-[initials].procore.prod1-IP.`

**STEPS TAKEN:**

1. Accessed the `epel.repo` file — noted `enabled=1` was included during original setup (not part of original instructions). Possible issue if the URL requires `https`.

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T36_1.png?raw=true"/>

[🔝 Back to Top](#-table-of-contents)

---

## 37. User is having issue in accessing file

`TASK: User created in ticket 6 has reported that he/she is unable to write to the directory /lfjs/logs when logged into dev-app-[initials].procore.prod.`

**STEPS TAKEN:**

1. `msoriano` is part of the webmasters group but still unable to write. Created an ACL:
   `sudo setfacl -m u:msoriano:rw /lfjs/logs`

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T37_1.png?raw=true"/>

[🔝 Back to Top](#-table-of-contents)

---

## 38. Urgent! Malicious IP

`TASK: The networking team has reported a malicious IP that is trying to get into our network.`

**STEPS TAKEN:**

1. Ran the following on each VM to block the malicious IP:
   `sudo firewall-cmd --permanent --add-rich-rule='rule family="ipv4" source address="XX.XX.XX.XX" port port="22" protocol="tcp" drop'`
2. Ran `sudo firewall-cmd --reload` to apply the rule
3. Ran `sudo firewall-cmd --list-all` to confirm it was applied

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T38_1.png?raw=true"/>

[🔝 Back to Top](#-table-of-contents)

---

## 39. Please provide the apache version

`TASK: The development team is helping us troubleshoot an issue with apache on stage-web-jl.procore.prod1-IP.`

**STEPS TAKEN:**

1. Ran both `dnf list httpd` and `dnf info httpd` to obtain the version information in two different formats

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T39_1.png?raw=true"/>

[🔝 Back to Top](#-table-of-contents)

---

## 40. Get a list of all the users that have enrolled on FreeIPA

`TASK: The administration is requesting a detailed list of all users registered on the FreeIPA server. Please generate this list using IPA commands and redirect the output to a file.`

**STEPS TAKEN:**

1. Used `ipa user-find msoriano` to confirm user was in database and then ran `ipa user-del msoriano` to delete user

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T40_1.png?raw=true"/>

2. Ran `ipa user-find >> ipa_users.txt` to export all users into a file

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T40_2.png?raw=true"/>

[🔝 Back to Top](#-table-of-contents)

---

## 41. Please configure cronjob

`TASK: The engineering team would like to have a cron job configured on the dev-app-jl.procore.prod1-IP server.`

**STEPS TAKEN:**

1. Copied the script file from `/nfs/incoming/scripts/logs.sh` to `~/` and changed ownership to my freeIPA user

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T41_1.png?raw=true"/>

2. Confirmed `crond` was running and ran `crontab -eu jlewis` to input the cron schedule

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T41_2.png?raw=true"/>

3. Checked `/var/log/cron` and confirmed the script was running every 6 hours

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T41_3.png?raw=true"/>

[🔝 Back to Top](#-table-of-contents)

---

## 42. Please create a cronjob

`TASK: Please create a cronjob on stage-web-jl.procore.prod1-IP server to restart apache every 2 days at 11 AM.`

**STEPS TAKEN:**

1. Set up initial cronjob on `stage-web-jl` server

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T42_1.png?raw=true"/>

2. Confirmed cronjob was running by setting up a temporary duplicate that ran every 2 minutes

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T42_2.png?raw=true"/>

3. Checked `/var/log/cron` — job ran but produced an error (required authentication)

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T42_3.png?raw=true"/>

4. Ran `sudo crontab -eu root` to add the cronjob as root and tested

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T42_4.png?raw=true"/>

5. Finalized cronjob: `0 11 */2 * * systemctl restart httpd` as root

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T42_5.png?raw=true"/>

[🔝 Back to Top](#-table-of-contents)

---

## 43. Create NAGIOS user and configure access

`TASK: To utilize the NAGIOS service, you need to create an HTTP user on the server.`

**STEPS TAKEN:**

1. SSH'd into `dev-nagios` server

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T43_1.png?raw=true"/>

2. Added user with: `htpasswd /usr/local/nagios/etc/htpasswd.users jlewis`

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T43_2.png?raw=true"/>

3. Edited `/usr/local/nagios/etc/cgi.cfg` and appended `jlewis` to all directives
4. Restarted Nagios and verified user access via the Nagios web UI

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T43_3.png?raw=true"/>

[🔝 Back to Top](#-table-of-contents)

---

## 44. Add the servers to Nagios

`TASK: Please add your Virtual machines to Nagios monitoring system.`

**STEPS TAKEN:**

1. Installed NRPE and Nagios plugins on each server:
   `sudo dnf install epel-release nrpe nagios-plugins-{load,http,users,procs,disk,swap,nrpe,uptime} -y`

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T44_1.png?raw=true"/>

2. Edited `/etc/nagios/nrpe.cfg` and updated `allowed_hosts` to include the Nagios server IP

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T44_2.png?raw=true"/>

3. Started NRPE and created config files for each server by copying `yt-templates.cfg.bak`

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T44_3.png?raw=true"/>

4. Linked new config files in `/usr/local/nagios/etc/nagios.cfg`

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T44_4.png?raw=true"/>

5. Reloaded Nagios — received warning message

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T44_5.png?raw=true"/>

6. Ran `sudo /usr/local/nagios/bin/nagios -v /usr/local/nagios/etc/nagios.cfg` to diagnose

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T44_6.png?raw=true"/>

7. Commented out missing referenced file, reran — no errors or warnings

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T44_7.png?raw=true"/>

8. Found that someone had changed the user:group of `/usr/local/nagios/`. Ran `sudo chown -R nagios:nagios /usr/local/nagios/` to correct and got the service running again

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T44_8.png?raw=true"/>

9. Verified hosts were being monitored in the Nagios web UI — both statuses showed OK!

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T44_9.png?raw=true"/>

[🔝 Back to Top](#-table-of-contents)

---

## 45. Configure FTP Server and Client

`TASK: Please configure the FTP server on dev-app-jl.procore.prod1-IP and the FTP client on stage-web-jl.procore.prod1-IP.`

**STEPS TAKEN:**

1. Used `sudo dnf install ftp -y` to install ftp on both servers, then copied `ftp-prod.config` from the NFS share

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T45_1.png?raw=true"/>

2. Added ftp service to both servers: `sudo firewall-cmd --permanent --add-service=ftp` and reloaded

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T45_2.png?raw=true"/>

3. Ran `ftp stage-web-jl` — received an error

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T45_3.png?raw=true"/>

4. Installed `vsftpd` on both servers, opened port 21, and started the service

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T45_4.png?raw=true"/>

5. Used `ftp dev-app-jl` from `stage-web-jl`, logged in with freeIPA credentials, and ran `get ftp-prod.config`

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T45_5.png?raw=true"/>

6. Confirmed the file was on the home directory with `ll`

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T45_6.png?raw=true"/>

[🔝 Back to Top](#-table-of-contents)

---

## 46. Create tasks using Ansible Playbook

`TASK: Please create an ansible playbook that would perform the below tasks on dev-app-jl.procore.prod1-IP.`

**STEPS TAKEN:**

1. Created `user_add.yml` in `/etc/ansible/playbook/jlewis` referencing Ansible documentation for user and dnf modules

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T46_1.png?raw=true"/>

2. Ran `ansible-playbook user_add.yml -K -b`

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T46_2.png?raw=true"/>

3. Confirmed on `dev-app-jl` server that everything was completed correctly

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T46_3.png?raw=true"/>

[🔝 Back to Top](#-table-of-contents)

---

## 47. Closing these ports via an ansible playbook

`TASK: Please create an Ansible playbook to close ports 80 and 443 on dev-app-jl.procore.prod1-IP.`

**STEPS TAKEN:**

1. Reviewed `ansible.posix.firewalld` documentation and wrote `close_ports.yml`

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T47_1.png?raw=true"/>

2. Ran `ansible-playbook close_ports.yml -K -b`

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T47_2.png?raw=true"/>

[🔝 Back to Top](#-table-of-contents)

---

## 48. Please create backups for your server kernel

`TASK: The infrastructure team will deploy a company wide kernel update next week.`

**STEPS TAKEN:**

1. Accessed `/lib/modules` on each server and created backups to the requested location:
   - `sudo tar -czvf /nfs/incoming/vhosts/backup/dev-app-jl-kernel-backup.tar.gz 5.14.0-621.el9.x86_64`
   - `sudo tar -czvf /nfs/incoming/vhosts/backup/stage-web-jl-kernel-backup.tar.gz 5.14.0-575.el9.x86_64/`

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T48_1.png?raw=true"/>

[🔝 Back to Top](#-table-of-contents)

---

## 49. Create a Symlink

`TASK: Please create a symlink in your home directory on your stage-web VM for the file /var/www/html/ariclaw/elements.html and name the symlink elements.`

**STEPS TAKEN:**

1. Ran the following command: `ln -s /var/www/html/ariclaw/elements.html ~/elements`

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T49_1.png?raw=true"/>

[🔝 Back to Top](#-table-of-contents)

---

## 50. Provide log information from Graylog

`TASK: The development team requires information about the MariaDB database you installed on your dev-app server. Please query the logs using the Graylog server to determine the exact date and time of the installation.`

**STEPS TAKEN:**

1. Accessed Graylog site and searched for "MariaDB"

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T50_1.png?raw=true"/>

2. Filtered by source `dev-app-jl` and changed time range to "last 14 days" — confirmed MariaDB was initially installed on October 18

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T50_2.png?raw=true"/>

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T50_3.png?raw=true"/>

[🔝 Back to Top](#-table-of-contents)

---

## 51. RAM upgrade request

`TASK: The infrastructure team is requesting that you scale up dev-app-jl.procore.prod1-IP due to an increase in user requests. Please create a clone of the virtual machine before making any changes.`

**STEPS TAKEN:**

1. Powered down `dev-app-jl` and cloned it as `dev-app-jl-clone` in vSphere

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T51_1.png?raw=true"/>

2. Updated memory from 1GB to 1536 MB

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T51_2.png?raw=true"/>

3. Powered back on and ran `free -mh` to confirm RAM was updated

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T51_3.png?raw=true"/>

4. Powered on the clone VM and confirmed the additional memory was reflected

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T51_4.png?raw=true"/>

[🔝 Back to Top](#-table-of-contents)

---

## 52. Storage request

`TASK: Users have requested additional space to be allocated to the /lfjs/logs filesystem on dev-app-jl.procore.prod1-IP.`

**STEPS TAKEN:**

1. Ran `lsblk` — confirmed no free space available to extend existing filesystem

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T52_1.png?raw=true"/>

2. Ran `fdisk /dev/sdb` to add another 100MB partition

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T52_2.png?raw=true"/>

3. Created the PV to add it to the VG

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T52_3.png?raw=true"/>

4. Extended the VG and LV: `sudo vgextend vglogs /dev/sdb2` and `lvextend -r -L +96 /dev/vglogs/lvlogs`

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T52_4.png?raw=true"/>

5. Confirmed new storage amount with `lsblk`

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T52_5.png?raw=true"/>

[🔝 Back to Top](#-table-of-contents)

---

## 53. Create a script to gather these info below

`TASK: Please create a script to gather information about your VM.`

**STEPS TAKEN:**

1. Identified the required commands after reviewing man pages:
   - `date`, `last -F 10`, `free -h`, `uname -srv`, `nmcli | grep "inet4 10.*"`
2. Created `/tmp/serverinfo.info` and populated it with the script content

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T53_1.png?raw=true"/>

3. Made executable with `sudo chmod +x serverinfo.info` and ran on each server

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T53_2.png?raw=true"/>

4. Network access was giving issues at the time — unable to provide additional screenshots for the second server.

[🔝 Back to Top](#-table-of-contents)

---

## 54. Create your own GitLab repository

`TASK: For documentation purposes, we request that everyone create their own GitLab repository and upload their Ansible playbooks and Bash scripts.`

**STEPS TAKEN:**

1. Used `rsync` to copy playbooks from `dev-ansible` to `dev-app-jl`:
   `rsync -avs --delete jlewis@dev-ansible:/etc/ansible/playbook/jlewis /home/jlewis/gitlab`

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T54_1.png?raw=true"/>

2. Created a new blank GitLab project at `https://gitlab.com/justintimejlew/ansible_playbooks`

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T54_2.png?raw=true"/>

3. Initialized git, added remote, committed, and attempted `git push -u origin master` — failed because the branch was named `main`

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T54_3.png?raw=true"/>

4. Ran `git pull --rebase origin main` then `git push -u origin main` successfully

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T54_4.png?raw=true"/>

5. Confirmed files were committed to: https://gitlab.com/justintimejlew/ansible_playbooks/

[🔝 Back to Top](#-table-of-contents)

---

## 55. Please rotate HTTPD logs

`TASK: The ariclaw website is generating a large number of logs. Please modify the log rotation settings to rotate the HTTPD logs daily and ensure that log rotation retains logs for only 14 days on stage-web-jl.procore.prod1-IP.`

**STEPS TAKEN:**

1. Accessed `/etc/logrotate.d/httpd` and set `daily` and `rotate 14`

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T55_1.png?raw=true"/>

2. Ran `sudo systemctl status logrotate` — confirmed service runs and deactivates after completion

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T55_2.png?raw=true"/>

3. Forced the changes: `sudo logrotate -f /etc/logrotate.d/httpd`

[🔝 Back to Top](#-table-of-contents)

---

## 56. Add both of your servers to CheckMK

`TASK: Please add both of your servers to CheckMK monitoring tools.`

**STEPS TAKEN:**

1. Installed wget and the Checkmk agent, then ran `sudo dnf -y localinstall check-mk-agent-2.3.0p2-1.noarch.rpm`

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T56_1.png?raw=true"/>

2. Opened port 6556 for Checkmk agent communication and started the socket

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T56_2.png?raw=true"/>

3. Accessed the Checkmk Web Interface, navigated to the DEV directory, and clicked "Add Host"

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T56_3.png?raw=true"/>

4. Entered hostname and IP for each VM and clicked "Save & run service discovery"

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T56_4.png?raw=true"/>

5. Clicked "Changes" to activate

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T56_5.png?raw=true"/>

6. Clicked "Activate on selected sites"

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T56_6.png?raw=true"/>

7. Verified hosts were created by filtering with "jl" in the Hosts view

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T56_7.png?raw=true"/>

[🔝 Back to Top](#-table-of-contents)

---

## 57. Fix the issue on your Web Server

`TASK: We have been receiving a lot of emails about your stage-web-jl-procore.prod1-IP. Verify and troubleshoot critical services using CheckMK.`

**STEPS TAKEN:**

1. Searched for `stage-web-jl` in CheckMK and clicked on the hostname

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T57_1.png?raw=true"/>

2. Checked "Monitoring Status" — nothing of concern found

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T57_2.png?raw=true"/>

3. Reviewed "Rules" — listed several rules CheckMK was running

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T57_3.png?raw=true"/>

4. Checked "Test notification" — found fallback email address was missing

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T57_4.png?raw=true"/>

5. Added email address to the system

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T57_5.png?raw=true"/>

6. Activated changes on selected sites

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T57_6.png?raw=true"/>

7. Reviewed all monitoring services — NTP showed "CRIT"

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T57_7.png?raw=true"/>

8. Ran `sudo systemctl enable --now chronyd` and rescanned

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T57_8.png?raw=true"/>

9. NTP showed OK after rescan. Removed test email from Global Settings.

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T57_9.png?raw=true"/>

[🔝 Back to Top](#-table-of-contents)

---

## 58. Create a systemd service for the script procored

`TASK: Procore-Plus has deployed a new daemon that needs to be running on every server.`

**STEPS TAKEN:**

1. Copied `procored.sh` to `/usr/bin/procored` on each server

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T58_1.png?raw=true"/>

2. Ran `sudo systemctl enable --now procored` — received an error (no unit file found)

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T58_2.png?raw=true"/>

3. Created `/etc/systemd/system/procored.service` unit file

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T58_3.png?raw=true"/>

4. Ran `sudo systemctl daemon-reload`, `sudo systemctl enable --now procored`, and confirmed status

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T58_4.png?raw=true"/>

[🔝 Back to Top](#-table-of-contents)

---

## 59. Configure an NFS Server

`TASK: Please configure an NFS server on dev-app-jl.procore.prod1.`

**STEPS TAKEN:**

1. Created `/nfs-jlewis` directory and downloaded the required rpm

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T59_1.png?raw=true"/>

2. Edited `/etc/exports` and added: `/nfs-jlewis stage-web-jl(rw,sync,no_root_squash)`

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T59_2.png?raw=true"/>

3. Ran `exportfs -rav` to refresh the NFS export table

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T59_3.png?raw=true"/>

4. Confirmed `nfs` service was allowed in the firewall

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T59_4.png?raw=true"/>

5. On `stage-web-jl`, created mount point, mounted the NFS share, and confirmed with `df -hT`

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T59_5.png?raw=true"/>

6. Updated `/etc/fstab` for persistent mounting

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T59_6.png?raw=true"/>

7. Ran `sudo systemctl daemon-reload` and `sudo mount -a` — confirmed access to `/nfs-jlewis`

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T59_7.png?raw=true"/>

[🔝 Back to Top](#-table-of-contents)

---

## 60. Install and Configure Bacula

`TASK: The infrastructure team needs to back up your VMs. Please install the Bacula Client (downgrade) and Libraries on both of your servers.`

**STEPS TAKEN:**

**Client Installation:**

1. Installed required development tools and libraries on each server

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T60_1.png?raw=true"/>

2. Downloaded and extracted Bacula 9.6.6 source code

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T60_2.png?raw=true"/>

3. Configured the build for client only: `sudo ./configure --enable-client-only`
4. Compiled and installed: `sudo make -j$(nproc)` and `sudo make install`

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T60_3.png?raw=true"/>

5. Created the `bacula-fd.service` unit file

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T60_4.png?raw=true"/>

6. Enabled and started the Bacula File Daemon — confirmed symlink was created

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T60_5.png?raw=true"/>

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T60_6.png?raw=true"/>

**Client Configuration:**

1. Configured `/etc/bacula/bacula-fd.conf`

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T60_7.png?raw=true"/>

2. Configured `/etc/bacula/bconsole.conf`

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T60_8.png?raw=true"/>

3. Added clients in the Bacula Web Interface

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T60_9.png?raw=true"/>

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T60_10.png?raw=true"/>

4. Verified connectivity for each server via "Status Client"

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T60_11.png?raw=true"/>

5. Created backup jobs using the "New job wizard"

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T60_12.png?raw=true"/>

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T60_13.png?raw=true"/>

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T60_14.png?raw=true"/>

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T60_15.png?raw=true"/>

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T60_16.png?raw=true"/>

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T60_17.png?raw=true"/>

6. Ran backup jobs for each server

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T60_18.png?raw=true"/>

7. Verified backup ran successfully for each server

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T60_19.png?raw=true"/>

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T60_20.png?raw=true"/>

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T60_21.png?raw=true"/>

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T60_22.png?raw=true"/>

[🔝 Back to Top](#-table-of-contents)

---

## 61. Run Performance script

`TASK: The development team has notified all users to manually run a performance script on all servers. Please execute the script located at /nfs/incoming/scripts/perfomance.sh as the root user. After running the script, a file named /setup_file.cfg should be created.`

**STEPS TAKEN:**

1. Created a snapshot on each VM prior to starting this ticket.
2. Accessed `/nfs/incoming/scripts/` and ran `sudo ./perfomance.sh` on each VM — `setup_file.cfg` was created on each.

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T61_1.png?raw=true"/>

[🔝 Back to Top](#-table-of-contents)

---

## 62. Issues with the Performance script

`TASK: After running the performance script, the development team noticed some issues with the NFS and HTTPD services. Most of the files for these services were deleted. Please restore these files from the backup you created earlier using Bacula.`

**STEPS TAKEN:**

1. Visited Bacula Web Interface — "Restore wizard" was not working properly, so accessed the "Jobs" tab

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T62_1.png?raw=true"/>

2. Clicked "Job history" and selected the "Full" backup to click "Details"

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T62_2.png?raw=true"/>

3. Clicked "Restore"

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T62_3.png?raw=true"/>

4. Navigated the folder tree to the `etc` folder, added both files, and clicked "Next"

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T62_4.png?raw=true"/>

5. Left "Where" settings as default

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T62_5.png?raw=true"/>

6. Left "Options" settings as default

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T62_6.png?raw=true"/>

7. Clicked "Run restore"

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T62_7.png?raw=true"/>

8. Restore job produced warning messages, but files were placed in `/tmp/restore/etc`

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T62_8.png?raw=true"/>

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T62_9.png?raw=true"/>

9. Moved files to `/etc` using `mv`: `sudo mv exports /etc/` and `sudo mv httpd/ /etc/httpd.bak`

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T62_10.png?raw=true"/>

10. Confirmed httpd and nfs-server services were running

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T62_11.png?raw=true"/>

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T62_12.png?raw=true"/>

[🔝 Back to Top](#-table-of-contents)

---

## 63. Deploy WordPress Docker Containers

`TASK: The Public Relations department wants to deploy a WordPress website. Please follow the instructions at the URL below to complete this request.`

**STEPS TAKEN:**

1. Ran `docker run --name some-wordpress --network some-network -d wordpress` — selected `docker.io/library/wordpress:latest`

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T63_1.png?raw=true"/>

2. Received an error

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T63_2.png?raw=true"/>

3. Tried `docker run --name some-wordpress -p 8080:80 -d wordpress` — same error

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T63_3.png?raw=true"/>

4. Ran `sudo podman system migrate` and reran — ran successfully

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T63_4.png?raw=true"/>

5. Accessed `10.1.XX.XX:8080` — redirected to WordPress setup page, confirming WordPress was configured

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T63_5.png?raw=true"/>

[🔝 Back to Top](#-table-of-contents)

---

## 64. Dev-performance Web server is not responding

`TASK: Some end users are reporting connectivity issues with the internal dev-performance system. Please troubleshoot the issue.`

**STEPS TAKEN:**

1. Checked network connection with `nmcli c s` and `ping -c4 google.com`

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T64_1.png?raw=true"/>

2. Checked `sudo systemctl status NetworkManager` — service was running

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T64_2.png?raw=true"/>

3. Ran `ss -tuln | grep :80` and `ss -tuln | grep :443` — HTTPS did not appear to be working

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T64_3.png?raw=true"/>

4. Found that `httpd.conf` was missing from `/etc/httpd/conf`. Copied it from the backup restoration and added `Listen 443`

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T64_4.png?raw=true"/>

5. Restarted httpd and confirmed `curl -k http://localhost` returned HTML content

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T64_5.png?raw=true"/>

[🔝 Back to Top](#-table-of-contents)

---

## 65. CPU Utilization issue with service

`TASK: Please stop and disable the procored system service on all servers. Afterward, verify that CPU utilization is normal using Check_MK.`

**STEPS TAKEN:**

1. On each server, ran `sudo systemctl stop procored`, `sudo systemctl disable procored`, and confirmed status

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T65_1.png?raw=true"/>

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T65_2.png?raw=true"/>

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T65_3.png?raw=true"/>

2. Visited CheckMK and confirmed CPU utilization was only about 5.06%

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T65_4.png?raw=true"/>

[🔝 Back to Top](#-table-of-contents)

---

## 66. Notify that Procore Products website is under maintenance

`TASK: The webmaster would like you to add a banner indicating that the website will be down for maintenance.`

**STEPS TAKEN:**

1. Attempted `sudo git clone git@gitlab.com:procoreplusmd/procore-products.git` — error

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T66_1.png?raw=true"/>

2. Ran `git init` then cloned with `sudo git clone`

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T66_2.png?raw=true"/>

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T66_3.png?raw=true"/>

3. Ran `git config --global --add safe.directory /var/www/html` and checked git status

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T66_4.png?raw=true"/>

4. Commented out all lines in `/etc/httpd/conf.d/welcome.conf` and restarted httpd

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T66_5.png?raw=true"/>

5. Removed the hidden `.git` directory and re-cloned using `https://` instead of `git@`

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T66_6.png?raw=true"/>

6. Copied `index.html` to `/var/www/html/` — site displayed web contents at `http://10.1.XX.XX`

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T66_7.png?raw=true"/>

7. Copied the maintenance banner `index.html` from `websiteDownForMaintenance` folder

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T66_8.png?raw=true"/>

8. Copied all site contents and applied the maintenance banner

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T66_9.png?raw=true"/>

[🔝 Back to Top](#-table-of-contents)

---

## 67. Modify User Account Profile Picture

`TASK: Please modify the profile picture for user Jessica on the website. Use the following files to update her information.`

**STEPS TAKEN:**

1. Used browser "Inspect" tool to identify Jessica's current photo as `notification-01.jpg`

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T67_1.png?raw=true"/>

2. Confirmed the updated photo in GitLab was labeled `notification-dog.img`

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T67_2.png?raw=true"/>

3. Ran: `sudo cp notification-dog.img /var/www/html/img/notification-01.jpg`

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T67_3.png?raw=true"/>

[🔝 Back to Top](#-table-of-contents)

---

## 68. Update Performance chart on Procore Products Website

`TASK: The website requires a new feature to be added to the performance chart.`

**STEPS TAKEN:**

1. Took a snapshot of the performance chart before making changes

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T68_1.png?raw=true"/>

2. Confirmed file location in `/var/www/html/js` and ran:
   `sudo cp tooplate-scripts-orig.js /var/www/html/js/tooplate-scripts.js`

[🔝 Back to Top](#-table-of-contents)

---

## 69. Update Order List on the Procore Products Website

`TASK: Please update the Order List table on the Procore Products website to ensure that all cancelled orders are removed.`

**STEPS TAKEN:**

1. Took a screenshot of the current order list

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T69_1.png?raw=true"/>

2. Accessed `/var/www/html/procore-products/removeCancelledProducts` and ran:
   `sudo cp index.html /var/www/html/`

[🔝 Back to Top](#-table-of-contents)

---

## 70. Remove Maintenance Banner

`TASK: Now that all issues on the dev-performance server have been resolved, please remove the maintenance banner that was added.`

**STEPS TAKEN:**

1. Took a screenshot of the site before making changes

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T70_1.png?raw=true"/>

2. Accessed `/var/www/html/procore-products/websiteUpAndReady` and ran:
   `sudo cp index.html /var/www/html/`

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T70_2.png?raw=true"/>

[🔝 Back to Top](#-table-of-contents)

---

## 71. Install Terraform on your Virtual Machine

`TASK: Please install terraform on your dev-app-jl.procore.prod1 VM.`

**STEPS TAKEN:**

1. Visited https://developer.hashicorp.com/terraform/install and selected ARM64 Version: 1.13.4

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T71_1.png?raw=true"/>

2. Downloaded Terraform: `sudo wget https://releases.hashicorp.com/terraform/1.13.4/terraform_1.13.4_linux_arm64.zip`

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T71_2.png?raw=true"/>

3. Unzipped and moved to `/usr/bin`

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T71_3.png?raw=true"/>

4. Ran `terraform -v` — received an error

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T71_4.png?raw=true"/>

5. Installed via the HashiCorp repo instead — `terraform -v` worked successfully

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T71_5.png?raw=true"/>

6. Cloned `dev-performance-jl` to a template in vSphere

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T71_6.png?raw=true"/>

7. Confirmed template was created by deploying a test VM from it

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T71_7.png?raw=true"/>

[🔝 Back to Top](#-table-of-contents)

---

## 72. Deploy Production Web Server from Template

`TASK: Please use Terraform code to deploy the newly fixed web server into production. The server should be created within your vSphere resource pool.`

**STEPS TAKEN:**

1. Created a `terraform` directory on `dev-app-jl`, initialized git, and cloned the Terraform repo

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T72_1.png?raw=true"/>

2. Edited `terraform.tfvars` with the required configuration

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T72_2.png?raw=true"/>

3. Updated `main.tf` with hostname `prod-webserver-jl.procore.prod1`

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T72_3.png?raw=true"/>

4. Ran `sudo terraform init`

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T72_4.png?raw=true"/>

5. Ran `sudo terraform plan` — resource pool not found due to case-sensitivity

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T72_5.png?raw=true"/>

6. Updated `terraform.tfvars` and reran `sudo terraform plan` — successful

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T72_6.png?raw=true"/>

7. Ran `sudo terraform apply` — received an error (likely a permissions restriction on VM deletion)

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T72_7.png?raw=true"/>

8. Despite the error, the VM was created and I was able to log into it

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T72_8.png?raw=true"/>

[🔝 Back to Top](#-table-of-contents)

---

## 73. Install PHP

`TASK: The web development team requests that PHP be installed on stage-web-jl.procore.prod1-IP.`

**STEPS TAKEN:**

1. Ran `sudo dnf info php` to check availability

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T73_1.png?raw=true"/>

2. Ran `sudo dnf install php` to install PHP and all dependencies

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T73_2.png?raw=true"/>

[🔝 Back to Top](#-table-of-contents)

---

## 74. Install a LAMP stack application

`TASK: The development team has released a new application, and you have been assigned the task of deploying it and configuring the associated database.`

**STEPS TAKEN:**

1. Cloned the CRM project: `sudo git clone https://gitlab.com/procoreplusmd/crm-project`

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T74_1.png?raw=true"/>

2. Extracted and copied the CRM project to `/var/www/html`

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T74_2.png?raw=true"/>

3. Installed MariaDB, enabled the service, and ran `sudo mysql_secure_installation`

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T74_3.png?raw=true"/>

4. Attempted to install Apache — service could not start because `httpd.conf` was deleted by the script

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T74_4.png?raw=true"/>

5. Restored `httpd.conf` via rsync from `dev-perf-jl`

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T74_5.png?raw=true"/>

6. Restarted httpd, opened firewall ports, and confirmed site access

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T74_6.png?raw=true"/>

7. Installed PHP with opcache and created `/var/www/html/info.php` to test

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T74_7.png?raw=true"/>

8. Installed MySQL support and common PHP modules

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T74_8.png?raw=true"/>

9. Reran install without `php-xmlrpc` (not found) and restarted Apache

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T74_9.png?raw=true"/>

10. Revisited info.php to verify module installation

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T74_10.png?raw=true"/>

11. Installed phpMyAdmin: `sudo dnf -y install phpMyAdmin`

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T74_11.png?raw=true"/>

12. Edited Apache's phpMyAdmin config to allow remote access

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T74_12.png?raw=true"/>

13. Attempted phpMyAdmin login — did not work initially

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T74_13.png?raw=true"/>

14. Updated `dbconnection.php` files with the correct password
15. Accessed the admin panel at `http://10.1.XX.XX/crm/admin`

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T74_14.png?raw=true"/>

16. Created the `crm` database in phpMyAdmin and imported: `mysql -u root -p crm < /var/www/html/crm/crm.sql`
17. Recreated user account and confirmed access to the site

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T74_15.png?raw=true"/>

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T74_16.png?raw=true"/>

[🔝 Back to Top](#-table-of-contents)

---

## 75. Create a WIKI page for Documentation Purposes

`TASK: Please create a wiki document outlining the steps to install and configure a firewall for an HTTP server. Name the page using your username and place it in the Procore-Plus How-To Guides section.`

**STEPS TAKEN:**

1. Created an account on the wiki site

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T75_1.png?raw=true"/>

2. Visited the Procore-Plus Wiki and clicked the "Edit" tab

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T75_2.png?raw=true"/>

3. Populated the editing page with my username link

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T75_3.png?raw=true"/>

4. Added the following content to the "JLewis" wiki page and confirmed changes were shown

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T75_4.png?raw=true"/>

[🔝 Back to Top](#-table-of-contents)

---

## 76. Perform a Security Audit on a Linux system using Lynis

`TASK: The security team has notified all administrators to conduct an audit and scan for security vulnerabilities and loopholes on your Linux machine using the Lynis tool.`

**STEPS TAKEN:**

1. Ran `sudo dnf provides lynis` and confirmed the package, then installed with `sudo dnf install lynis`

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T76_1.png?raw=true"/>

2. Ran `sudo lynis audit system >> /tmp/systemaudit` to perform the audit and redirect output

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T76_2.png?raw=true"/>

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T76_3.png?raw=true"/>

[🔝 Back to Top](#-table-of-contents)

---

## 77. Create a Python script

`TASK: The security team requires that administrators create a Python script to gather information about the VM they are working on (Hostname, IP address, OS System, Release, Version, Machine architecture).`

**STEPS TAKEN:**

1. Confirmed Python 3.9.23 was installed via `python -V`. Created `sudo vim python.sh` on the dev-app server with the required script content.

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T77_1.png?raw=true"/>

2. Made executable with `sudo chmod u+x python.sh` and ran: `sudo ./python.sh >> /tmp/pythoninfo`

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T77_2.png?raw=true"/>

[🔝 Back to Top](#-table-of-contents)

---

## 78-83. Project : Managing Active Directory

`TASK: Accessing the Windows Active Directory server to manage and administer user accounts.`

[🔝 Back to Top](#-table-of-contents)

---

## 79. Access Active Directory Services

`OBJECTIVE: Use the Remote Desktop Client to connect to Active Directory services.`

**STEPS TAKEN:**

1. Accessed Microsoft Remote Desktop on iMac and clicked on "Add PC"

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T79_1.png?raw=true"/>

2. Input the Server and User information as directed on the wiki

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T79_2.png?raw=true"/>

[🔝 Back to Top](#-table-of-contents)

---

## 80. Create a New Organization Unit

`OBJECTIVE: Add a new Organizational Unit (OU) under the domain using the Active Directory Users and Computers tool.`

**STEPS TAKEN:**

1. Right clicked on the VITI folder under "sandbox.prod → Yellow tail" and selected "New → Organizational Unit," named it "JLewis-VITI," and unchecked "Protective Container"

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T80_1.png?raw=true"/>

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T80_2.png?raw=true"/>

[🔝 Back to Top](#-table-of-contents)

---

## 81. Create a new user

`OBJECTIVE: Enhance system administration skills through identity management using Active Directory.`

**STEPS TAKEN:**

1. Right clicked on the OU, then selected "New" and "User"

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T81_1.png?raw=true"/>

2. Entered user information and clicked "Next"

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T81_2.png?raw=true"/>

3. Selected "password never expire" and entered the provided password

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T81_3.png?raw=true"/>

4. Clicked "Finish"

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T81_4.png?raw=true"/>

[🔝 Back to Top](#-table-of-contents)

---

## 82. Create a new user group

`OBJECTIVE: Enhance system administration skills through identity management using Active Directory.`

**STEPS TAKEN:**

1. Right clicked on the OU, then selected "New" and "Group"

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T82_1.png?raw=true"/>

2. Entered group name and confirmed "Global" and "Security" were selected

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T82_2.png?raw=true"/>

3. Right clicked on user "Mike Tyson" and selected "Add to a group…"

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T82_3.png?raw=true"/>

4. Entered group name and clicked "OK"

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T82_4.png?raw=true"/>

[🔝 Back to Top](#-table-of-contents)

---

## 83. Research and create documentation

`OBJECTIVE: Research and create a document explaining what an Active Directory Domain is and the steps to join a Windows 10 device to it.`

**STEPS TAKEN:**

1. Researched via Microsoft documentation: https://learn.microsoft.com/en-us/windows-server/identity/ad-ds/get-started/virtual-dc/active-directory-domain-services-overview

2. **Summary:** An Active Directory Domain is a directory on a network that stores information about users for access across the network based on assigned permissions. Users can be added to groups and permissions can be assigned individually or collectively. Users and groups can also be removed to preserve the structure of any organization.

3. Researched how to join a Windows 10 device via Microsoft documentation: https://learn.microsoft.com/en-us/windows-server/identity/ad-ds/manage/join-computer-to-domain — reviewed the Control Panel Method, Settings App Method, and Command Line Method.

[🔝 Back to Top](#-table-of-contents)

---

## 84. Vulnerability Scanning with OpenVAS

`TASK: Scan a Linux System with OpenVAS and generate an auto report of all the vulnerabilities found on the system.`

**STEPS TAKEN:**

1. Opened the firewall on development servers: `sudo firewall-cmd --permanent --add-source=10.1.XX.XX` and `sudo firewall-cmd --reload`

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T84_1.png?raw=true"/>

2. Accessed the OpenVAS console and logged in

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T84_2.png?raw=true"/>

3. Created new credentials under Configuration → Credentials

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T84_3.png?raw=true"/>

4. Created a scan target under Configuration → Targets

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T84_4.png?raw=true"/>

5. Created a scan task under Scans → Tasks

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T84_5.png?raw=true"/>

6. Clicked "Start" to run the scan

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T84_6.png?raw=true"/>

7. After the scan finished, accessed Scans → Reports and downloaded the report

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T84_7.png?raw=true"/>

8. Scan results: `OpenVAS-Rescan-Validation.pdf`

[🔝 Back to Top](#-table-of-contents)

---

## 85. Fix the high Vulnerabilities showing in the report

`TASK: This ticket documents the remediation and subsequent validation of vulnerabilities reported in the initial OpenVAS scan. As part of compliance requirements, provide a clean re-scan as evidence.`

**STEPS TAKEN:**

1. Reviewed the scan report. For Host Authentications, checked `/etc/ssh/sshd_config` and changed `PermitRootLogin` to `yes` to allow root login and result in a "Success."

2. Could not update the OpenVAS version (22.4.1 to 23.0.1) as it was outside my control. Instead, ran `sudo dnf update` to update all packages and address a portion of 2.1.1 High general/tcp threats.

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T85_1.png?raw=true"/>

3. For 2.1.2 Medium 8080/tcp, ran `sudo podman system migrate` to stop the container and remove the public configuration.

    <img src="https://github.com/justintimejlew/sysadmin-ticket-log/blob/main/Screenshots/T85_2.png?raw=true"/>

4. For 2.1.3 Medium 21/tcp, reviewed `/etc/vsftpd/vsftpd.conf`, commented out problematic lines, and removed the ftp service from the firewall: `sudo firewall-cmd --remove-service=ftp`

5. For 2.1.4 Low general/icmp, edited `/etc/sysctl.conf` to add `net.ipv4.icmp_echo_ignore_all = 1`. Then ran the following firewall commands to block ICMP timestamp responses:
   - `sudo firewall-cmd --permanent --add-rich-rule='rule family="ipv4" icmp-type name="timestamp-reply" drop'`
   - `sudo firewall-cmd --reload`

6. For 2.1.5 Low general/tcp, added `net.ipv4.tcp_timestamps = 0` to `/etc/sysctl.conf` and ran `sudo sysctl -p` to apply.

7. Rebooted the VM and reran the scan — all vulnerabilities were addressed.
   Scan results: `OpenVAS-Rescan-Validation-2025-11-17.pdf`

[🔝 Back to Top](#-table-of-contents)