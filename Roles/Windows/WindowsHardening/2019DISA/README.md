Role Name
=========

This Role is designed to harden a Windows 2019 Server to 99% or higher from a fresh install perspective.

Requirements
------------

This role makes some changes with more favor for a RTX asset. Example: Login Banner

Role Variables
--------------

Banner Text is a variable

Dependencies
------------

Two zip files with DER Certificates included in the Role's files folder.

Example Playbook
----------------

Just run the role plain and simple. No special variables to pass.

---

- hosts: servers
  roles:
    - 2019DISA

License
-------

BSD

Author Information
------------------
 Adalberto Sanchez
 https://github.com/asanc115/asanc115 (Maybe one day this will be full of stuff)
