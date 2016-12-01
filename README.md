Ansible Role: Conky & Conky Manager
=========

[![Build Status](https://travis-ci.org/patrick-hill/ansible-role-conky.svg?branch=master)](https://travis-ci.org/patrick-hill/ansible-role-conky)


Installs [Conky](https://github.com/brndnmtthws/conky) and [Conky Manager](http://www.teejeetech.in/p/conky-manager.html) on Debian based OS. 
Allows for the use of a backup of the configs (.conky dir) to be restored.


Requirements
------------

Ansible 1.6+

Role Variables
--------------

    conky_use_backup: true
"conky_use_backup" determines if a backup should be used

    os_username: "{{ lookup('env','USER') }}"
"os_username" is used for pathing. If you are logged in as another user, set your target user here

    conky_dir: "/home/{{os_username}}/.conky"
"conky_dir" defines conky's config directory and is set to the default

    conky_config_file: "/home/{{os_username}}/.config/conky-manager.json"
"conky_config_file" is the default config json file

    conky_backup_file: "{{backup_dir_root}}/configs/conky/conky-manager.json"
"conky_backup_file" is the path to the backed up config you'd like to restore

Dependencies
------------

None.

Example Playbook
----------------

    - hosts: localhost
      gather_facts: yes
      roles:
         - role: patrick-hill.conky

*Inside `defaults/main.yml`*:

    conky_use_backup: true
    os_username: "{{ lookup('env','USER') }}"
    
    conky_dir: "/home/{{os_username}}/.conky"
    conky_config_file: "/home/{{os_username}}/.config/conky-manager.json"
    conky_backup_file: "{{backup_dir_root}}/configs/conky/conky-manager.json"
    
License
-------

BSD

Author Information
------------------

Role written in 2016 by [Patrick Hill](http://www.HillsPCWorld.com) 
