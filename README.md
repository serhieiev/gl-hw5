## Prerequisites

- 4 linux machines (VMs, instances in Digital Ocean, GCP, AWS EC2, dosen't matter);
- Python installed (2.7 or 3.5+);
- established password-less connection from one machine (controller) to others;

ps: one of machine (controller) can be a Windows 10 machine with WSL/WSL2

## Task

- Create a inventory file with four groups, each provisioning VM should be in separate group and group named `iaas` what should include childrens from two first groups;
- Create reusable roles for that:

* creating a empty file `/etc/iaac` with rigths `0500`
* fetch a linux distro name/version

- Create playbook for:

* invoke the role for `/etc/iaac` for hosts group `iaas`
* invoke the role for defining variable for all hosts
* print in registered variables
* printing hostnames together with registered variables will be a plus.

- Create a repo in your GitHub account and commit code above

Optional:

- use `ansible_user` and `ansible_password` for ssh connection and store passwords for each VM in encrypred way (add vault password to README.md in this case)

## Future reading

- [Ansible documentation](https://docs.ansible.com/ansible/latest/index.html)
- Google it!

## Testing

Testing was done with AWS EC2 instances.

File `group_vars/all.yml` is encrypted for demo purposes.

The results of execution `ansible-playbook playbook.yml --ask-vault-pass` can be found on the scrennshot below:

<img width="647" alt="gl-hw5" src="https://user-images.githubusercontent.com/12089303/209735454-6753fb17-8a3a-4674-890a-8d9249a9e0bd.png">


