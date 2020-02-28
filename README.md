# Ansible role: rsyslog
System log with filtering and remote logging.

## Requirements
Only tested on Debian stable, for now.

## Role Variables
+ `rsyslog_role` (default: client): either `client` (sender) or `server` (receiver)
+ `rsyslog_server` (default: localhost): DNS name or IP address to send RELP logs to
+ `rsyslog_port` (default: 2514): port to send RELP messages to
+ `rsyslog_file` (default: /var/log/messages): local file to copy logs to

### Role Variables for Server
+ `rsyslog_listen` (default: lo): network interface on which to listen
+ `rsyslog_tags` (default: none): list of systemd services for which logs should be split into separate files
+ `rsyslog_rules` (default: none): dict of custom rules

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
