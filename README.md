tmux\_install
=============

This role installs tmux from the source-master on Debian/Ubuntu or
RHEL7/CentOS7. Primarily intended for RHEL 7/CentOS 7 or Ubuntu 16.04+
which default to old Tmux versions.

**Notes:**
* This role will attempt to install libevent-devel from rpmfind.pbone.net for RHEL/CentOS since it is not otherwise avaiable without supplemental repos
* Installs tmux to /usr/local/bin
* Adds /usr/local/bin to the global PATH for RHEL/CentOS
* Uses /usr/src/tmux as the working directory

Requirements
------------
* Internet connection

Dependencies
------------

None.

Example Playbook
----------------

    ```yaml
    - hosts: servers
      roles:
         - { role: V01dDweller.tmux_install }
    ```

License
-------

BSD

Author Information
------------------

Written by V01dDweller in 2019.
