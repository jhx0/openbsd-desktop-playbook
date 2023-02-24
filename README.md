# openbsd-desktop-playbook

Automatically setup a **OpenBSD** desktop (**Xfce** and optionally **OpenBox**) via **Ansible**.

## USAGE:
1. Clone/download this repository
2. Unpack/cd into the directory
3. Run
```Shell
$ ansible-playbook main.yml (-Kk)
```
4. The target will reboot when the Playbook is finished running
5. Done

## Examples
All tasks can be selected via **Tags**, so you can pick whatever tasks you want to run.   
Following, a couple of use cases:
1. Run all tasks
```Ansible
$ ansible-playbook main.yml --tags all (-Kk)
```
2. Only run a subset of tasks
```Ansible
ansible-playbook main.yml --tags "login_conf,packages,rcctl,syspatch,doas" (-Kk)
```
3. Run only one task
```
ansible-playbook main.yml --tags "syspatch" (-Kk)
```
All available **Tags**:
```Shell
login_conf
groups
doas
sysctl
firmware
syspatch
sshd
upgrade
packages
xfce
openbox
rcctl
xenodm
reboot
```

## NOTE:
Make sure to install python on the target before running this Playbook since Ansible needs python to be on the host to function.
```Shell
target# pkg_add python
```
Also, make sure to take a look at **vars/main.yml** to customize the Playbook.
