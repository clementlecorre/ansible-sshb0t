Ansible sshb0t
=========

Mini role for deploy [sshb0t](https://github.com/jessfraz/sshb0t) service

Requirements
------------

  * Ansible

Role Variables
--------------

```
---
# defaults file for sshb0t
sshb0t_install_dir: /usr/bin
sshb0t_version: v0.2.1
sshb0t_binary_url: "https://github.com/clementlecorre/sshb0t/releases/download/{{ sshb0t_version }}/sshb0t-linux-amd64"
sshb0t_bin_path: "{{ sshb0t_install_dir }}/sshb0t"
sshb0t_systemd_unit_template: sshb0t.service
sshb0t_systemd_unit_dest: /etc/systemd/system/sshb0t.service
sshb0t_update: yes
# Creating path for authorized_keys (sshb0t_keyfile)
sshb0t_keyfile_path: /root/.ssh
# Prams for sshb0t
sshb0t_interval: 30s
sshb0t_gituri: github.com
sshb0t_keyfile: /root/.ssh/authorized_keys
sshb0t_user:
  - "a"
  - "b"
  - "clementlecorre"
```

Dependencies
------------

Example Playbook
----------------

```
---
- hosts: all
  remote_user: root
  become: true
  roles:
    - { role: clementlecorre.ansible-sshb0t }
```

License
-------

Author Information
------------------

<clement@le-corre.eu>
