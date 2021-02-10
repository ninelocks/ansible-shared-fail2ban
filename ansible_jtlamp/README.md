Install lamp
=========

A very basic installer for apache(or httpd),mysql,php,phpmyadmin

Requirements
------------

Target machine is centos 7 or ubuntu 20

Role Variables
--------------

```
    mysql_root_password password to give to the mysql instance

    admin_ip  ip address from which phpmyadmin can be accessed

    
```

Dependencies
------------

## Example Playbook

    To aim at a specific host do this
    
    ansible-playbook -i jt_setuplamp2021.yml 192.168.1.10, -K

Note using an ad hoc inventory of just giving it an ip number
and note that comma after the ip (its looking for a list )
The -K will prompt for the sudo password

License
-------

BSD

Author Information
------------------
