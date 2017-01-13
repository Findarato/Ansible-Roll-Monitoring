# Ansible Role: Monitoring

[![Build Status](https://travis-ci.org/Findarato/Ansible-Roll-Monitoring.svg?branch=master)](https://travis-ci.org/Findarato/Ansible-Roll-Monitoring) [![Code Climate](https://codeclimate.com/github/Findarato/Ansible-Roll-Monitoring/badges/gpa.svg)](https://codeclimate.com/github/Findarato/Ansible-Roll-Monitoring)

## Requirements

There are no requirements for this role. Other than EPEL for some extra packages. If firewalld or UFW is not installed it will be installed for easier managing of the firewall rules.

## Role Variables

```yml
nagiosPlugins:
    - nagios-nrpe
    - nagios-plugins-swap
    - nagios-plugins-users
    - nagios-plugins-procs
    - nagios-plugins-load
    - nagios-plugins-disk
    - nagios-plugins-ntp

nrpeInfo:
    port: 5666
    user: nrpe
    group: nrpe
    allowedHosts: [127.0.0.1, 192.168.1.33]

# This are global definitions and should be mapped in host_vars
# This is just an example of how you create the host_vars

nrpeDriveMounts:
  - name: root
    path: /dev/sda1
  - name: boot
    path: /dev/sda2
  - name: home
    path: /dev/sda3
```

## Dependencies

A list of other roles hosted on Galaxy should go here, plus any details in regards to parameters that may need to be set for other roles, or variables that are used from other roles.

## Example Playbook

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

```
- hosts: servers
  roles:
     - { role: findarato.monitoring, x: 42 }
```

## License

BSD

## Author Information

Joseph Harry
