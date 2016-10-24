gitconfig
==========

[![Build Status](https://travis-ci.org/suzuki-shunsuke/ansible-gitconfig.svg?branch=master)](https://travis-ci.org/suzuki-shunsuke/ansible-gitconfig)

Install your gitconfig hosted on the Github.

Requirements
------------

* [motemen/ghq](https://github.com/motemen/ghq)

The directory structure of the repository where your git config is hosted must be in the following manner.

```
(repository root)/
  .gitconfig
```

Role Variables
--------------

* ghq_executable: The executable path of ghq command. The default is "ghq".
* remote_repository_path: The remote repository where your gitconfig is hosted.

Dependencies
------------

* [suzuki-shunsuke.ghq-module](https://galaxy.ansible.com/suzuki-shunsuke/ghq-module/)

Example Playbook
----------------

```yaml
- hosts: servers
  roles:
  - role: suzuki-shunsuke.gitconfig
    remote_repository_path: suzuki-shunsuke/git.conf
    ghq_executable: "{{ansible_env.HOME}}/.go/bin/ghq"
```

License
-------

MIT
