# ROLE dginhoux.prometheus_keepalived_exporter



## DESCRIPTION

This ansible role install, configure and uninstall prometheus keepalived exporter.<br />
It can be deploy as binary downloaded from github OR as docker (no public image, you have to build an image and push to a registry)



## REQUIREMENTS

#### SUPPORTED PLATFORMS

This role require a supported platform.<br />
It will skip node with unsupported platform to avoid any compatibility problem.<br />
This behaviour can be bypassed by settings the following variable `asserts_bypass=True`.

| Platform | Versions |
|----------|----------|
| Debian | buster, bullseye |
| Fedora | 33, 34, 35, 36, 37 |
| EL | 7, 8 |

#### ANSIBLE VERSION

Ansible >= 2.12

#### DEPENDENCIES

None.



## INSTALLATION

#### ANSIBLE GALAXY

```shell
ansible-galaxy install dginhoux.prometheus_keepalived_exporter
```
#### GIT

```shell
git clone https://github.com/dginhoux/ansible_role.prometheus_keepalived_exporter dginhoux.prometheus_keepalived_exporter
```


## USAGE

#### EXAMPLE PLAYBOOK

```yaml
- hosts: all
  roles:
    - name: start role dginhoux.prometheus_keepalived_exporter
      ansible.builtin.include_role:
        name: dginhoux.prometheus_keepalived_exporter
```


## VARIABLES

#### DEFAULT VARIABLES

Defaults variables defined in `defaults/main.yml` : 

```yaml
deploy_keepalived_exporter: install
deploy_keepalived_exporter_mode: binary
prometheus_keepalived_exporter_docker_image: registry-build.infra.ginhoux.net:5001/ginhoux.net/keepalived-exporter
prometheus_keepalived_exporter_name: keepalived-exporter
prometheus_keepalived_exporter_version: 1.2.0
prometheus_keepalived_exporter_arch: amd64
prometheus_keepalived_exporter_download_url: >-
  https://github.com/cafebazaar/keepalived-exporter/releases/
  download/v{{prometheus_keepalived_exporter_version}}/
  {{prometheus_keepalived_exporter_name}}-{{prometheus_keepalived_exporter_version}}.
  linux-{{prometheus_keepalived_exporter_arch}}.zip
prometheus_keepalived_exporter_bin_path: /usr/local/bin/{{prometheus_keepalived_exporter_name}}
prometheus_keepalived_exporter_options: ""
prometheus_keepalived_exporter_state: started
prometheus_keepalived_exporter_enabled: true
prometheus_keepalived_exporter_port: 9165
prometheus_keepalived_exporter_run_user: keepalived-exporter
prometheus_keepalived_exporter_nice_level: 0
```

#### DEFAULT OS SPECIFIC VARIABLES

Those variables files are located in `vars/*.yml` are used to handle OS differences.<br />
One of theses is loaded dynamically during role runtime using the `include_vars` module and set OS specifics variable's.

`NOT USED BY THIS ROLE`



## AUTHOR

Dany GINHOUX - https://github.com/dginhoux



## LICENSE

MIT
