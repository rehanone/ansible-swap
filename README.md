ansible-swap
============

An ansible role for managing the swap file on Linux systems.

Requirements
------------

This role requires standard Linux ext4 based filesystem as root.

Role Variables
--------------

The following variables will change the behavior of this role (default values
are shown below):

```yaml
# The swap file used
swap_file_path: '/swap.img'
```

Example Playbook
----------------

```yaml
- hosts: all
  roles:
    - role: rehanone.swap
      vars:
        swap:
          debug: true
          state: present
          file: '/swap.img'
          size: 512
          swappiness:
            value: 60
            file: '/etc/sysctl.d/50-vm-swappiness.conf'
      when: swap_manage
```

License
-------

Apache-2.0
