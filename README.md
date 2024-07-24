---

- hosts: localhost
  become: true
  roles:
    - aws_instance
