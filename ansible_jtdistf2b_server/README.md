Install distributed fail2ban server
=========

Install distributed fail2ban server

Any pre-requisites that may not be covered by Ansible itself or the role should be mentioned here. For instance, if the role uses the EC2 module, it may be a good idea to mention in this section that the boto package is required.

Role Variables
--------------

installer will prompt for 

```
    mysql_root_password the root password for mysql

    db_user  username for api to access databased

    db_pass  password for api to access database
    
    api_port which port the web service runs on

    htaccess_username username for access to web page showing bans

    htaccess_password password for access to web page showing bans
```

Dependencies
------------

Needs mysql and apache on target server

Example Playbook
----------------

```
To aim at a specific host do this

ansible-playbook -i jt_setup_distf2b_server.yml 192.168.1.10, -K
```

 Note using an ad hoc inventory of just giving it an ip number
and note that comma after the ip (its looking for a list )
The -K will prompt for the sudo password

License
-------

BSD

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
