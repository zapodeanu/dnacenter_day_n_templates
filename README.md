# Cisco DNA Center Templates

This repo will be used for the proof of concept Cisco DNA Center GitOps operations.

Users will create new YAML files using these requirements: 

```yaml

project_name: template project name
template_name: template name
filter: one of these options - hostname, device_family, role, site, version, device_ip
filter_value: the value for the above filter
cli_template: |
  !
  cli command 1
  cli command 2
  ...
  !

```

device_family, role, version and site params must match the Cisco DNA Center device list API response parameters.

Sample files:

```yaml

project_name: Ansible_Project
template_name: Ansible_Template
filter: device_family
filter_value: Cisco Cloud Services Router 1000V
cli_template: |
  !
  no snmp-server host 10.93.135.30 version 2c RO
  no snmp-server host 10.93.130.50 version 2c RW
  !
  ntp server 171.68.48.78
  no ntp server 171.68.48.80

```

```yaml

project_name: Ansible_Project
template_name: Ansible_Template
filter: role
filter_value: ACCESS
cli_template: |
  !
  no snmp-server host 10.93.135.30 version 2c RO
  no snmp-server host 10.93.130.50 version 2c RW
  !
  ntp server 171.68.48.78
  no ntp server 171.68.48.80

```