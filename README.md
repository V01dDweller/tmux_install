tmux\_install
=============

This role installs tmux from the source-master on Debian/Ubuntu or
RHEL7/CentOS7. Primarily intended for RHEL 7/CentOS 7 or Ubuntu 16.04+
which default to old Tmux versions. This also works well on Ubuntu 19.04.

**Notes:**
* This role will attempt to install libevent-devel from rpmfind.pbone.net for
  RHEL/CentOS since it is not otherwise avaiable without supplemental repos
* Installs tmux to /usr/local/bin
* Adds /usr/local/bin to the global PATH for RHEL/CentOS
* Uses /usr/src/tmux as the working directory

Requirements
------------

* Internet connection

Dependencies
------------

None.

Example Usage
----------------

**1. Install the role**
```
ansible-galaxy install V01dDweller.tmux_install
```

This installs the role in ~/.ansible/roles

**2. Create a short playbook**

Create tmux\_install.yml:

```yaml
# file: tmux_install.yml
---
- name: Install tmux
  hosts: localhost
  connection: local
  become: true
  roles:
     - role: V01dDweller.tmux_install
...
```

**3. Run the Playbook**

```cmd
ansible-playbook tmux_install.yml
```

**4. Validate**

```
bash-4.2$ tmux -V
tmux 2.8
```

License
-------

BSD

Author Information
------------------

Written by V01dDweller in 2019.
