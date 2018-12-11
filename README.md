# Ansible role: prometheus-rabbitmq-exporter

Ansible role for install and configure [Prometheus RabbitMQ Exporter](https://github.com/kbudde/rabbitmq_exporter). Currently this works on Debian and RedHat based linux systems. Tested platforms are:

* Ubuntu 16.04
* Debian 9
* CentOS 7

Requirements
------------

No special requirements; note that this role requires root access, so either run it in a playbook with a global become: yes

Role Variables
--------------

The variables that can be passed to this role and a brief description about them are as follows. (For all variables, take a look at defaults/main.yml)

```yaml
rabbitmq_exporter_version: 0.29.0
```
version for installation

```yaml
rabbitmq_exporter_listen_address: "0.0.0.0"
rabbitmq_exporter_listen_port: 9419
```
listen address and port

```yaml
rabbitmq_exporter_root_dir: /opt/rabbitmq_exporter
```
directory for installation

```yaml
rabbitmq_exporter_system_group: "rabbitmq-exp"
rabbitmq_exporter_system_user: "{{ rabbitmq_exporter_system_group }}"
```
user and group for service

```yaml
# see https://github.com/kbudde/rabbitmq_exporter#configuration
rabbitmq_exporter_config_vars: |
  RABBIT_URL=http://127.0.0.1:15672
  RABBIT_USER=guest
  RABBIT_PASSWORD=guest
```
config variables

Dependencies
------------

None

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

```yaml
- hosts: app
  become: yes
  roles:
      - mbaran0v.prometheus-rabbitmq-exporter
```

License
-------

MIT / BSD

Author Information
------------------

This role was created in 2018 by Maxim Baranov.
