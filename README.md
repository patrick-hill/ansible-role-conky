Ansible Role: Conky & Conky Manager
=========

[![Build Status](https://travis-ci.org/patrick-hill/ansible-role-conky.svg?branch=master)](https://travis-ci.org/patrick-hill/ansible-role-conky)
[![Ansible Galaxy](https://img.shields.io/badge/ansible--galaxy-patrick--hill.conky-blue.svg)](https://galaxy.ansible.com/patrick-hill/conky)


Installs [Conky](https://github.com/brndnmtthws/conky) and [Conky Manager](http://www.teejeetech.in/p/conky-manager.html) on Debian based OS. 
Allows for the use of a backup of the configs (.conky dir) to be restored.


Requirements
------------

Ansible 1.6+

Role Variables
--------------

    conky_use_backup: true
"conky_use_backup" determines if a backup should be used

    conky_dir: "/home/{{os_username}}/.conky"
"conky_dir" defines conky's config directory and is set to the default

    conky_config_file: "/home/{{os_username}}/.config/conky-manager.json"
"conky_config_file" is the default config json file

    conky_backup_conky_manager_file: "{{backup_dir_root}}/configs/conky/conky-manager.json"
"conky_backup_conky_manager_file" is the path to the backed up config you'd like to restore

Dependencies
------------

None.

Example Playbook
----------------

    - hosts: localhost
      gather_facts: yes
      vars:
        os_username: 'Your_OS_Username'
      roles:
         - role: patrick-hill.conky

*Inside `defaults/main.yml`*:

    conky_use_backup: true
    
    conky_dir: "/home/{{os_username}}/.conky"
    conky_config_file: "/home/{{os_username}}/.config/conky-manager.json"
    conky_backup_conky_manager_file: "{{backup_dir_root}}/configs/conky/conky-manager.json"
    
License
-------

BSD

Author Information
------------------

Role written in 2016 by [Patrick Hill](http://www.HillsPCWorld.com) 
