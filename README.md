# ansible-gitconfig

[![Ansible Role](https://img.shields.io/ansible/role/12951.svg)](https://galaxy.ansible.com/suzuki-shunsuke/gitconfig/)
[![Ansible Role](https://img.shields.io/ansible/role/d/12951.svg)](https://galaxy.ansible.com/suzuki-shunsuke/gitconfig/)
[![Build Status](https://travis-ci.org/suzuki-shunsuke/ansible-gitconfig.svg?branch=master)](https://travis-ci.org/suzuki-shunsuke/ansible-gitconfig)
[![GitHub last commit](https://img.shields.io/github/last-commit/suzuki-shunsuke/ansible-gitconfig.svg)](https://github.com/suzuki-shunsuke/ansible-gitconfig)

ansible role to install gitconfig hosted on the Github.

## Requirements

Nothing.

## Role Variables

name | required | default | description
--- | --- | --- | ---
gitconfig_repo | yes | |
gitconfig_cloned_dest | yes | |
gitconfig_version | no | HEAD |
gitconfig_src | no | ".gitconfig" |

## Dependencies

Nothing.

## Example Playbook

```yaml
- hosts: servers
  roles:
  - role: suzuki-shunsuke.gitconfig
    gitconfig_repo: "https://github.com/suzuki-shunsuke/git.conf"
    gitconfig_cloned_dest: "{{ansible_env.HOME}}/repos/src/github.com/suzuki-shunsuke/git.conf"
    gitconfig_src: "{{(ansible_os_family == 'Darwin')|ternary('mac', 'linux')}}_gitconfig"
```

## License

[MIT](LICENSE)
