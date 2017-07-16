# Install tmux from source #

This ansible playbook installs tmux from source on RHEL7/CentOS7 since those distributions only provide the ancient tmux 1.8. The playbook:

* assumes sudo-to-root with NOPASSWD.
* installs the following pre-requisite packages from primary yum repos:
    * automake
    * gcc
    * git
    * ncurses-devel
* installs libevent-devel from rpmfind.pbone.net since this is not avaiable without supplemental repos
* adds /usr/local/bin to the global PATH

## Usage ##

`ansible-playbook -i <your-inventory>.ini tmux_install.yml`

Tested successfully against a EC2 RHEL7 instance.

```
tmux_install
│
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
│       └── tasks
│           └── main.yml
└── tmux_install.yml
```

10 directories, 6 files
