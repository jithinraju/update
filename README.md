# Simple Ansible playbook for updating Redhat and Debain based Operating systems

This playbook can be used for updating both Redhat and Debain based Operating systems. Also can be applied for groups including servers with both the OS
. 

```bash
---
- name: 'update'
  hosts: all
  become: yes
  tasks:
    - name: 'update redhat'
      when: ansible_os_family == "RedHat"
      yum:
        name: "*"
        state: latest

    - name: 'update debain'
      when: ansible_os_family == "Debian"
      apt:
        name: "*"
        state: latest
        update_cache: yes
```
