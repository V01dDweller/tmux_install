# Install tmux from source #

This ansible playbook installs tmux from the source-master on Debian/Ubuntu or RHEL7/CentOS7.

* assumptions:
    * sudo-to-root with NOPASSWD.
    * internet connection with no proxy
* installs the following pre-requisite packages from primary yum/apt repos:
    * automake
    * gcc
    * git
    * ncurses-devel/libncurses5-dev
* installs libevent-devel from rpmfind.pbone.net for RHEL/CentOS since this is not avaiable without supplemental repos
* Installs tmux to /usr/local/bin
* adds /usr/local/bin to the global PATH for RHEL/CentOS
* Uses /usr/src/tmux as the working directory
* Does not clean up /usr/src after itself (may add that later)

## Usage ##

`ansible-playbook -i <your-inventory>.ini tmux_install.yml`

**Playbook Contents**

```
tmux_install
├── README.md       # You are here
├── ansible.cfg
├── roles
│   ├── install_dependencies
│   │   └── tasks
│   │       └── main.yml
│   ├── install_libevent_devel
│   │   └── tasks
│   │       └── main.yml
│   └── install_tmux
│       ├── files
│       │   └── tmux.sh
│       ├── meta
│       │   └── main.yml
│       └── tasks
│           └── main.yml
└── tmux_install.yml
```
