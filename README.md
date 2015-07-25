ansible_restart
====

## Overview

Setup deeplearning tool caffe development environment on ubuntu(ec2)

## Environment

* target server
  * OS: Ubuntu 14.04

## Installation

See http://docs.ansible.com/intro_installation.html

## Usage

### SSH setting on local client

1. edit hosts to ssh target server

```
$ vim hosts
```

```text:hosts
[development]
ec2-XXX-XXX-XXX-XXX.ap-northeast-1.compute.amazonaws.com ansible_connection=ssh ansible_ssh_user=ubuntu ansible_ssh_private_key_file=~/.ssh/hoge.pem
```

### Run playbook from local client

1. run playbook on local client

```
$ ansible-playbook site.yml
```

## Running results

Running result summary
Using Ansible plugin [ansible-profile](https://github.com/jlafon/ansible-profile)

```
PLAY RECAP ********************************************************************
development | wait for SSH port up ------------------------------------- 55.25s
development | touch file ------------------------------------------------ 2.06s
development | reboot! --------------------------------------------------- 0.38s
development | wait for SSH port down ------------------------------------ 0.16s
ec2-XXX-XXX-XXX-XXX.ap-northeast-1.compute.amazonaws.com
              : ok=6    changed=3    unreachable=0    failed=0
```

## Lisence

This software is released under the MIT License, see LICENSE.
