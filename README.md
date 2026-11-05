# ubuntu-hardening-ansible
Automated Ubuntu Server hardening using Ansible, with before/after Lynis scoring.
The goal of this project was to take a blank ubuntu server and make it more secure with Ansible, using Lynis as a measuring tool.
## Results
| Stage | Lynis hardening index | Ansible changes |
|---|---|---|
| Fresh Ubuntu Server 24.04 (clean snapshot) | 57 | n/a |
| After running the playbook once | 64 | 11 changed |
| Playbook run a second time | n/a | 0 changed |

The second run making zero changes shows the playbook is idempotent: it only changes what's out of line.
## What is in it
Firewall : Was configured to block all traffic and only allow SSH, so server can be accessed remotely.
Accounts: sets password aging rules 90 day maximum ,1 day minimum with 7 day warning before password expire. 
Fail2ban: a temparary ban on an IP after 5 failed login attempts , 1 hr ban
Updates: install unattended upgrades so security patches are automatically applied
sysctl: hardens the network settings , so server does not forward traffic working along with the firewall
## what I didnt fix
Smaller security controls: separate disks, and usb storage 
The goal of this was not to get a perfect score but to understand how to reduce an attack surface. 
