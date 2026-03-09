# sysadmin-ticket-log

[![Home Button](https://img.shields.io/badge/%E2%9E%A4_Go_Back_Home-darkred?style=for-the-badge&logo=)](https://github.com/justintimejlew#home-button)

> **Note:** Please ignore red font used on tickets 1–48. Some information has been redacted for security purposes.

---

## 📋 Table of Contents

| # | Ticket Title |
|---|---|
| 1 | [Deploy a new CentOS 9 Virtual Machine on vSphere](#1-deploy-a-new-centos-9-virtual-machine-on-vsphere) |
| 2 | [Create your own resource pool on vSphere](#2-create-your-own-resource-pool-on-vsphere) |
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
| 23 | [Disable and prevent SSH root user access to all your servers](#23-disable-and-prevent-ssh-root-user-access-to-all-your-servers) |
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

---

## 1. Deploy a new CentOS 9 Virtual Machine on vSphere

`TASK: The Infrastructure Team is requesting a new CentOS 9 Virtual Machine (VM) to launch a new product for the software development team. Please use the naming convention in the requirements section below. Ensure VM details are added to the asset tiger inventory tool.`

**STEPS TAKEN:**

1. Accessed vSphere and selected the correct sandbox correlated to the Host IP address.
2. Clicked on "Actions" and selected "New Virtual Machine."
3. Selected "Create a new virtual machine."
4. Created VM according to the "Requirements;" however, CentOS 9 was not listed as an option, so I chose CentOS 8 for the guest OS.
5. Then later I was able to select the ISO image as listed in the "Requirements."
6. Once it was created, I powered it on and clicked "Launch Web Console."
7. I booted the OS normally and went through the steps to perform a minimal installation.
8. I was able to successfully login to the VM.
9. I ran `ip a` to obtain the IP address and MAC address (link).
10. I ran `dmidecode -t system | grep -i serial` to obtain the serial number.

[🔝 Back to Top](#-table-of-contents)

---

## 2. Create your own resource pool on vSphere

`TASK: To efficiently manage and allocate organization's resources, we need to create resource clusters for our deployed and upcoming VMs.`

**STEPS TAKEN:**

1. Followed the instruction listed on the Wiki on "How to create a resource pool in vSphere."
2. Opened vSphere Client and highlighted Data Center location.
3. Right-click on the Data Center and choose 'New Resource Pool.'
4. Named my resource pool as JLEWIS-CLUSTER and clicked 'OK.'
5. Next, I selected the VM I created for Ticket 1 and right-clicked on it to select 'Migrate.'
6. Selected the first option: 'Change compute resource only', and clicked 'Next.'
7. Selected 'Resource Pools' tab, chose my resource pool, and clicked 'Next.'
8. Selected YT-Intran-VLAN and clicked 'Next' until I was able to click 'Finish.'

[🔝 Back to Top](#-table-of-contents)

---

## 3. Migrate your deployed VM to your Resource Pool

`TASK: Now that the Resource Pool has been successfully created, please proceed with moving your server/s into it.`

**STEPS TAKEN:**

1. I selected the VM I created for Ticket 1 and right-clicked on it to select 'Migrate.'
2. Selected the first option: 'Change compute resource only', and clicked 'Next.'
3. Selected 'Resource Pools' tab, chose my resource pool, and clicked 'Next.'
4. Selected YT-Intran-VLAN and clicked 'Next' until I was able to click 'Finish.'

[🔝 Back to Top](#-table-of-contents)

---

## 4. Network setup request

`TASK: Please refer to the IP Address Management (IPAM sheet) to locate the necessary network information. Use this information to establish a static connection for your dev-app server.`

**STEPS TAKEN:**

1. Used the following command to add a static connection:
   ```
   nmcli c a con-name dev-app-static autoconnect yes ifname ens192 type ethernet ip4 <ipaddress> gw4 <gatewayaddress> ipv4.dns <dnsaddress>
   ```
2. Added the user procore to wheel group and assigned password.

[🔝 Back to Top](#-table-of-contents)

---

## 5. Install and Configure FreeIPA client

`TASK: Proceed with the installation and configuration of the IPA client on your new virtual machine (VM).`

**STEPS TAKEN:**

1. Followed the steps listed for configuring an IPA-Client.
2. Ran the following to install package: `dnf install ipa-client -y`
3. Ran the following to install IPA Client:
   - `ipa-client-install --mkhomedir`
   - `procore.dev`
   - `ipa.procore.dev`
4. Entered username and password to enroll IPA Client and received confirmation.
5. Used the `id jlewis` command to confirm IPA was working correctly.
6. Used the `ipa user-show jlewis` command to confirm.
7. **Note:** If you get an error message, try: `ipa-client-install --mkhomedir --force-join` or use `kinit jlewis` to use Kerberos.

[🔝 Back to Top](#-table-of-contents)

---

## 6. Add user msoriano to FreeIPA

`TASK: The developer's team recently hired Marie Soriano. Please create a username msoriano for the new user and add them to the group "webmasters." Additionally, set up a temporary password for the user and ensure this information is documented in the ticket.`

**STEPS TAKEN:**

1. Logged into FreeIPA, added a new user for Marie Soriano, set password and clicked "Add and Edit."
2. Clicked on the "User Groups" tab to add msoriano to the group "Webmasters" by moving it from "Available" to "Prospective," then clicked "Add."
3. Confirmed user was created by running the `id msoriano` command.

[🔝 Back to Top](#-table-of-contents)

---

## 7. Add user to group using FreeIPA

`TASK: The user you recently added has been assigned to another project supporting the team in revamping the production webpage. Please add this user to the "support" group.`

**STEPS TAKEN:**

1. Clicked on "Active Users" and searched for msoriano.
2. Clicked on username, clicked on "User Groups" tab, then clicked "+Add" to move the support group from "Available" to "Prospective" and clicked "Add."
3. Confirmed user was added to the group by running the `id msoriano` command.

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
3. Used the `ping` command to confirm connection to the DNS files.

[🔝 Back to Top](#-table-of-contents)

---

## 9. Create the Following Mount points

`TASK: Please create the following mount points for the upcoming nfs share on the dev-app server.`

**STEPS TAKEN:**

1. Used the following command: `mkdir -pv /nfs/incoming/{home,vhosts,scripts}`
2. Then used `cd` to enter directory `/nfs/incoming` to confirm mount points were created.

[🔝 Back to Top](#-table-of-contents)

---

## 10. Please mount the following NFS shares permanently

`TASK: Please ensure the following NFS shares are mounted permanently on the dev-app server.`

**STEPS TAKEN:**

1. Updated the `/etc/fstab` with the appropriate NFS entries.
2. Then ran `mount -a` and `mount | grep nfs` to confirm that the directories were mounted correctly.

[🔝 Back to Top](#-table-of-contents)

---

## 11. NFS home directory

`TASK: Since you will be using SSH in accessing multiple servers, please create a shared directory using your username and 700 permission.`

**STEPS TAKEN:**

1. Used `cd` to enter `/nfs/incoming/home` directory and then used `mkdir jlewis` to create my shared directory.
2. Then used `chown -R jlewis:jlewis jlewis/` to assign my FreeIPA username as the owner.
3. Lastly, used `chmod -R 700 jlewis/` to assign the proper permissions.

[🔝 Back to Top](#-table-of-contents)

---

## 12. Please deploy a dev webserver using configuration Template

`TASK: The web development team requires you to deploy a development web server using the NEW-YT-DEV-WEBSERVER-TEMPLATE. Please update the necessary information on the newly deployed server.`

**STEPS TAKEN:**

1. Selected my Cluster folder and clicked on "Actions" to select "New Virtual Machine."
2. For creation type, selected "Deploy from template."
3. Under "Select a Template," clicked on the "Data Center" tab and selected the NEW-YT-DEV-WEBSERVER-TEMPLATE.
4. Labeled new 'Virtual machine name' to `dev-performance-jl.procore.prod1`.
5. Selected my cluster folder as the compute resource.
6. For Storage, DS-01 was selected from the "Batch Configure" tab.
7. For Clone options, left everything as default and clicked "Finish."
8. Interrupted the GRUB process to access rescue mode via the shell (unknown template password).
9. Added password and created autorelabel file to bypass SELinux.
10. Logged into VM, enabled SSH, updated hostname, and added static connection using `nmcli`.
11. Installed FreeIPA following Ticket 5 steps and ran `id jlewis` to confirm.
12. Added DNS records (Ticket 8), created mount points (Ticket 9), and permanently mounted directories (Ticket 10).
13. Added user `procore` with: `useradd -G wheel procore` and `echo procoreplus | passwd --stdin procore`.

[🔝 Back to Top](#-table-of-contents)

---

## 13. Allow HTTP to use non-standard ports

`TASK: The network and security teams are requesting that your dev-performance web server listens on a non-standard port (8001). Please configure your server to meet this requirement and provide the link for testing.`

**STEPS TAKEN:**

1. Installed `policycoreutils` to utilize `semanage`.
2. Ran: `semanage port -a -t http_port_t -p tcp 8001`
3. Confirmed with: `semanage port -l | grep 8001`
4. Installed httpd: `dnf install httpd`
5. Started the service: `systemctl enable --now httpd`
6. Edited `/etc/httpd/conf/httpd.conf` to listen on port 8001.
7. Installed `net-tools` and confirmed with: `netstat -tuln | grep 8001`
8. Added services and port to the firewall:
   - `firewall-cmd --permanent --add-service=http`
   - `firewall-cmd --permanent --add-service=https`
   - `firewall-cmd --add-port=8001/tcp`
9. Created the link: `http://{insertipaddress}:8001/`

[🔝 Back to Top](#-table-of-contents)

---

## 14. Configure a repository

`TASK: The Development team requires you to install a third-party application that can be found on the below repository.`

**STEPS TAKEN:**

1. Added repository by using `vim epel.repo` to add the required information in `/etc/yum.repos.d`.
2. Ran `dnf clean all` and `dnf repoinfo`, then ran `dnf provides tmux` and `dnf install tmux`.

[🔝 Back to Top](#-table-of-contents)

---

## 15. Create and Copy your SSH key

`TASK: The security and network team is requesting that all users generate SSH keys to access the Ansible server and our GitLab repository.`

**STEPS TAKEN:**

1. Logged into `jlewis` account on `dev-app-jl.procore.prod1` and ran `ssh-keygen`.
2. Ran `ssh-copy-id jlewis@dev-ansible.procore.prod1` and entered password to add key.
3. Tested connection with `ssh jlewis@dev-ansible.procore.prod1`.
4. Ran `ssh-keygen` while in the `dev-ansible.procore.prod1` directory.
5. Ran `ssh-copy-id jlewis@10.1.XX.XX` and entered password.
6. Obtained SSH public key by running `cat id_ed25519.pub`.
7. Accessed GitLab → User Settings → SSH Keys → "Add New Key" and pasted both keys. Repeated for `dev-performance` server.

[🔝 Back to Top](#-table-of-contents)

---

## 16. Add Dev Servers into Ansible inventory

`TASK: To perform automated actions on our infrastructure, please add your development servers to the Ansible inventory file.`

**STEPS TAKEN:**

1. SSH'd into `dev-ansible` server and edited `/etc/hosts` by adding:
   - `10.1.XX.XX dev-app-jl.procore.prod1 dev-app-jl`
   - `10.1.XX.XX dev-performance-jl.procore.prod1 dev-perf-jl`
2. Accessed the inventory file (`/etc/ansible/hosts`) and added my ansible group `[dev-jl]`.
3. Ran `ansible -m ping dev-jl` to test ping compatibility.

[🔝 Back to Top](#-table-of-contents)

---

## 17. Patch your Dev Servers using Ansible

`TASK: In accordance with company policy, all development servers must be patched regularly. Please patch your development servers using Ansible.`

**STEPS TAKEN:**

1. Used `dnf update python3` to confirm it was installed and up to date on both servers.
2. Copied `dev-patch.yml` to `dev-patch-jl.yml` in `/opt/ansible/patching`.
3. Ran `ansible-playbook dev-patch-jl-app.yml -K` — received fatal errors related to exclusions.
4. Removed `kernel-*` exclusion and reran — resolved one error.
5. Removed `rpm-*` filter and `var=out` line; reran and achieved successful results on both servers.

[🔝 Back to Top](#-table-of-contents)

---

## 18. Please use Ansible to create the task below

`TASK: The programmers on the webmasters team want to have a shared directory for collaboration on scripting knowledge for their division on all development servers.`

**STEPS TAKEN:**

1. Attempted ad-hoc command:
   ```
   ansible dev-jl -m ansible.builtin.file -a "dest=/opt/scripts/jlewis/ state=directory owner=jlewis group=webmasters mode=775" -K
   ```
2. Command did not complete correctly due to permissions. Read `ansible --help` for Privilege Escalation options.
3. Added `-b` flag to run as root without being prompted:
   ```
   ansible dev-jl -m ansible.builtin.file -a "dest=/opt/scripts/jlewis/ state=directory owner=jlewis group=webmasters mode=775" -K -b
   ```
4. Verified both servers had the shared directory created: `ll -d /opt/scripts/jlewis/`
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
   Run with: `ansible-playbook create_shared_directory.yml -K -b`

[🔝 Back to Top](#-table-of-contents)

---

## 19. Please update the system inventory database

`TASK: For inventory purposes, please populate the system inventory database of your dev servers.`

**STEPS TAKEN:**

1. Created `git-repository.yml` in `/opt/ansible` with tasks to: install git, clone the repository, and run `host_facts.sh`.
2. Ran `ansible-playbook git-repository.yml -K -b -vv` — git installed but cloning stalled due to credential prompt.
3. Ran `git clone` manually and confirmed GitLab required authentication.
4. Updated playbook to use a Personal Access Token (PAT) for authentication.
5. Corrected the script filename to `host_fact.sh_DoNotDelete` (confirmed with Infrastructure team).
6. Used double quotes around `git_token` and `repo` values for special character handling.
7. Reran playbook — all tasks completed successfully.
8. Verified `.txt` files were generated in `/tmp` on both servers.

[🔝 Back to Top](#-table-of-contents)

---

## 20. Push the script to gitlab repo

`TASK: The development department will need to have a new version of the host_facts.sh created and uploaded to Gitlab.`

**STEPS TAKEN:**

1. Logged in as `root` on dev-app server, accessed `/root/scripts`, and ran:
   `cp host_fact.sh_DoNotDelete jlewis_host_facts.sh`
2. Appended a date command: `echo 'date >> "/tmp/$HOSTNAME.txt"' >> jlewis_host_facts.sh`
3. Initialized git repo with `git init`, staged file with `git add jlewis_host_facts.sh`.
4. Ran `git commit -m "Add jlewis_host_facts.sh"` — successfully committed.
5. Pushed with `git push -u origin master`.
6. Confirmed file appeared in GitLab repository.

[🔝 Back to Top](#-table-of-contents)

---

## 21. Spin up a Web server using a Kickstart file

`TASK: One of our clients intends to build a staging web server to launch a new product. Please set up a new VM using the naming convention provided below.`

**STEPS TAKEN:**

1. Created new VM named `stage-web-jl.procore.prod1` with all required specs.
2. Powered on VM and interrupted boot process, pressed `e` to edit boot parameters for the `linuxefi` line.
3. Added the required code for GRUB to run the kickstart configuration file and pressed `Ctrl-x` to execute.
4. Server booted successfully; corrected the default IP address to allow package installation.
5. Completed Ticket 8–10 steps to configure mount points and DNS records.

[🔝 Back to Top](#-table-of-contents)

---

## 22. Configure FreeIPA Client on the Stage Virtual Machine

`TASK: All new servers must be enrolled in our IPA server. Please enroll the staging server you just created.`

**STEPS TAKEN:**

1. Installed IPA onto staging server following Ticket 5 steps.
2. Created unique SSH key: `ssh-keygen -t rsa -C "jlewis@stage-web-jl"` and copied to dev-ansible with `ssh-copy-id`.
3. Added `stage-web-jl.procore.prod1` to Ansible inventory group and performed ping test — all successful.
4. Added public key for stage-web server to GitLab using `cat id_rsa.pub`.

[🔝 Back to Top](#-table-of-contents)

---

## 23. Disable and prevent SSH root user access to all your servers

`TASK: Disallowing root logins over SSH requires system administrators to authenticate using their own individual accounts and then escalate to root via sudo or su.`

**STEPS TAKEN:**

1. Confirmed SSH access via `jlewis` IPA account, then accessed each server as root.
2. Edited `/etc/ssh/sshd_config` and set `PermitRootLogin no`.
3. Ran `systemctl restart sshd` and `systemctl daemon-reload`.
4. Confirmed SSH as root was blocked; `su` still worked for local escalation.

[🔝 Back to Top](#-table-of-contents)

---

## 24. Restrict SSH access on all servers except Bastion Host (Rich Rule)

`TASK: The security department requests that all servers created on our infrastructure only accept SSH communication from the Bastion host.`

**STEPS TAKEN:**

1. Opened two terminal sessions per server, then allowed Bastion Host IP:
   ```
   sudo firewall-cmd --permanent --add-rich-rule='rule family="ipv4" source address="{bastionip}" port port="22" protocol="tcp" accept'
   ```
2. Removed default SSH access rules:
   - `sudo firewall-cmd --permanent --remove-port=22/tcp`
   - `sudo firewall-cmd --permanent --remove-service=ssh`
3. Reloaded firewall to apply changes.
4. Confirmed direct SSH was blocked.
5. SSH'd into Bastion server with IPA username, then successfully SSH'd into target VMs from Bastion.
6. Updated `/etc/hosts` on Bastion and added RSA SSH keys from Bastion to each server.

[🔝 Back to Top](#-table-of-contents)

---

## 25. Graylog client

`TASK: Please configure your dev-app, dev-performance and stage-web virtual machines to send logs to the Graylog server.`

**STEPS TAKEN:**

1. SSH'd into `stage-graylog` and confirmed firewall was configured to accept syslog input over UDP port 5140.
2. Created `/etc/rsyslog.d/90-graylog.conf` on each server with:
   ```
   *.* @10.1.XX.XX:5140;RSYSLOG_SyslogProtocol23Format
   ```
3. Restarted rsyslog: `sudo systemctl restart rsyslog`.
4. Logged into Graylog web interface and searched for each server to confirm logs were transmitting.

[🔝 Back to Top](#-table-of-contents)

---

## 26. Install Apache Web Server

`TASK: Please install the apache webserver to the stage-web-jl.procore.prod1-IP server. Make sure to start and enable apache.`

**STEPS TAKEN:**

1. Checked if httpd was installed: `sudo dnf info httpd` and `systemctl status httpd`.
2. Installed with: `sudo dnf install httpd -y`
3. Started and enabled: `systemctl enable --now httpd`
4. Confirmed status with: `systemctl status httpd`

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
2. Verified with `sudo firewall-cmd --list-all` and reloaded with `sudo firewall-cmd --reload`.

[🔝 Back to Top](#-table-of-contents)

---

## 28. Configure apache web content

`TASK: Please configure ariclaw web server contents on stage-web server.`

**STEPS TAKEN:**

1. Installed git: `sudo dnf install git`, then cloned: `git clone git@gitlab.com:procoreplusmd/ariclaw.git`.
2. Configured git user: `git config --global user.name "justintimejlew"`, moved repo to `/var/www/html`.
3. Accessed IP address — site not displaying content.
4. Edited `/etc/httpd/conf.d/welcome.conf` and commented out all lines.
5. Restarted Apache: `systemctl restart httpd`.
6. Site displayed content at IP address.
7. Set correct permissions on the repository folder and created `/etc/httpd/conf.d/ariclaw.conf`.
8. Restarted httpd, cleared browser cache, and confirmed site loaded correctly.

[🔝 Back to Top](#-table-of-contents)

---

## 29. Update web content for ariclaw

`TASK: Ariclaw has recently changed their phone number. Please update the website content.`

**STEPS TAKEN:**

1. Located phone number in two places on the site.
2. Accessed `/var/www/html` and `/nfs/incoming/vhosts/ariclaw/htdocs` to update `contact.html` with the new phone number.
3. Ran `sudo systemctl restart httpd` and confirmed the updated number appeared on the site.

[🔝 Back to Top](#-table-of-contents)

---

## 30. Install MariaDB

`TASK: The development team requested the installation of MariaDB version 10.3 on your dev-app-jl.procore.prod1-IP server.`

**STEPS TAKEN:**

1. Created and configured the MariaDB repository: `sudo vi /etc/yum.repos.d/MariaDB.repo`
2. Installed server and client: `sudo dnf install MariaDB-server MariaDB-client`
3. Started and enabled: `sudo systemctl enable --now mariadb`
4. Ran the secure installation script: `sudo mariadb-secure-installation`
5. Verified login with: `mysql -u root -p`

[🔝 Back to Top](#-table-of-contents)

---

## 31. Create a snapshot of your VM

`TASK: The infrastructure team will perform a company wide maintenance next week. Please create a snapshot of all your Virtual Machines.`

**STEPS TAKEN:**

1. Accessed vSphere Client and clicked on each VM to access the "Snapshots" tab.
2. Clicked "Take Snapshot…" and named each snapshot respective to the server and Ticket 31.
3. Waited for all VM snapshots to complete successfully.

[🔝 Back to Top](#-table-of-contents)

---

## 32. Register your VMs to Foreman

`TASK: The Security Team is requiring that all servers be registered with the Foreman server and patched accordingly moving forward.`

**STEPS TAKEN:**

1. SSH'd into `stage-foreman` VM — was unable to access due to firewall restrictions.
2. Updated `/etc/ssh/sshd_config` to allow root login and ran `ssh-copy-id -i ~foreman-proxy/.ssh/id_rsa_foreman_proxy.pub 10.1.XX.XX` for each VM.
3. Installed subscription-manager: `curl --insecure --output katello-ca-consumer-latest.noarch.rpm`
4. Installed Katello CA cert: `sudo dnf localinstall katello-ca-consumer-latest.noarch.rpm`
5. Registered with: `subscription-manager register --org="Procore" --activationkey="XXXXXX"`
6. Verified registration in Foreman Web UI under Hosts → Content Hosts.

[🔝 Back to Top](#-table-of-contents)

---

## 33. Run remote command from Foreman

`TASK: The Security Team needs to create a local user on all the VMs of the infrastructure using Foreman. The user's name is Reuben Camilo, the username would be rcamilo.`

**STEPS TAKEN:**

1. Navigated to Foreman hosts page, filtered for my VMs, selected all 3, and clicked "Schedule Remote Job."
2. Added command `useradd -C "Reuben Camilo" rcamilo` — all jobs failed.
3. Identified issue: used wrong flag `-C` instead of `-c`. Reran with corrected command.
4. Identified secondary issue: `PermitRootLogin` was set to `no`. Set all servers back to `yes`.
5. Reran job — all 3 VMs showed successful.

[🔝 Back to Top](#-table-of-contents)

---

## 34. Create a central location for logs

`TASK: We would like to establish a central location on the server dev-app-jl.procore.prod1-IP to store logs.`

**STEPS TAKEN:**

1. Powered off `dev-app-jl.procore.prod1`, added a new 1 GB hard disk in vSphere, and powered back on.
2. Confirmed disk at `/dev/sdb` using `lsblk`.
3. Used `fdisk /dev/sdb` to create partition.
4. Created `ext4` filesystem via VG and LV.
5. Created mount point: `mkdir -p /lfjs/logs`
6. Created local user `lfjs` and assigned ownership: `sudo chown -R lfjs:webmasters /lfjs/logs`
7. Set SGID permissions: `sudo chmod 2755 /lfjs/logs/`
8. Edited `/etc/fstab` to mount persistently and confirmed with `lsblk`.

[🔝 Back to Top](#-table-of-contents)

---

## 35. Users are having issues with SSH

`TASK: We have received numerous emails from developers regarding issues with SSH access to your dev-app server. Please investigate the issue and attach the last 20 lines of the logs to this ticket.`

**STEPS TAKEN:**

1. Used `id apprentice` to confirm user existed, then attempted `ssh apprentice@localhost`.
2. Attempted to access `/lfjs/logs` as `apprentice` — permissions had reset to root.
3. Re-applied correct permissions and confirmed as `apprentice` via `su`.
4. Checked `/var/log`, `tallylog`, and `lastlog` — nothing notable found.
5. Ran `find / -type f -user apprentice | grep ssh` and reviewed all 3 files — noted similar keys in `known_hosts` and `known_hosts.old`.
6. Exited `apprentice` and checked `/var/log/secure` for the last 20 lines — found that user `apprentice` was not using port 22 for SSH.

[🔝 Back to Top](#-table-of-contents)

---

## 36. Users are reporting repo issues

`TASK: One of our clients has reported that the del.extreme-ix repository is not functioning properly on dev-app-[initials].procore.prod1-IP.`

**STEPS TAKEN:**

1. Accessed the `epel.repo` file — noted that `enabled=1` was included during original setup (not part of original instructions).
2. Reviewed the URL and noted it may require `https` — not confirmed as the root issue at time of investigation.

[🔝 Back to Top](#-table-of-contents)

---

## 37. User is having issue in accessing file

`TASK: User created in ticket 6 has reported that he/she is unable to write to the directory /lfjs/logs when logged into dev-app-[initials].procore.prod.`

**STEPS TAKEN:**

1. `msoriano` is part of the webmasters group but still unable to write. Created an ACL:
   ```
   sudo setfacl -m u:msoriano:rw /lfjs/logs
   ```

[🔝 Back to Top](#-table-of-contents)

---

## 38. Urgent! Malicious IP

`TASK: The networking team has reported a malicious IP that is trying to get into our network.`

**STEPS TAKEN:**

1. Ran the following on each VM to block the malicious IP:
   ```
   sudo firewall-cmd --permanent --add-rich-rule='rule family="ipv4" source address="XX.XX.XX.XX" port port="22" protocol="tcp" drop'
   ```
2. Ran `sudo firewall-cmd --reload` to apply the new rich rule.
3. Ran `sudo firewall-cmd --list-all` to confirm the rule was applied on each VM.

[🔝 Back to Top](#-table-of-contents)

---

## 39. Please provide the apache version

`TASK: The development team is helping us troubleshoot an issue with apache on stage-web-jl.procore.prod1-IP.`

**STEPS TAKEN:**

1. Ran both `dnf list httpd` and `dnf info httpd` to obtain the version information in two formats.

[🔝 Back to Top](#-table-of-contents)

---

## 40. Get a list of all the users that have enrolled on FreeIPA

`TASK: The administration is requesting a detailed list of all users registered on the FreeIPA server. Please generate this list using IPA commands and redirect the output to a file.`

**STEPS TAKEN:**

1. Used `ipa user-find msoriano` to confirm user was in database, then ran `ipa user-del msoriano` to delete user.
2. Ran `ipa user-find >> ipa_users.txt` to export all users into a file.

[🔝 Back to Top](#-table-of-contents)

---

## 41. Please configure cronjob

`TASK: The engineering team would like to have a cron job configured on the dev-app-jl.procore.prod1-IP server.`

**STEPS TAKEN:**

1. Copied script from `/nfs/incoming/scripts/logs.sh` to `~/` and changed ownership to FreeIPA user.
2. Confirmed `crond` was running: `sudo systemctl status crond`
3. Ran `crontab -eu jlewis` and entered the cron schedule to execute every 6 hours.
4. Checked `/var/log/cron` and confirmed the script was running on schedule.

[🔝 Back to Top](#-table-of-contents)

---

## 42. Please create a cronjob

`TASK: Please create a cronjob on stage-web-jl.procore.prod1-IP server to restart apache every 2 days at 11 AM.`

**STEPS TAKEN:**

1. Set up initial cronjob as `jlewis` — failed due to authentication requirements.
2. Ran as root with `sudo crontab -eu root` and tested with a 2-minute interval.
3. Confirmed job ran in `/var/log/cron`.
4. Finalized cronjob as root:
   ```
   0 11 */2 * * systemctl restart httpd
   ```

[🔝 Back to Top](#-table-of-contents)

---

## 43. Create NAGIOS user and configure access

`TASK: To utilize the NAGIOS service, you need to create an HTTP user on the server.`

**STEPS TAKEN:**

1. SSH'd into `dev-nagios` server.
2. Added user with: `htpasswd /usr/local/nagios/etc/htpasswd.users jlewis`
3. Edited `/usr/local/nagios/etc/cgi.cfg` and appended `jlewis` to all directives.
4. Restarted Nagios: `sudo systemctl restart nagios`
5. Verified user access by logging into the Nagios web UI.

[🔝 Back to Top](#-table-of-contents)

---

## 44. Add the servers to Nagios

`TASK: Please add your Virtual machines to Nagios monitoring system.`

**STEPS TAKEN:**

1. Installed NRPE and Nagios plugins on each server:
   ```
   sudo dnf install epel-release nrpe nagios-plugins-{load,http,users,procs,disk,swap,nrpe,uptime} -y
   ```
2. Edited `/etc/nagios/nrpe.cfg` and updated `allowed_hosts` to include the Nagios server IP.
3. Started NRPE: `sudo systemctl enable --now nrpe.service`
4. Copied `yt-templates.cfg.bak` for each server and added host definitions for `dev-app-jl` and `stage-web-jl`.
5. Linked new config files in `/usr/local/nagios/etc/nagios.cfg`.
6. Reloaded Nagios: `sudo systemctl reload nagios.service` — received warning.
7. Ran `sudo /usr/local/nagios/bin/nagios -v /usr/local/nagios/etc/nagios.cfg` to diagnose config errors.

[🔝 Back to Top](#-table-of-contents)