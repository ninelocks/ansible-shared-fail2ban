Install distributed fail2ban client
=========

Install variation of  https://github.com/bulgemonkey/Shared-Fail2Ban 
from https://github.com/ninelocks/Shared-Fail2Ban onto a client machine

Requirements
------------

Client machine ubuntu   or centos 7

Role Variables
--------------

installer will prompt for

```
    mysql_root_password

    db_user  username for api to access databased

    db_pass  password for api to access database
    
    api_url address of database server
    
    api_token the token used to identify the client (see shared fail2ban project notes)

    api_or_sql whether clinet access DB directly or via api call

    api_port which port number the api runs on
```

Dependencies
------------

Example Playbook
----------------

```
To aim at a specific host do this

ansible-playbook -i jt_setup_distf2b_client.yml  192.168.1.10, -K
```

Note using an ad hoc inventory of just giving it an ip number
and note that comma after the ip (its looking for a list )
The -K will prompt for the sudo password

License
-------

BSD

Author Information
------------------
