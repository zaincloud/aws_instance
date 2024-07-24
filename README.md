# AWS Instance Playbook

This playbook sets up an AWS instance using Ansible.

```yaml
---

- hosts: localhost
  become: true
  roles:
    - aws_instance
