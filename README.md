# Ansible Installers for Shared Fail2 Ban

Ansible installer scripts for fork of sharedfail2ban project.

see  [GitHub - ninelocks/Shared-Fail2Ban](https://github.com/ninelocks/Shared-Fail2Ban)

(see also [GitHub - bulgemonkey/Shared-Fail2Ban](https://github.com/bulgemonkey/Shared-Fail2Ban) )

3 ansible installer scripts  

- ansible_jtdistf2b_client install shared fail2ban client

- ansible_jtdistf2b_server install shared fail2ban server

- ansible_jtlamp install apache/mysql/php/phpmyadmin

The idea being these will give you all you need to setup a test system

To use the installer  cd into relevent installer and run the playbook that is there.
So for example to install  the client on ip address  192.168.1.248

```
cd ansible_jtdistf2b_client
ansible-playbook jt_setup_distf2b_client.yml -i 192.168.1.248, -K
```

Note using an ad hoc  inventory of just giving it an ip number
and note that comma after the ip   (its looking for a list )
The -K will prompt for the sudo password
Each of the scripts will prompt for any variables it needs. The installer script main action is in 
tasks/main.yml

## Layout of Roles

The layout of each of the folders is shown below and not all the main.ymls are used, eg vars/main.yml not used

#### ansible_jtlamp layout

> └── ansible_jtlamp\
>     ├── jt_setuplamp2021.yml \
>     ├── README.md \
>     └── roles \
>         └── jtlamp \
>             ├── defaults \
>             │└── main.yml \
>             ├── files \
>             │├── index.html \
>             │└── pylon.jpg \
>             ├── handlers\
>             │└── main.yml\
>             ├── meta\
>             │└── main.yml\
>             ├── tasks\
>             │└── main.yml\
>             ├── templates\
>             │├── 000-default.conf.j2\
>             │├── default-ssl.conf.j2\
>             │├── my.cnf.j2\
>             │├── owncloud_apache.j2\
>             │├── phpmyadmin.conf.j2\
>             │
>             ├── tests\
>             │├── inventory\
>             │└── test.yml\
>             └── vars\
>                 └── main.yml\

#### ansible_jtditsf2b_client layout

> ansible_jtdistf2b_client folder layout
> ├── ansible_jtdistf2b_client\
> ├── jt_setup_distf2b_client.yml\
> ├── README.md\
> └── roles\
>     └── jtdistf2b_client\
>         ├── defaults\
>         │└── main.yml\
>         ├── files\
>         │├── jail.local\
>         │├── jail-sf2b-apache-noscript.local\
>         │├── jail-sf2b-ssh.local\
>         │└── test_sending.sh\
>         ├── handlers\
>         │└── main.yml\
>         ├── meta\
>         │└── main.yml\
>         ├── tasks\
>         │└── main.yml\
>         ├── templates\
>         │└── shared_cfg.py.j2\
>         ├── tests\
>         │├── inventory\
>         │└── test.yml\
>         └── vars\
>             └── main.yml\

#### ansible_jtlamp directory layout

> ├── ansible_jtdistf2b_server\
> ├── jt_setup_distf2b_server.yml\
> ├── README.md\
> └── roles\
>     └── jtdistf2b_server\
>         ├── defaults\
>         │└── main.yml\
>         ├── files\
>         │├── base-server.sql\
>         │├── f2bweb\
>         ││└── index.php\
>         │└── httpd.conf\
>         ├── handlers\
>         │└── main.yml\
>         ├── meta\
>         │└── main.yml\
>         ├── tasks\
>         │└── main.yml\
>         ├── templates\
>         │├── api_cfg.py.j2\
>         │├── api.wsgi.j2\
>         │├── config.php.j2\
>         │└── forwebserver\
>         │    ├── api.conf.j2\
>         │    ├── api.conf.original\
>         │    ├── api.conf.v1.j2\
>         │    └── api.conf-withwebpage\
>         ├── tests\
>         │├── inventory\
>         │└── test.yml\
>         └── vars\
>             └── main.yml\
