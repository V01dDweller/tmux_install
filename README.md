# tmux_install

![Ansible Role](https://img.shields.io/ansible/role/d/v01ddweller/tmux_install)
![GitHub commit activity](https://img.shields.io/github/commit-activity/t/v01dDweller/tmux_install)

**Last update:** 7/31/2022

This role installs tmux from the source-master on Debian/Ubuntu or
RHEL7/CentOS7. Primarily intended for RHEL 7/CentOS 7 or Ubuntu 16.04+
which default to old Tmux versions. This also works well on Ubuntu 19.04.

## Requirements

* Internet connection

## Dependencies

None.

## Example Usage

**1. Install the role**

```
ansible-galaxy install V01dDweller.tmux_install
```

This installs the role in ~/.ansible/roles

**2. Create a short playbook**

Create tmux_install.yml:

```yaml
# file: tmux_install.yml
---
- name: Install tmux
  hosts: localhost
  connection: local
  become: true
  roles:
     - role: V01dDweller.tmux_install
       tags: tmux
...
```

**3. Run the Playbook**

```cmd
ansible-playbook tmux_install.yml
```

**4. Validate**

```
bash-4.2$ tmux -V
tmux 3.1-rc
```

## License

BSD

## Author Information

By V01dDweller
