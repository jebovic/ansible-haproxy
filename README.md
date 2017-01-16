HAProxy
=======

[![Build Status](https://travis-ci.org/jebovic/ansible-haproxy.svg?branch=master)](https://travis-ci.org/jebovic/ansible-haproxy) [![Ansible Galaxy](https://img.shields.io/badge/galaxy-jebovic.haproxy-blue.svg?style=flat)](https://galaxy.ansible.com/jebovic/haproxy)

Install and configure HAProxy

This role is a part of my [OPS project](https://github.com/jebovic/ops), follow this link to see it in action. OPS provides a lot of stuff, like a vagrant file for development VMs, playbooks for roles orchestration, inventory files, examples for roles configuration, ansible configuration file, and many more.

Compatibility
-------------

Tested and approved on :

* Debian jessie (8+)
* Ubuntu Trusty (14.04 LTS)
* Ubuntu Xenial (16.04 LTS)

Role Variables
--------------

```yaml
# Global configuration
haproxy_config_file: /etc/haproxy/haproxy.cfg

# UI configuration
haproxy_enable_ui: yes
haproxy_ui_user: haproxy_user
haproxy_ui_password: haproxy

# Custom configuration
haproxy_custom_config: no
```

Example Playbook
----------------

```yaml
- hosts: servers
  roles:
     - { role: jebovic.haproxy }
```

Example : config
----------------

```yaml
# disable web UI
haproxy_enable_ui: no
# custom config
haproxy_custom_config: |
                        frontend localnodes
                            bind *:80
                            mode http
                            default_backends nodes
```

Tags
----

* haproxy_config : only update config and restart service

License
-------

MIT

Author Information
------------------

Jérémy Baumgarth https://github.com/jebovic
