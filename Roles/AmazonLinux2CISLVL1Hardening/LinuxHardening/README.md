Role Name
=========
LinuxHardening

This role is designed to harden a brand new Amazon Linux 2 instance and get almost to 100% compliantper CIS Benchmark for Amazon Linux 2 v2.0.0 Level 1.

Requirements
------------
This role does make some changes that are favorable for a Raytheon asset. Such as setting the Raytheon proxy variables and importing the Raytheon Cert bundle. It also uninstalls the ssm-agent that comes with Amazon Linux 2 by default since selinux complains about it being an unconfined service. If you don't like these changes please comment them out or remove them altogether.

Find the ssm action in LinuxHardening/tasks/special_services.yml (Line 23)

Find the Raytheon Actions in LinuxHardening/tasks/ray_hygiene.yml

Role Variables
--------------

There's only one variable in this role, and it simply uses a command combined with awk to capture a list of local users.

Dependencies
------------

Connectivity to the Amazon repo's. My inventory file had defined the path to my ssh key. So your's  should look similiar to below:
 
[servers]
192.168.168.168
[servers:vars]
ansible_ssh_private_key_file=/opt/key.pem


Example Playbook
----------------

To use this role just create a your playbook with content like below and that should get you going.

---

- hosts: servers
  become: true
  roles:
    - LinuxHardening

License
-------

BSD

Author Information
------------------
Adalberto Sanchez
https://github.com/asanc115/asanc115 (Maybe one day this will be full of stuff)
