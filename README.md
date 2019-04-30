# Ansible Role: Bootstrap
=========

## Summary

  This role performs basic configuration tasks and installs some packages to ensure that environment is
  identical on all servers in group.

## Role tasks

  - Install repository (EPEL for RedHat / CentOS)
  - Install basic packages
  - Update yum/apt cache 
  - Update packages to latest version
  - Set up timezone
  - Enable cron service

## Requirements
------------

  - Minimal Version of the Ansible for installation: 2.4
  - Supported OS:
      - RHEL
          - 6
          - 7
      - CentOS
          - 6
          - 7

## Role Variables
--------------

  Available variables are listed below along with their default values.

  ```yaml
    - bootstrap_timezone_name: UTC                # Default timezone
    - bootstrap_ntpdate_servers: "pool.ntp.org"   # NTP servers to synchronize with
    - bootstrap_yum_update_cache: True            # YUM will update its cache
    - bootstrap_yum_update_all: True              # All packages will be updated
    - bootstrap_install_development_tools: False  # Install packages from 'Development group'
    - bootstrap_redhat_common_packages: []        # Basic packages to install (see vars/common-RedHat.yml for actual values)
  ```


## Dependencies
------------

  This role has no external dependencies

## Example Playbook
----------------

```yaml
  ---

  - name: Apply role ansible-role-bootstrap to every host in group 'all'
    hosts: all
    become: True
    roles:
      - role: ansible-role-bootstrap

```


## License
-------

Apache

## Author Information
------------------

Author:
  - Max Khmelevsky <max.khmelevsky@yandex.ru>

