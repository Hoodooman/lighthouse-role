Ansible Role: Vector
=========

An Ansible role that installs and configures [Vector](https://vector.dev/) log collector on Linux servers.

Requirements
------------

- Ansible >= 2.10
- Debian/Ubuntu or RHEL/CentOS

Role Variables
--------------

Dependencies
------------

| Variable | Default | Description |
|----------|---------|-------------|
| `vector_version` | `0.33.X` | Vector version to install |
| `vector_download_url` | `"https://packages.timber.io/vector/{{ vector_version }}/vector-{{ vector_version }}-amd64.deb"` | Download URL for Vector package |
| `vector_install_method` | `package` | Installation method (package or archive) |

Example Playbook
----------------

```yaml
- hosts: all
  roles:
    - role: vector
      vars:
        vector_sources:
          syslog:
            type: syslog
            mode: tcp
            address: "0.0.0.0:514"
        vector_sinks:
          clickhouse:
            type: clickhouse
            inputs: ["syslog"]
            host: "clickhouse-server"
            database: "logs"
            table: "system_logs"

License
-------

BSD

Author Information
------------------

shvirtd-19.
