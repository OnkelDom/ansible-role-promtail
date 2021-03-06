# Ansible Role: Promtail

[![ubuntu-18](https://img.shields.io/badge/ubuntu-18.x-orange?style=flat&logo=ubuntu)](https://ubuntu.com/)
[![ubuntu-20](https://img.shields.io/badge/ubuntu-20.x-orange?style=flat&logo=ubuntu)](https://ubuntu.com/)
[![debian-9](https://img.shields.io/badge/debian-9.x-orange?style=flat&logo=debian)](https://www.debian.org/)
[![debian-10](https://img.shields.io/badge/debian-10.x-orange?style=flat&logo=debian)](https://www.debian.org/)

[![License](https://img.shields.io/badge/license-MIT%20License-brightgreen.svg?style=flat)](https://opensource.org/licenses/MIT)
[![GitHub issues](https://img.shields.io/github/issues/OnkelDom/ansible-role-promtail?style=flat)](https://github.com/OnkelDom/ansible-role-promtail/issues)
[![GitHub tag](https://img.shields.io/github/tag/OnkelDom/ansible-role-promtail.svg?style=flat)](https://github.com/OnkelDom/ansible-role-promtail/tags)
[![GitHub action](https://github.com/OnkelDom/ansible-role-promtail/workflows/ansible-lint/badge.svg)](https://github.com/OnkelDom/ansible-role-promtail)

## Description

Deploy [Promtail](https://github.com/grafana/loki) using ansible.

## Requirements

- Ansible >= 2.9 (It might work on previous versions, but we cannot guarantee it)

## Role Variables

All variables which can be overridden are stored in [defaults/main.yml](defaults/main.yml) file as well as in table below.

| Name           | Default Value | Description                        |
| -------------- | ------------- | -----------------------------------|
| `proxy_env` | {} | Proxy environment variables |
| `promtail_version` | 2.2.0 | app version |
| `promtail_listen_port` | 9080 | default listen port |
| `promtail_listen_address` | 0.0.0.0 | default listen address |
| `promtail_config_dir` | /etc/promtail | default config dir |
| `promtail_config_file` | config.yml | default config file |
| `promtail_config_file_sd_dir` | "{{ promtail_config_dir }}/file_sd" | default file_sd dir |
| `promtail_binary_install_dir` | /usr/local/bin | default bin dir |
| `promtail_data_dir` | /var/lib/promtail | default data dir |
| `promtail_config_log_level` | warn | default log level |
| `promtail_system_user` | loki | default system user |
| `promtail_system_group` | loki | default system group |
| `promtail_user_additional_groups` | adm | additional groups |
| `promtail_config` | [defaults/main.yml#L16](defaults/main.yml#L16) | server config |

## Example

### Playbook

```yaml
---
- hosts: all
  roles:
  - onkeldom.promtail
```

## Contributing

See [contributor guideline](CONTRIBUTING.md).

## License

This project is licensed under MIT License. See [LICENSE](/LICENSE) for more details.
