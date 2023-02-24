# openbsd-desktop-playbook

Automatically setup a OpenBSD desktop (Xfce and optionally Openbox) via **Ansible**.

## USAGE:
1. Clone/download this repository
2. Unpack/cd into the directory
3. Run
```Shell
$ ansible-playbook main.yml (-Kk)
```
4. The target will reboot when the Playbook is finished running
5. Done

## NOTE:
Make sure to install python on the target before running this Playbook since Ansible needs python to be on the host to function.
```Shell
target# pkg_add python
```
Also, make sure to take a look at **vars/main.yml** to customize the Playbook.
