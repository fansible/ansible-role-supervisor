#Supervisor

An ansible role to install [Supervisor](http://supervisord.org/) and add program to supervise in a simply manner for Ubuntu (trusty).

## Requirements and dependencies

None.

##Role Variables

``` yaml
    programs_to_supervise: []
    # Name and command are the only mandatory variable,
    # check the template for a better understanding
    # programs_to_supervise:
    # - { name: top, command: "/usr/bin/top -b" }
    # - { name: top, state: stopped, command: "/usr/bin/top -b", directory: "/var/www/", autostart: true, autorestart:false, startretries:5, user: "vagrant",  }
```

Example Playbook

``` yaml
    - hosts: all
      roles:
         - ubuntu-supervisor #you may have to rename the role
      vars:
        commands_to_supervise:
            - { name: myapp, command: "/usr/bin/node /var/www/myapp/server.js" }
```


License
-------

MIT

Author Information
------------------

Maxime Thoonsen [@maxthoon](https://twitter.com/maxthoon)
