# Ansible role: rsyslog
System log with filtering and remote logging.
Server listens on udp/514 and tcp/514 for standard syslog, and tcp/2514 for RELP.

## Requirements
Only tested on Debian stable, for now.

## Role Variables
+ `rsyslog_role` (default: client): either `client` (sender) or `server` (receiver)
+ `rsyslog_server` (default: localhost): DNS name or IP address to send RELP logs to
+ `rsyslog_port` (default: 2514): port to send RELP messages to
+ `rsyslog_file` (default: /var/log/messages): local file to copy logs to
+ `rsyslog_host_pattern` (default: `/var/log/%HOSTNAME%/%programname%.log`):
  where to store remote logs

### Role Variables for Server
+ `rsyslog_interface` (default: lo): network interface on which to add firewall rules,
  or empty string for all interfaces
+ `rsyslog_address` (default: `127.0.0.1`): IP address on which to listen,
  or empty string for all interfaces
+ `rsyslog_tags` (default: none): list of systemd services for which logs should be split into separate files
+ `rsyslog_rules` (default: none): dict of custom rules

## Playbooks
+ `main.yml`: apply dnsmasq role
+ `uninstall.yml`: remove dnsmasq. Run before removing config from inventory.

## Dependencies
+ [ho-ansible.systemd](https://github.com/ho-ansible/systemd)

## License
+ Ansible role licensed [MIT](LICENSE)

## Author Information
+ Ansible role by [Sean Ho](https://github.com/ho-ansible/)
