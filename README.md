HAProxy
=======

[![Build Status](https://travis-ci.org/jebovic/ansible-haproxy.svg?branch=master)](https://travis-ci.org/jebovic/ansible-haproxy) [![Ansible Galaxy](https://img.shields.io/badge/galaxy-jebovic.haproxy-blue.svg?style=flat)](https://galaxy.ansible.com/jebovic/haproxy)

Install and configure HAProxy

Role Variables
--------------

```
# Global configuration
haproxy_config_file: /etc/haproxy/haproxy.cfg

# UI configuration
haproxy_enable_ui: true
haproxy_ui_user: haproxy_user
haproxy_ui_password: haproxy

# Custom configuration
# example
# haproxy_custom_config: |
#                         frontend localnodes
#                             bind *:80
#                             mode http
#                             default_backends nodes
haproxy_custom_config: no
```

Example Playbook
----------------

```
    - hosts: servers
      roles:
         - { role: jebovic.haproxy }
```

License
-------

MIT

Author Information
------------------

Jérémy Baumgarth https://github.com/jebovic
