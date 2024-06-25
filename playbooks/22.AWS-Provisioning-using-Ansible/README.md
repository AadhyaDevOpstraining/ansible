https://docs.ansible.com/ansible/latest/collections/amazon/aws/index.html
https://docs.ansible.com/ansible/latest/collections/amazon/aws/ec2_instance_module.html#ansible-collections-amazon-aws-ec2-instance-module


Ansible cluster setup steps
---------------------------
1)Login As a root user first
sudo su - (OR) sudo -i

2)Update all packages
yum update -y

3)Install ansible
yum install ansible -y

5) Verify the version
ansible --version

------------------------------------------------------------------------------------------------------------
Create Normal User(ansible) in Machine 1 (Where Ansible is installing) This is important as we will use this user to perform all ansible related tasks.
 
#adduser ansible 
  (OR)
#useradd ansible

Assign a password to this user:
#passwd ansible

change /etc/sudoers permission
#chmod 755 /etc/sudoers

Give sudo access to user ansible
#vi /etc/sudoers

ansible ALL=(ALL)    NOPASSWD: ALL


Enable the PasswordAuthentication parameter to "yes":
#vi /etc/ssh/sshd_config

#/bin/systemctl restart sshd.service
    or
#service sshd restart

Login with ansible user
#sudo su - ansible

Generate ssh key
#ssh-keygen
ssh-copy-id localhost

Add server details in local host
#sudo vi /etc/ansible/hosts
localhost
