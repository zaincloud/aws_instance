# AWS Instance Playbook

This playbook sets up an AWS instance using Ansible.

## Requirements

No special requirements; note that this role requires root access, so either run it in a playbook with a global `become: true`, or invoke the role in your playbook like:

```yaml
- hosts: localhost
  roles:
    - role: aws_instance
      become: true

