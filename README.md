# AWS Instance Playbook

This playbook sets up an AWS instance using Ansible.

### Introduction
This Ansible role automates the process of launching multiple EC2 instances on AWS. It is designed to be simple and efficient, leveraging Ansible's capabilities to manage cloud infrastructure.

### Requirements
No special requirements; note that this role requires root access, so either run it in a playbook with a global `become: true`, or invoke the role in your playbook like:

```yaml
- hosts: localhost
  roles:
    - role: aws_instance
      become: true
```

### Role Variables
The following variables are defined in `vars/main.yml`:

- `AWS_ACCESS_KEY`: Your AWS access key.
- `AWS_SECRET_KEY`: Your AWS secret key.
- `instance_type`: The type of instance to launch (default: `t2.micro`).
- `image`: The AMI ID to use for the instance.
- `region`: The AWS region to launch the instance in.
- `security_group`: The security group to associate with the instance.
- `key_name`: The key pair name to use for SSH access.
- `Total_Instances`: The number of instances to launch.

### Example Playbook
Here is an example of how to use this role in a playbook:

```yaml
- hosts: localhost
  roles:
    - role: aws_instance
      become: true
```

### Author Information
This role was created by Mohammed Zainul Abid. For any issues or contributions, please reach out via 
- ***Phone***: +91 7899266604.
- ***Mail***: zaintheorem@gmail.com.

### Tasks
The main tasks for this role are defined in `tasks/main.yml`:

- **Launch an EC2 instance**: Uses the `amazon.aws.ec2_instance` module to launch instances.
- **Extract details**: Uses `set_fact` to extract instance details.
- **Debug the values**: Outputs the instance details for verification.

### Additional Information
For more details on the `amazon.aws.ec2_instance` module, refer to the [Ansible documentation](https://docs.ansible.com/ansible/latest/collections/amazon/aws/ec2_instance_module.html).
