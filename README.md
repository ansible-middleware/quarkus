# Quarkus collection for Ansible - middleware_automation.quarkus collection

[![Build Status](https://github.com/ansible-middleware/quarkus/actions/workflows/ci.yml/badge.svg?branch=main)](https://github.com/ansible-middleware/quarkus/actions/workflows/ci.yml)

## About

This Ansible collection provides support to build and deploy a Quarkus app from the git repository URL.

### I know nothing about Ansible, but I want to install my Quarkus app, can I?

Yes! It's not rocket science :)

Once you have installed Ansible on your computer you can simply run the following command (note that the inventory file needs to be populated with the name(s) of the machine(s) you wish to install the Quarkus app on):

    $ ansible-galaxy collection install middleware_automation.quarkus
    $ ansible-playbook -i inventory middleware_automation.quarkus.playbook

<!--start requires_ansible-->
## Ansible version compatibility

This collection has been tested against following Ansible versions: **>=2.13.3**.

## Install

Plugins and modules within a collection may be tested with only specific Ansible versions. A collection may contain metadata that identifies these versions.
<!--end requires_ansible-->

## Included content

### Roles

* [quarkus](https://github.com/ansible-middleware/quarkus/blob/main/roles/quarkus/README.md): clone the repo app, build the app and deploys it as a systemd service.
