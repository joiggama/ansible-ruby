Role Name
=========

[![Join the chat at https://gitter.im/joiggama/ansible-ruby](https://badges.gitter.im/Join%20Chat.svg)](https://gitter.im/joiggama/ansible-ruby?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)

This ansible role aims to install ruby on ubuntu systems.

Requirements
------------

None.

Role Variables
--------------

| Name                 | Default                           |                                             |
|:--------------------:|:---------------------------------:|:-------------------------------------------:|
| apt_cache_expiration | 3600                              | Update apt cache window in seconds          |
| default_version      |                                   | Default ruby version (rbenv global)         |
| forbid_gem_docs      | true                              | Wheter or not to install gem docs           |
| install_dependencies | true                              | Whether or not to install dependencies      |
| rbenv_root           | /home/{{ansible_env.USER}}/.rbenv | Install path for rbenv                      |
| rbenv_version        | v0.4.0                            | Install version of rbenv                    |
| ruby_build_root      | {{rbenv_root}}/plugins/ruby-build | Install path for rbenv                      |
| ruby_build_version   | v20150319zf                       | Install version of ruby-build               |
| version              | 2.2.0                             | Ruby version to install (ruby-build format) |

**NOTE:** Some of these defaults require facts to be gathered.

Dependencies
------------

- joiggama.rbenv
- joiggama.ruby-build

**NOTE:** This role already provides [sane defaults](#role-variables) for these dependencies.

Example Playbook
----------------

```yml
- gather_facts: true
  hosts:        all
  roles:
                - ansible-ruby
```

License
-------

[MIT](LICENSE.md)
