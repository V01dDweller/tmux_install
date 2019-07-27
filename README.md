# Install Tmux 2.8 from source #

This playbook installs tmux from the source-master on Debian/Ubuntu or
RHEL7/CentOS7. Primarily intended for RHEL 7/CentOS 7 or Ubuntu 16.04
LTS which default to old Tmux versions.

* Assumptions:
    * sudo-to-root with NOPASSWD.
    * internet connection with no proxy
* Installs the following pre-requisite packages from primary yum/apt repos:
    * automake
    * gcc
    * git
    * ncurses-devel/libncurses5-dev
* Installs libevent-devel from rpmfind.pbone.net for RHEL/CentOS since
  this is not avaiable without supplemental repos
* Installs tmux to /usr/local/bin
* Adds /usr/local/bin to the global PATH for RHEL/CentOS
* Uses /usr/src/tmux as the working directory

## Usage ##

`ansible-playbook -i <your-inventory>.ini tmux_install.yml`

**Playbook Contents**

```
tmux_install
├── roles
│   ├── dependencies
│   │   └── tasks
│   │       └── main.yml
│   ├── libevent_devel_install
│   │   └── tasks
│   │       └── main.yml
│   └── tmux_install
│       ├── files
│       │   └── tmux.sh
│       ├── meta
│       │   └── main.yml
│       └── tasks
│           └── main.yml
├── ansible.cfg
├── README.md            # You are here
└── tmux_install.yml
```
