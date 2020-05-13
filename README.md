rd-ansible-ntp  [![Build Status](https://travis-ci.org/bbc/rd-ansible-ntp.svg?branch=master)](https://travis-ci.org/bbc/rd-ansible-ntp)
=========

This module installs and configures NTP. If the configuration changes it forces the server to do a forced ntpdate command and restarts the ntp service

Requirements
------------

This module requires Ansible 2.x

Role Variables
--------------

See defaults for variables and descriptions

Example Playbook
----------------

Example to call:

    - hosts: all
      vars:
        ntp_install_ntp_servers:
          - ntp0.server.org
          - ntp1.server.org

      roles:
         - { role: rd-ansible-ntp }
