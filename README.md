# Ansible role: rsyslog
System log with filtering and remote logging.

## Requirements
Only tested on Debian stable, for now.

## Role Variables
+ `rsyslog_servers` (default: localhost): list of servers to send logs to
+ `rsyslog_port` (default: 2514): port
+ `rsyslog_file` (default: /var/log/messages): where to store local logs
+ `rsyslog_server_group` (default: log) ansible inventory group of servers

### Only used by server:
+ `rsyslog_tags`: list of keywords, each to be stored in a separate log file
+ `rsyslog_rules`: dictionary of additional rules for the rsyslog config


## Dependencies
None.

## Example Playbook

```
- hosts: rsyslog
  roles:
    - { role: ho-ansible.rsyslog }
```

## License
MIT

## Author Information
Sean Ho, https://github.com/ho-ansible/
