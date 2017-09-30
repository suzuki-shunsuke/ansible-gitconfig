# ansible-gitconfig

[![Build Status](https://travis-ci.org/suzuki-shunsuke/ansible-gitconfig.svg?branch=master)](https://travis-ci.org/suzuki-shunsuke/ansible-gitconfig)

ansible role to install gitconfig hosted on the Github.

## Requirements

The directory structure of the repository where your git config is hosted must be in the following manner.

```
(repository root)/
  .gitconfig
```

## Role Variables

name | required | default | description
--- | --- | --- | ---
gitconfig_repo | yes | |
gitconfig_cloned_dest | yes | |
gitconfig_version | no | HEAD |

## Dependencies

Nothing.

## Example Playbook

```yaml
- hosts: servers
  roles:
  - role: suzuki-shunsuke.gitconfig
    gitconfig_repo: "https://github.com/suzuki-shunsuke/git.conf"
    gitconfig_cloned_dest: "{{ansible_env.HOME}}/repos/src/github.com/suzuki-shunsuke/git.conf"
    gitconfig_version: mac
```

## License

[MIT](LICENSE)
