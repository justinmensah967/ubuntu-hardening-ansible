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
