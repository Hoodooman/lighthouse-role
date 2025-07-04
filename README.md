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
- hosts: monitoring
  roles:
    - role: lighthouse
      vars:
        lighthouse_nginx_server_name: "lighthouse.example.com"
        lighthouse_nginx_ssl_enabled: true
        lighthouse_nginx_ssl_cert: "/etc/ssl/certs/lighthouse.crt"
        lighthouse_nginx_ssl_key: "/etc/ssl/private/lighthouse.key"


License
-------

BSD

Author Information
------------------

shvirtd-19.
