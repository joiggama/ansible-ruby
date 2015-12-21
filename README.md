ruby
=========

This ansible role aims to install ruby on ubuntu systems.

Requirements
------------

None.

Role Variables
--------------

| Name                      | Default                             |                                             |
|:-------------------------:|:-----------------------------------:|:-------------------------------------------:|
| ruby_apt_cache_expiration | 3600                                | Update apt cache window in seconds          |
| ruby_default_version      |                                     | Default ruby version (rbenv global)         |
| ruby_forbid_gem_docs      | true                                | Wheter or not to install gem docs           |
| ruby_install_dependencies | true                                | Whether or not to install dependencies      |
| rbenv_root                | /home/{{ ansible_env.USER }}/.rbenv | Install path for rbenv                      |
| rbenv_version             | master                              | Install version of rbenv                    |
| ruby_build_root           | {{ rbenv_root }}/plugins/ruby-build | Install path for rbenv                      |
| ruby_build_version        | master                              | Install version of ruby-build               |
| ruby_version              | 2.2.3                               | Ruby version to install (ruby-build format) |

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
