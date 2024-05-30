# openbsd-desktop-playbook

Automatically setup a **OpenBSD** desktop (**Xfce**) via **Ansible**.

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
rcctl
xenodm
reboot
```

## NOTE:
If **Python** is not already installed on the destionation host, you can run the supplied **bootstrap.yml** **Playbook** to do just that.
```Shell
$ ansible-playbook bootstrap.yml (-Kk)
```

**xenodm** is not enabled by default. You can change this by setting **xenodm_enable** to **true** (Under **vars/main.yml**)

Also, make sure to take a look at **vars/main.yml** to customize the Playbook.
