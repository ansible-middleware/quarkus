Quarkus Install role
====================

A role to automate checkout, build and deployment of Quarkus application.

Requirements
------------

Requirements on the target system are ensured by the role.

<!--start argument_specs-->
Role Defaults
-------------

| Variable | Description | Default |
|:---------|:------------|:--------|
|`quarkus_builder_host`| `hostname of the system in charge of building the Quarkus application` | `localhost` |
|`quarkus_build_app`| `Should Ansible build the application from source` | `true` |
|`quarkus_build_delete_workdir`| `Should Ansible delete the workdir` | `true` |
|`quarkus_build_shell_interpreter`| `Shell interpreter used by Ansible` | `/bin/bash` |
|`quarkus_build_relative_path_to_deploy_dir`| `Path to the directory containing the Quarkus app to deploy` | `target/quarkus-app/` |
|`quarkus_java_package_version`| `Package name of the JDK to used to build and run the Quarkus app` | `'java-17-openjdk'` |
|`quarkus_java_home`| `Path to the Java Home used` | `'/usr/lib/jvm/jre-17-openjdk'` |
|`quarkus_app_workdir`| `Path to the app work directory` | `'/tmp/workdir'` |
|`quarkus_app_user`| `System user used to run the app` | `quarkus_app` |
|`quarkus_app_group`| `System group used to run the app` | `"{{ quarkus_app_user }}"` |
|`quarkus_app_service_name`| `Systemd service name for the app` | `"{{ app_name }}"` |
|`quarkus_deploy_systemd_service_conf`| `Path to the (systemd) service configuration` | `"/etc/{{ app_name }}.conf"` |
|`quarkus_app_validation_host`| `Hostname of the system used to validate that the Quarkus app has been properly deployed` | `localhost` |
|`quarkus_systemd_service_template`| `Path to the template to use for systemd service definition.` | `'templates/service_systemd.j2'` |
|`quarkus_systemd_home`| `Path to systemd folder (where the service is deployed)` | `'/usr/lib/systemd/system'` |
|`quarkus_app_port`| `Network port used by the Quarkus app` | `8080` |
|`quarkus_app_port_firewalld`| `Port used by the Quarkus that needs to be opened in firewalld` | `"{{ quarkus_app_port }}"` |
|`quarkus_app_firewalld_enabled`| `Indicate if Ansible should open port in firewalld` | `false` |
|`quarkus_firewalld_package`| `Package name to install firewalld.` | `firewalld` |

Role Variables
--------------

* No required variables

<!--end argument_specs-->

## Dependencies

## Example Playbooks

### Default Install

Installs the default version of Quarkus to the default location with the default user.

```
---
- name: "Build and deploy my Quarkus app"
  hosts: "{{ hosts_group_name | default('localhost') }}"
  collections:
    - middleware_automation.quarkus
  roles:
    - quarkus
```
## License

Apache License 2

## Author Information

* [Romain Pelisse](https://github.com/rpelisse)
